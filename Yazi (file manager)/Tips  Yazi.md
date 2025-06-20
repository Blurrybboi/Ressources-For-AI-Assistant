---
title: "Tips | Yazi"
source: "https://yazi-rs.github.io/docs/tips"
author:
published:
created: 2025-06-17
description: "A few helpful tips for using Yazi."
tags:
  - "clippings"
---
These tips require prior knowledge of the Yazi configuration file.

If you are using Yazi for the first time, please read our [configuration](https://yazi-rs.github.io/docs/configuration/overview) and [plugins](https://yazi-rs.github.io/docs/plugins/overview) documentation first.

## Full border

![](https://yazi-rs.github.io/webp/full-border.webp)

Moved to: [https://github.com/yazi-rs/plugins/tree/main/full-border.yazi](https://github.com/yazi-rs/plugins/tree/main/full-border.yazi)

## Dropping to the shell

Add this keybinding to your `keymap.toml`:

```toml
[[mgr.prepend_keymap]]
on   = "!"
for  = "unix"
run  = 'shell "$SHELL" --block'
desc = "Open $SHELL here"

# If you also using Yazi on Windows:
[[mgr.prepend_keymap]]
on   = "!"
for  = "windows"
run  = 'shell "powershell.exe" --block'
desc = "Open PowerShell here"
```

## Close input by once Esc press

You can change the Esc of input component from the default `escape` to `close` command, in your `keymap.toml`:

```toml
[[input.prepend_keymap]]
on   = "<Esc>"
run  = "close"
desc = "Cancel input"
```

to exiting input directly, without entering Vi mode, making it behave like a regular input box.

## Smart enter: open files or enter directories all in one key

Moved to: [https://github.com/yazi-rs/plugins/tree/main/smart-enter.yazi](https://github.com/yazi-rs/plugins/tree/main/smart-enter.yazi)

## Smart paste: paste files without entering the directory

Moved to: [https://github.com/yazi-rs/plugins/tree/main/smart-paste.yazi](https://github.com/yazi-rs/plugins/tree/main/smart-paste.yazi)

## Smart tab: create a tab and enter the hovered directory

Save these lines as `~/.config/yazi/plugins/smart-tab.yazi/main.lua`:

```lua
--- @sync entry
return {
    entry = function()
        local h = cx.active.current.hovered
        ya.emit("tab_create", h and h.cha.is_dir and { h.url } or { current = true })
    end,
}
```

Then bind it to the t key, in your `keymap.toml`:

```toml
[[mgr.prepend_keymap]]
on   = "t"
run  = "plugin smart-tab"
desc = "Create a tab and enter the hovered directory"
```

## Smart switch: create tab if the tab being switched to does not exist

Save these lines as `~/.config/yazi/plugins/smart-switch.yazi/main.lua`:

```lua
--- @sync entry
local function entry(_, job)
    local cur = cx.active.current
    for _ = #cx.tabs, job.args[1] do
        ya.emit("tab_create", { cur.cwd })
        if cur.hovered then
            ya.emit("reveal", { cur.hovered.url })
        end
    end
    ya.emit("tab_switch", { job.args[1] })
end

return { entry = entry }
```

Then bind it to the 2 key, in your `keymap.toml`:

```toml
[[mgr.prepend_keymap]]
on   = "2"
run  = "plugin smart-switch 1"
desc = "Switch or create tab 2"
```

## Folder-specific rules

You can subscribe to directory change events through the [`cd` event provided by DDS](https://yazi-rs.github.io/docs/dds#cd), and then do any action you want, such as setting different sorting methods for specific directories.

The following code demonstrates making the `Downloads` directory to sort by modification time, while others are sorted alphabetically. Save these lines as `~/.config/yazi/plugins/folder-rules.yazi/main.lua`:

```lua
local function setup()
    ps.sub("cd", function()
        local cwd = cx.active.current.cwd
        if cwd:ends_with("Downloads") then
            ya.emit("sort", { "mtime", reverse = true, dir_first = false })
        else
            ya.emit("sort", { "alphabetical", reverse = false, dir_first = true })
        end
    end)
end

return { setup = setup }
```

Then enable it in your `~/.config/yazi/init.lua`:

```lua
require("folder-rules"):setup()
```

Credits to [@tianze0926 for sharing it](https://github.com/sxyazi/yazi/issues/623#issuecomment-2096270843).

## Folder-specific previewer and preloader

In addition to the `mime` rules, Yazi also has `name` rules for pre{viewer,loader}, which accept a glob expression. This allows for flexible creation of different pre{viewer,loader} rules for various directories.

For example, you can use the `noop` builtin preloader for a remote mount point like `/remote`, disabling preloads in that directory:

```toml
# yazi.toml
[[plugin.prepend_preloaders]]
name = "/remote/**"
run  = "noop"
```

If you want to disable all the preset previewers, preloaders:

```toml
# yazi.toml
[plugin]
preloaders = []
previewers = []
```

## Drag and drop via dragon

Original post: [https://github.com/sxyazi/yazi/discussions/327](https://github.com/sxyazi/yazi/discussions/327)

```toml
[[mgr.prepend_keymap]]
on  = "<C-n>"
run = 'shell -- dragon -x -i -T "$1"'
```

## Linux: Copy selected files to the system clipboard while yanking

Yazi allows multiple commands to be bound to a single key, so you can set y to not only do the `yank` but also run a shell script:

```toml
[[mgr.prepend_keymap]]
on  = "y"
run = [ 'shell -- echo "$@" | xclip -i -selection clipboard -t text/uri-list', "yank" ]
```

The above is available on X11, there is also a Wayland version (Thanks [@hurutparittya for sharing this](https://discord.com/channels/1136203602898194542/1136203604076802092/1188498323867455619) in Yazi's discord server):

```toml
[[mgr.prepend_keymap]]
on  = "y"
run = [ 'shell -- for path in "$@"; do echo "file://$path"; done | wl-copy -t text/uri-list', "yank" ]
```

## cd back to the root of the current Git repository

```toml
[[mgr.prepend_keymap]]
on = [ "g", "r" ]
run = 'shell -- ya emit cd "$(git rev-parse --show-toplevel)"'
```

Credits to [@aidanzhai for sharing it](https://t.me/yazi_rs/3325/15373) in Yazi's telegram group.

## Unix: Add subtitle to the running MPV

Add these lines to your `~/.config/yazi/yazi.toml`:

```toml
[[opener.add-sub]]
run  = ''' echo sub-add "'$0'" | socat - /tmp/mpv.sock '''
desc = "Add sub to MPV"

[[open.prepend_rules]]
name = "*.{ass,srt,ssa,sty,sup,vtt}"
use  = [ "add-sub", "edit" ]
```

To make it work, make sure you've:

1. Installed `socat` and can be found in your `$PATH`
2. Enabled and configured the ipc socket to `/tmp/mpv.sock`, that is, include:
	```markdown
	input-ipc-server=/tmp/mpv.sock
	```
	in your `~/.config/mpv/mpv.conf`. See [the documentation of `--input-ipc-server`](https://mpv.io/manual/stable/#options-input-ipc-server) for more info.

## Maximize preview pane

Moved to: [https://github.com/yazi-rs/plugins/tree/main/toggle-pane.yazi](https://github.com/yazi-rs/plugins/tree/main/toggle-pane.yazi)

## Hide preview pane

Moved to: [https://github.com/yazi-rs/plugins/tree/main/toggle-pane.yazi](https://github.com/yazi-rs/plugins/tree/main/toggle-pane.yazi)

## Navigation in the parent directory without leaving the CWD

Save these lines as `~/.config/yazi/plugins/parent-arrow.yazi/main.lua`:

Then bind it for K and J key, in your `keymap.toml`:

```toml
[[mgr.prepend_keymap]]
on  = "K"
run = "plugin parent-arrow -1"

[[mgr.prepend_keymap]]
on  = "J"
run = "plugin parent-arrow 1"
```

## Confirm before quitting if multiple tabs are open

Save these lines as `~/.config/yazi/plugins/confirm-quit.yazi/main.lua`:

```lua
local count = ya.sync(function() return #cx.tabs end)

local function entry()
    if count() < 2 then
        return ya.emit("quit", {})
    end

    local yes = ya.confirm {
        pos = { "center", w = 60, h = 10 },
        title = "Quit?",
        content = ui.Text("There are multiple tabs open. Are you sure you want to quit?"):wrap(ui.Wrap.YES),
    }
    if yes then
        ya.emit("quit", {})
    end
end

return { entry = entry }
```

Next, bind it to the q key in your `keymap.toml`:

```toml
[[mgr.prepend_keymap]]
on  = "q"
run = "plugin confirm-quit"
```

Credits to [@lpnh for sharing it](https://github.com/sxyazi/yazi/issues/2267#issuecomment-2624805134).

## No status bar

![](https://yazi-rs.github.io/webp/no-status-bar.webp)

Moved to: [https://github.com/yazi-rs/plugins/tree/main/no-status.yazi](https://github.com/yazi-rs/plugins/tree/main/no-status.yazi)

## Show symlink in status bar

![](https://yazi-rs.github.io/webp/symlink-in-status.webp)

Add the following code to your `~/.config/yazi/init.lua`:

```lua
Status:children_add(function(self)
    local h = self._current.hovered
    if h and h.link_to then
        return " -> " .. tostring(h.link_to)
    else
        return ""
    end
end, 3300, Status.LEFT)
```

## Show user/group of files in status bar

![](https://yazi-rs.github.io/webp/owner.webp)

Add the following code to your `~/.config/yazi/init.lua`:

```lua
Status:children_add(function()
    local h = cx.active.current.hovered
    if not h or ya.target_family() ~= "unix" then
        return ""
    end

    return ui.Line {
        ui.Span(ya.user_name(h.cha.uid) or tostring(h.cha.uid)):fg("magenta"),
        ":",
        ui.Span(ya.group_name(h.cha.gid) or tostring(h.cha.gid)):fg("magenta"),
        " ",
    }
end, 500, Status.RIGHT)
```

## Show username and hostname in header

![](https://yazi-rs.github.io/webp/hostname-in-header.webp)

Add the following code to your `~/.config/yazi/init.lua`:

## macOS: Preview files with the system Quick Look

```toml
[[mgr.prepend_keymap]]
on = "<C-p>"
run = 'shell -- qlmanage -p "$@"'
```

Credits to [@UncleGravity for sharing it](https://discord.com/channels/1136203602898194542/1146658361740369960/1293471643959558156) in Yazi's discord server.

## Specify a different editor for bulk renaming

For bulk renaming, Yazi finds the first matching opener in your [`[open]`](https://yazi-rs.github.io/docs/configuration/yazi#open) rules with:

|  | Value |
| --- | --- |
| `block` | `true` |
| `name` | `"bulk-rename.txt"` |
| `mime` | `"text/plain"` |

to use as the editor for editing the file list.

By default, this matches your editor used for opening normal text files, if you want to use an editor different from that:

```toml
# ~/.config/yazi/yazi.toml
[[opener.bulk-rename]]
run   = 'hx "$@"'
block = true

[[open.prepend_rules]]
name = "bulk-rename.txt"
use  = "bulk-rename"
```

## Linux: Yazi as your system file chooser

The `xdg-desktop-portal-termfilechooser` backend lets you replace the default file picker with Yazi, providing seamless integration with applications, such as Firefox.

For installation steps, refer to the [installation guide](https://github.com/hunkyburrito/xdg-desktop-portal-termfilechooser?tab=readme-ov-file#installation) and additional instructions available there.

## File tree picker in Helix with Zellij

Yazi can be used as a file picker to browse and open file(s) in your current Helix instance (running in a Zellij session).

Add a keymap to your Helix config, for example Ctrl + y:

If you also want the ability to open files in split panes, you can define additional keybindings:

Then save the following script as `~/.config/helix/yazi-picker.sh`:

```sh
#!/usr/bin/env bash

paths=$(yazi "$2" --chooser-file=/dev/stdout | while read -r; do printf "%q " "$REPLY"; done)

if [[ -n "$paths" ]]; then
    zellij action toggle-floating-panes
    zellij action write 27 # send <Escape> key
    zellij action write-chars ":$1 $paths"
    zellij action write 13 # send <Enter> key
else
    zellij action toggle-floating-panes
fi
```

Note: this uses a floating window, but you should also be able to open a new pane to the side, or in place. Review the Zellij documentation for more info.

Original post: [https://github.com/zellij-org/zellij/issues/3018#issuecomment-2086166900](https://github.com/zellij-org/zellij/issues/3018#issuecomment-2086166900), credits to [@rockboynton](https://github.com/rockboynton), [@postsolar](https://github.com/postsolar), [@TheAwiteb](https://github.com/TheAwiteb) and [@Dreaming-Codes](https://github.com/Dreaming-Codes) for sharing and polishing it!

## File tree picker in Helix with tmux

Yazi can be used as a file picker to browse and open file(s) in your current Helix instance (running in a tmux session).

Add a keymap to your Helix config, for example Ctrl + y:

```toml
# ~/.config/helix/config.toml
[keys.normal]
C-y = ":sh tmux new-window -n fx '~/.config/helix/yazi-picker.sh open'"
```

If you also want the ability to open files in split panes, you can define additional keybindings:

```toml
# ~/.config/helix/config.toml
[keys.normal.C-y]
# Open file(s) in the current window
y = ":sh tmux new-window -n fx '~/.config/helix/yazi-picker.sh open'"
# Open file(s) in a vertical split
v = ":sh tmux new-window -n fx '~/.config/helix/yazi-picker.sh vsplit'"
# Open file(s) in a horizontal split
h = ":sh tmux new-window -n fx '~/.config/helix/yazi-picker.sh hsplit'"
```

Then save the following script as `~/.config/helix/yazi-picker.sh`:

```sh
#!/usr/bin/env bash

paths=$(yazi --chooser-file=/dev/stdout)

if [[ -n "$paths" ]]; then
    tmux last-window
    tmux send-keys Escape
    tmux send-keys ":$1 $paths"
    tmux send-keys Enter
else
    tmux kill-window -t fx
fi
```

## Email selected files

To send selected files using [Thunderbird](https://www.thunderbird.net/), with a keybinding Ctrl + m:

```toml
# ~/.config/yazi/keymap.toml
[[mgr.prepend_keymap]]
on  = "<C-m>"
run = '''shell --
    paths=$(for p in "$@"; do echo "$p"; done | paste -s -d,)
    thunderbird -compose "attachment='$paths'"
'''
```

Or, use the [NeoMutt](https://neomutt.org/) command-line mail client:

```toml
# ~/.config/yazi/keymap.toml
[[mgr.prepend_keymap]]
on  = "<C-m>"
run = 'shell --block -- neomutt -a "$@"'
```

## Make Yazi even faster than fast

While Yazi is already fast, there is still plenty of room for optimization for specific users or under certain conditions:

- For users who don't need image previews at all, disabling the default `image` previewer and preloader will make Yazi faster by reducing the I/O read file and CPU decode image consumption.
- For users managing network files, it's recommended to [disable all previewers and preloaders](https://yazi-rs.github.io/docs/tips#folder-previewer) since previewing and preloading these files means they need to be downloaded locally.
- For low-spec devices like Raspberry Pi, [reducing the concurrency](https://yazi-rs.github.io/docs/configuration/yazi#tasks) will make Yazi faster since the default configuration is optimized for PCs, and high concurrency on these low-spec devices may have the opposite effect.
- For users who don't need accurate mime-type, [`mime-ext.yazi`](https://github.com/yazi-rs/plugins/tree/main/mime-ext.yazi) may be useful, as it simply returns mime-type based on file extensions, while Yazi defaults to obtaining mime-type based on file content for accuracy. Mime-type is used for matching opening, previewing, rendering rules. Encourage users to choose an appropriate `mime` plugin based on their needs, which is why we decided to open it up to plugin developers.
- For high-performance terminal emulators, lowering the [`image_delay` option](https://yazi-rs.github.io/docs/configuration/yazi/#preview.image_delay) or setting it to 0 can reduce image preview latency.
---
title: "Image Preview | Yazi"
source: "https://yazi-rs.github.io/docs/image-preview"
author:
published:
created: 2025-06-17
description: "How to preview images in Yazi."
tags:
  - "clippings"
---
Yazi has done a lot of work to adapt to different terminals and multiplexers, trying their best to make it out-of-the-box for users.

This is by no means a simple task, to reduce maintenance costs, we only guarantee it is available in the ***latest version*** of terminals and multiplexers (tmux, Zellij):

| Platform | Protocol | Support |
| --- | --- | --- |
| [kitty](https://github.com/kovidgoyal/kitty) (>= 0.28.0) | [Kitty unicode placeholders](https://sw.kovidgoyal.net/kitty/graphics-protocol/#unicode-placeholders) | ✅ Built-in |
| [iTerm2](https://iterm2.com/) | [Inline images protocol](https://iterm2.com/documentation-images.html) | ✅ Built-in |
| [WezTerm](https://github.com/wez/wezterm) | [Inline images protocol](https://iterm2.com/documentation-images.html) | ✅ Built-in |
| [Konsole](https://invent.kde.org/utilities/konsole) | [Kitty old protocol](https://github.com/sxyazi/yazi/blob/main/yazi-adapter/src/drivers/kgp_old.rs) | ✅ Built-in |
| [foot](https://codeberg.org/dnkl/foot) | [Sixel graphics format](https://www.vt100.net/docs/vt3xx-gp/chapter14.html) | ✅ Built-in |
| [Ghostty](https://github.com/ghostty-org/ghostty) | [Kitty unicode placeholders](https://sw.kovidgoyal.net/kitty/graphics-protocol/#unicode-placeholders) | ✅ Built-in |
| [Windows Terminal](https://github.com/microsoft/terminal) (>= v1.22.10352.0) | [Sixel graphics format](https://www.vt100.net/docs/vt3xx-gp/chapter14.html) | ✅ Built-in |
| [st with Sixel patch](https://github.com/bakkeby/st-flexipatch) | [Sixel graphics format](https://www.vt100.net/docs/vt3xx-gp/chapter14.html) | ✅ Built-in |
| [Warp](https://www.warp.dev/) (macOS/Linux only) | [Inline images protocol](https://iterm2.com/documentation-images.html) | ✅ Built-in |
| [Tabby](https://github.com/Eugeny/tabby) | [Inline images protocol](https://iterm2.com/documentation-images.html) | ✅ Built-in |
| [VSCode](https://github.com/microsoft/vscode) | [Inline images protocol](https://iterm2.com/documentation-images.html) | ✅ Built-in |
| [Rio](https://github.com/raphamorim/rio) | [Inline images protocol](https://iterm2.com/documentation-images.html) | ❌ Rio doesn't correctly clear images [#709](https://github.com/raphamorim/rio/issues/709) |
| [Black Box](https://gitlab.gnome.org/raggesilver/blackbox) | [Sixel graphics format](https://www.vt100.net/docs/vt3xx-gp/chapter14.html) | ✅ Built-in |
| [Hyper](https://github.com/vercel/hyper) | [Inline images protocol](https://iterm2.com/documentation-images.html) | ✅ Built-in |
| [Bobcat](https://github.com/ismail-yilmaz/Bobcat) | [Inline images protocol](https://iterm2.com/documentation-images.html) | ✅ Built-in |
| X11 / Wayland | Window system protocol | ☑️ [Überzug++](https://github.com/jstkdng/ueberzugpp) required |
| Fallback | [ASCII art (Unicode block)](https://en.wikipedia.org/wiki/ASCII_art) | ☑️ [Chafa](https://hpjansson.org/chafa/) required |

Yazi automatically selects the appropriate preview method for you, based on the priority from top to bottom. That's relying on the `$TERM`, `$TERM_PROGRAM`, and `$XDG_SESSION_TYPE` variables, make sure you don't overwrite them by mistake!

For instance, if your terminal is Alacritty, which doesn't support displaying images itself, but you are running on an X11/Wayland environment, it will automatically use the "Window system protocol" to display images - this requires you to have Überzug++ installed.

## tmux users

To enable Yazi's image preview to work correctly in tmux, add the following 3 options to your `tmux.conf`:

Then restart tmux (important):

```sh
tmux kill-server && tmux || tmux
```

Now you should be able to enjoy with the image preview.

Note that if [the protocol you are using](https://yazi-rs.github.io/docs/#protocol) is Sixel, make sure you passed `--enable-sixel` when building tmux, as it's disabled by default. You can verify this through [tmux/tmux#4104](https://github.com/tmux/tmux/issues/4104#issuecomment-2326339395).

## Zellij users

Zellij currently only supports the Sixel graphics format, so you will need a terminal that also supports Sixel.

Note that, Zellij's Sixel implementation is quite buggy and has serious performance issues at the moment, causing noticeable lagginess when quickly switching between images, and sometimes even [image tearing](https://github.com/zellij-org/zellij/issues/2576#issuecomment-1707107473) or [not working at all](https://github.com/zellij-org/zellij/issues/2814#issuecomment-2318473921).

This situation won't improve until Zellij enhances its Sixel implementation or [provides a passthrough mode](https://github.com/zellij-org/zellij/issues/775). If the image is a stronger need to you, consider running Yazi outside of Zellij or using Überzug++:

```sh
# Deceive Yazi into thinking you're running in kitty,
# forcing it fallback to Überzug++ or Chafa
TERM=xterm-kitty yazi
```

## Windows users

Currently, only the following 3 terminals support displaying images on Windows:

- WezTerm

## Windows with WSL users

Limited by ConPTY, the Windows edition has had to implement many workarounds, which are not perfect.

However, if you run Yazi in WSL, you can experience perfect image previews through [`wezterm ssh`](https://wezfurlong.org/wezterm/cli/ssh.html).  
[WezTerm](https://wezfurlong.org/wezterm/) is an excellent terminal that can bypass the limitations of ConPTY through its SSH feature, and it's currently the only terminal that allows this approach.

You need to install `sshd` in WSL and start it:

```sh
sudo apt install openssh-server
sudo service ssh restart
```

Then, on the *host* machine, connect to WSL over SSH:

```sh
wezterm ssh 127.0.0.1
```

That's it! you can now get Yazi's image preview working properly.

## Neovim users

The builtin terminal emulator (`:term`) in Neovim [doesn't support any graphic protocols](https://github.com/neovim/neovim/issues/4349), so Yazi will try to fallback to X11/Wayland/Chafa in sequence.

Note that Überzug++ might display images in the wrong position; in that case, please adjust it manually using [`ueberzug_offset`](https://yazi-rs.github.io/docs/configuration/yazi/#preview.ueberzug_scale).

## Why won't my images adapt to terminal size?

The size of the image depends on two factors:

1. The [max\_width](https://yazi-rs.github.io/docs/configuration/yazi#preview.max_width) and [max\_height](https://yazi-rs.github.io/docs/configuration/yazi#preview.max_height) config options, which need to be adjusted by the user as needed.
2. The pixel size of the terminal.

Yazi will use the smaller of these two factors as the image preview size.

However, some terminals (such as VSCode, Tabby, and all Windows terminals) don't implement the `ioctl` system call, before [Add `CSI 14 t` sequence support](https://github.com/crossterm-rs/crossterm/pull/810) is merged, it's not possible to obtain the actual pixel width and height of the terminal.

Hence, only `max_width` and `max_height` will be used in this case.

## How can I know what image protocol Yazi uses?

Yazi provides a `yazi --debug` command that includes all your environment information, such as terminal emulator, image adapter, whether you're in SSH mode, etc.

Run it in the terminal where you want to preview images, and you'll see output like:

```sh
...
Adapter
    Adapter.matches: Kgp
...
```

which indicates the image protocol detected and used by Yazi:

| `Adapter.matches` | Protocol | Notes |
| --- | --- | --- |
| `Kgp` | [Kitty unicode placeholders](https://sw.kovidgoyal.net/kitty/graphics-protocol/#unicode-placeholders) | Ensure your terminal is up-to-date to support it |
| `KgpOld` | [Kitty old protocol](https://github.com/sxyazi/yazi/blob/main/yazi-adapter/src/drivers/kgp_old.rs) | Doesn't work under `tmux` due to the limitations of the protocol itself |
| `Iip` | [Inline images protocol](https://iterm2.com/documentation-images.html) | \- |
| `Sixel` | [Sixel graphics format](https://www.vt100.net/docs/vt3xx-gp/chapter14.html) | See [tmux](https://yazi-rs.github.io/docs/#tmux) and [Zellij](https://yazi-rs.github.io/docs/#zellij) section if you're using either of them |
| `X11` | Window system protocol | [Überzug++](https://github.com/jstkdng/ueberzugpp) is required |
| `Wayland` | Window system protocol | [Überzug++](https://github.com/jstkdng/ueberzugpp) is required and [*only* supports Sway, Hyprland, and Wayfire](https://github.com/jstkdng/ueberzugpp/blob/eea57daece774e152aedba9ac82a8113056fbab4/README.md?plain=1#L12) |
| `Chafa` | [ASCII art (Unicode block)](https://en.wikipedia.org/wiki/ASCII_art) | [Chafa](https://hpjansson.org/chafa/) is required as the last fallback resort |

## Why can't I preview images via Überzug++?

This may be a problem with Überzug++ itself. Please [run Yazi in debug mode](https://yazi-rs.github.io/docs/plugins/overview#logging), then hover on the image that's causing the issue.

Then find the last Überzug++ command in your log file sorted by time, it is usually at the very end of the file and looks like:

```markdown
ueberzugpp command: {"action":"add","identifier":"yazi","x":96,"y":1,"max_width":400,"max_height":150,"path":"/root/test.jpg"}
```

Finally, run `ueberzugpp layer` directly in the terminal without and outside Yazi, and paste the command:

```sh
{"action":"add","identifier":"yazi","x":96,"y":1,"max_width":400,"max_height":150,"path":"/root/test.jpg"}
```

into it, press `Enter`, and to see if any image is shown, without exiting the Überzug++.

If the image shows properly when using Überzug++ independently, but not when used with Yazi, please create a bug report with:

- The contents of your log file.
- The contents of `/tmp/ueberzugpp-$USER.log`.
- A GIF demonstration of the above steps.
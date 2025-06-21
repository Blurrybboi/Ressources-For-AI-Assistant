---
title: "theme.toml | Yazi"
source: "https://yazi-rs.github.io/docs/configuration/theme"
author:
published:
created: 2025-06-17
description: "Learn how to configure your Yazi theme."
tags:
  - "clippings"
---
## Types

### Color

A color. It can be in Hex format with RGB values, such as `"#484D66"`. Or can be one of the following 17 values:

- `"reset"`
- `"black"`
- `"white"`
- `"red"`
- `"lightred"`
- `"green"`
- `"lightgreen"`
- `"yellow"`
- `"lightyellow"`
- `"blue"`
- `"lightblue"`
- `"magenta"`
- `"lightmagenta"`
- `"cyan"`
- `"lightcyan"`
- `"gray"`
- `"darkgray"`

### Style

Appears in a format similar to `{ fg = "#e4e4e4", bg = "black", ... }`, and supports the following properties:

- fg (Color): Foreground color
- bg (Color): Background color
- bold (Boolean): Bold
- dim (Boolean): Dim (not supported by all terminals)
- italic (Boolean): Italic
- underline (Boolean): Underline
- blink (Boolean): Blink
- blink\_rapid (Boolean): Rapid blink
- reversed (Boolean): Reversed foreground and background colors
- hidden (Boolean): Hidden
- crossed (Boolean): Crossed out

## \[flavor\]

See [flavor documentation](https://yazi-rs.github.io/docs/flavors/overview) for more details.

### dark

Flavor name used in dark mode, e.g. `"dracula"`.

|  |  |
| --- | --- |
| Type | `string` |

### light

Flavor name used in light mode, e.g. `"gruvbox"`.

|  |  |
| --- | --- |
| Type | `string` |

## \[mgr\]

### cwd

CWD text style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### hovered

Hovered file style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### preview\_hovered

Hovered file style, in the preview pane.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### find\_keyword

Style of the highlighted portion in the filename.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### find\_position

Style of current file location in all found files to the right of the filename.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### marker\_copied

Copied file marker style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### marker\_cut

Cut file marker style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### marker\_marked

Marker style of pre-selected file in visual mode.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### marker\_selected

Selected file marker style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### count\_copied

Style of copied file number.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### count\_cut

Style of cut file number.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### count\_selected

Style of selected file number.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### border\_symbol

Border symbol, e.g. `"│"`.

|  |  |
| --- | --- |
| Type | `string` |

### border\_style

Border style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### syntect\_theme

Code preview highlighting themes, which are paths to `.tmTheme` files. You can find them on GitHub [using "tmTheme" as a keyword](https://github.com/search?q=tmTheme&type=repositories)

For example, `"~/Downloads/Dracula.tmTheme"`, not available after using a flavor, as flavors always use their own tmTheme files `tmtheme.xml`.

|  |  |
| --- | --- |
| Type | `string` |

## \[tabs\]

### active

Active tab style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### inactive

Inactive tab style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### sep\_inner

Inner separator symbol, e.g. `{ open = "[", close = "]" }`.

|  |  |
| --- | --- |
| Type | `{ open: string, close: string }` |

### sep\_outer

Outer separator symbol, e.g. `{ open = "", close = "" }`.

|  |  |
| --- | --- |
| Type | `{ open: string, close: string }` |

## \[mode\]

### normal\_main

Normal mode main style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### normal\_alt

Normal mode alternative style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### select\_main

Select mode main style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### select\_alt

Select mode alternative style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### unset\_main

Unset mode main style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### unset\_alt

Unset mode alternative style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

## \[status\]

### overall

Overall status bar style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### sep\_left

Left separator symbol, e.g. `{ open = "", close = "]" }`.

|  |  |
| --- | --- |
| Type | `{ open: string, close: string }` |

### sep\_right

Right separator symbol, e.g. `{ open = "[", close = "" }`.

|  |  |
| --- | --- |
| Type | `{ open: string, close: string }` |

### perm\_type

Style of the file type symbol, such as `d` for directory, `-` for file, `l` for symlink, etc.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### perm\_read

Style of the read permission symbol (`r`).

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### perm\_write

Style of the write permission symbol (`w`).

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### perm\_exec

Style of the execute permission symbol (`x`).

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### perm\_sep

Style of the permission separator symbol (`-`).

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### progress\_label

Progress label style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### progress\_normal

Style of the progress bar when it is not in an error state.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### progress\_error

Style of the progress bar when an error occurs.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

## \[which\]

### cols

Number of columns.

|  |  |
| --- | --- |
| Type | `1` \| `2` \| `3` |

### mask

Mask style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### cand

Candidate key style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### rest

Rest key style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### desc

Description style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### separator

Separator symbol, e.g. `" -> "`.

|  |  |
| --- | --- |
| Type | `string` |

### separator\_style

Separator style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

## \[confirm\]

### border

Border style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### title

Title style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### content

Content style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### list

List style, which is the style of the list of items below the content.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### btn\_yes

The style of the yes button.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### btn\_no

The style of the no button.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### btn\_labels

Labels for the yes and no buttons.

The first string is the label for the yes button and the second is the label for the no button.

|  |  |
| --- | --- |
| Type | `[string, string]` |

## \[spot\]

### border

Border style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### title

Title style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### tbl\_col

The style of the selected column in the table.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### tbl\_cell

The style of the selected cell in the table.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

## \[notify\]

### title\_info

Style of the info title.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### title\_warn

Style of the warning title.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### title\_error

Style of the error title.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

## \[pick\]

### border

Border style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### active

Selected item style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### inactive

Unselected item style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

## \[input\]

### border

Border style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### title

Title style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### value

Value style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### selected

Selected value style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

## \[cmp\]

### border

Border style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### active

Selected item style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### inactive

Unselected item style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### icon\_file

File icon.

|  |  |
| --- | --- |
| Type | `string` |

### icon\_folder

Folder icon.

|  |  |
| --- | --- |
| Type | `string` |

### icon\_command

Command icon.

|  |  |
| --- | --- |
| Type | `string` |

## \[tasks\]

### border

Border style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### title

Title style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### hovered

Hovered item style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

## \[help\]

### on

Key column style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### run

Command column style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### desc

Description column style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### hovered

Hovered item style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

Footer style.

|  |  |
| --- | --- |
| Type | [`Style`](https://yazi-rs.github.io/docs/configuration/#types.style) |

### icon\_info

Info icon.

|  |  |
| --- | --- |
| Type | `string` |

### icon\_warn

Warning icon.

|  |  |
| --- | --- |
| Type | `string` |

### icon\_error

Error icon.

|  |  |
| --- | --- |
| Type | `string` |

## \[filetype\]

Set file list item display styles for specific file types, supporting matching by name and mime-type:

```toml
[filetype]
rules = [
    # Images
    { mime = "image/*", fg = "yellow" },

    # Videos
    { mime = "video/*", fg = "magenta" },
    { mime = "audio/*", fg = "magenta" },

    # Empty files
    { mime = "inode/empty", fg = "cyan" },

    # Orphan symbolic links
    { name = "*", is = "orphan", fg = "red" },

    # ...

    # Fallback
    # { name = "*", fg = "white" },
    { name = "*/", fg = "blue" }
]
```

Each rule supports complete [Style properties](https://yazi-rs.github.io/docs/configuration/#types.style). There are two special rule:

- `name = "*"` matches all files.
- `name = "*/"` matches all directories.

You can restrict the specific type of files through `is`, noting that it must be used with either `name` or `mime`. It accepts the following values:

- `block`: Block device
- `char`: Char device
- `exec`: Executable
- `fifo`: FIFO
- `link`: Symbolic link
- `orphan`: Orphan symbolic link
- `sock`: Socket
- `sticky`: File with sticky bit set

## \[icon\]

Yazi has builtin support for [nvim-web-devicons](https://github.com/nvim-tree/nvim-web-devicons), a rich set of icons ready to use. If you want to add your own rules to this set, you can use `prepend_*` and `append_*` to prepend or append rules to the default ones (see [Configuration Mixing](https://yazi-rs.github.io/docs/configuration/overview#mixing) for details):

```toml
[icon]
prepend_dirs = [
    { name = "desktop", text = "", fg = "#563d7c" },
    # ...
]
append_exts = [
    { name = "mp3", text = "", fg = "#00afff" },
    # ...
]
# ...
```

If you want to completely override the default rules, you can do so with:

```toml
[icon]
dirs = [
    { name = "desktop", text = "", fg = "#563d7c" },
    # ...
]
exts = [
    { name = "mp3", text = "", fg = "#00afff" },
    # ...
]
# ...
```

Each icon rule contains the following properties:

- `name` (globs, dirs, files, exts), or `if` (conds): the rule itself, which is a string
- `text`: icon text, which is a string
- `fg`: icon color, which is a [Color](https://yazi-rs.github.io/docs/configuration/theme#types.color)

Icons are matched according to the following priority:

1. globs: glob expressions, e.g., `{ name = "**/Downloads/*.zip", ... }`
2. dirs: directory names, e.g., `{ name = "Desktop", ... }`
3. files: file names, e.g., `{ name = ".bashrc", ... }`
4. exts: extensions, e.g., `{ name = "mp3", ... }`
5. conds: conditions, e.g., `{ if = "!dir", ... }`

`dirs`, `files`, and `exts` are compiled into a HashMap at startup, offering O(1) time complexity for very fast lookups, which should meet most needs.

For more complex and precise rules, such as matching a specific file in a specific directory, use `globs` - these are always executed first to check if any rules in the glob set are met. However, they are much slower than `dirs`, `files`, and `exts`, so it's not recommended to use them excessively.

If none of the above rules match, it will fall back to `conds` to check if any specific conditions are met. `conds` are mostly used for rules related to file metadata, which includes the following conditional factors:

- `dir`: The file is a directory
- `hidden`: The file is hidden
- `link`: The file is a symbolic link
- `orphan`: The file is an orphan (broken symbolic link)
- `dummy`: The file is dummy (failed to load complete metadata, possibly the filesystem doesn't support it, such as FUSE)
- `block`: The file is a block device
- `char`: The file is a char device
- `fifo`: The file is a FIFO
- `sock`: The file is a socket
- `exec`: The file is executable
- `sticky`: The file has the sticky bit set

These conditions support basic `|` (or), `&` (and), `!` (not), and `()` for priority, so you can combine them as needed, for example:

```toml
[icon]
prepend_conds = [
    { if = "hidden & dir",  text = "👻" },  # Hidden directories
    { if = "dir",           text = "📁" },  # Directories
    { if = "!(dir | link)", text = "📄" },  # Normal files (not directories or symlinks)
]
```
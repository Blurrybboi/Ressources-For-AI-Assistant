---
title: "Configuration | Yazi"
source: "https://yazi-rs.github.io/docs/configuration/overview"
author:
published:
created: 2025-06-17
description: "Learn how to configure Yazi."
tags:
  - "clippings"
---
There are three configuration files for Yazi:

- [`yazi.toml`](https://yazi-rs.github.io/docs/configuration/yazi) - General configuration.
- [`keymap.toml`](https://yazi-rs.github.io/docs/configuration/keymap) - Keybindings configuration.
- [`theme.toml`](https://yazi-rs.github.io/docs/configuration/theme) - Color scheme configuration.

You can find the default configuration files on the ***`shipped`*** tag [https://github.com/sxyazi/yazi/tree/ ***shipped*** /yazi-config/preset](https://github.com/sxyazi/yazi/tree/shipped/yazi-config/preset).

To override any of the defaults, begin by creating the corresponding file (from the directory linked above) to:

- `~/.config/yazi/` on Unix-like systems.
- `%AppData%\yazi\config\` on Windows.

For example, to change the visible status of hidden files, start by creating a `yazi.toml` file to:

- `~/.config/yazi/yazi.toml` on Unix-like systems.
- `%AppData%\yazi\config\yazi.toml` on Windows.

Then [copy the required part](https://github.com/sxyazi/yazi/blob/shipped/yazi-config/preset/yazi-default.toml) into it, here is `show_hidden`:

```toml
# yazi.toml
[mgr]
show_hidden = true
```

Yazi has already preset these default configurations in the release, so you don't need to copy the entire file unless you want to completely overwrite them.

## Configuration mixing

The options from your configuration file will be used to override the default. However, for key bindings, if you don't want to override the default directly:

```toml
# keymap.toml
[mgr]
keymap = [
    # ...
]
```

And instead want to customize your keys upon the default, you can use `prepend_*` or `append_*` directories to prepend or append them to the default (See [keymap.toml](https://yazi-rs.github.io/docs/configuration/keymap) for details):

```toml
# keymap.toml
[mgr]
prepend_keymap = [
    # ...
]
append_keymap = [
    # ...
]
```

They are also available for open, icon, previewer, and preloader rules.

## Custom config directory

You can change the Yazi configuration directory by exporting the `YAZI_CONFIG_HOME` environment variable. For example:

```sh
env "YAZI_CONFIG_HOME=~/.config/yazi-alt" yazi
```

will start Yazi with `~/.config/yazi-alt` as the configuration directory, and can have its own `yazi.toml`, `keymap.toml`, `init.lua`, etc. files within it.
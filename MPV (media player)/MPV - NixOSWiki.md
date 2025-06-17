---
title: "MPV - NixOS Wiki"
source: "https://nixos.wiki/wiki/MPV"
author:
published:
created: 2025-06-16
description:
tags:
  - "clippings"
---
There are 2 packages that provide an `mpv` executable:

- `mpv`
- `mpv-unwrapped`

`mpv` is a wrapper for the `mpv` binary which adds `--script=` arguments according to the scripts the wrapper was built with.

If you'd like to add scripts to your `mpv` wrapper, you'll need to create an overlay in `~/.config/nixpkgs/config.nix` or `/etc/nixos/configuration.nix` (if you are using NixOS):

```
nixpkgs.overlays = [
  (self: super: {
    mpv = super.mpv.override {
      scripts = [ self.mpvScripts.<your choice> ];
    };
  })
];
```

All of the scripts for MPV can be found under the `mpvScripts` attribute. You can search for them by running `nix search mpvScripts`. The scripts are defined in the following Nixpkgs directory:

[`pkgs/applications/video/mpv/scripts`](https://github.com/NixOS/nixpkgs/tree/master/pkgs/applications/video/mpv/scripts)

So for example, for adding the MPRIS MPV script, use the following in your `~/.config/nixpkgs/config.nix`:

```
{
  nixpkgs.overlays = [
    (self: super: {
      mpv = super.mpv.override {
        scripts = [ self.mpvScripts.mpris ];
      };
    })
  ];
}
```

## Error, unknown format

If you get the following sort of error, note that mpv currently uses the small ffmpeg version (ffmpeg\_5) instead of the full version (ffmpeg\_5-full).

```
$ mpv --log-file=foo.log av://v4l2:/dev/video5
[lavf] Unknown lavf format v4l2
Failed to recognize file format.

Exiting... (Errors when loading file)
```

To address this problem, you can use the following overlay in your `nixpkgs.overlays`:

```
nixpkgs.overlays = with pkgs; [
    (self: super: {
      mpv-unwrapped = super.mpv-unwrapped.override {
        ffmpeg_5 = ffmpeg_5-full;
      };
    })
  ];
```
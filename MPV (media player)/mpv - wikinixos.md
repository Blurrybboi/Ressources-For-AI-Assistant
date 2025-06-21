---
title: mpv - NixOS Wiki
source: https://wiki.nixos.org/wiki/MPV
author: 
published: 
created: 2025-06-16
description: mpv is an open-source command line media player.
tags:
  - clippings
---
## Installation

#### With nix-shell

```
nix-shell -p mpv
```

#### With NixOS

```
environment.systemPackages = [
  pkgs.mpv
];
```

#### With Home Manager

```
home.packages = [ 
  pkgs.mpv 
];
```

## Configuration

### With Home Manager

#### Basic

```
programs.mpv.enable = true;
```

#### Advanced

```
programs.mpv = {
  enable = true;

  package = (
    pkgs.mpv-unwrapped.wrapper {
      scripts = with pkgs.mpvScripts; [
        uosc
        sponsorblock
      ];

      mpv = pkgs.mpv-unwrapped.override {
        waylandSupport = true;
      };
    }
  );

  config = {
    profile = "high-quality";
    ytdl-format = "bestvideo+bestaudio";
    cache-default = 4000000;
  };
};
```

## Tips and Tricks

#### Where to get scripts

To find more scripts run this in a terminal:

```
nix search nixpkgs mpvScripts
```

The scripts are also defined in the following [Nixpkgs directory](https://github.com/NixOS/nixpkgs/tree/master/pkgs/applications/video/mpv/scripts).

#### Enabling additional features: where to find override options and using umpv

The package override options are defined in the following [Nixpkgs directory](https://github.com/NixOS/nixpkgs/blob/master/pkgs/applications/video/mpv/default.nix). This includes a commonly used first party script called [umpv](https://github.com/mpv-player/mpv/blob/master/TOOLS/umpv) which allows additional files to be appended to the playlist of an open instance. In the nix derivation of mpv, the umpv script is bundled into the program and can be ran from the command line with \`umpv foo.ogg\`. Note that umpv can only be ran with the name of the file being opened and cannot be ran with additional arguments or flags.

For example, here is an overlay showing how to enable JACK audio support:

```
nixpkgs.overlays = [
  (final: prev: {
    mpv = prev.mpv.override {
      mpv = prev.mpv-unwrapped.override {
        jackaudioSupport = true;
      };
    };
  })
];
```

or alternatively, you can define the package inline:

```
(pkgs.mpv.override { mpv = pkgs.mpv-unwrapped.override { jackaudioSupport = true; }; })
```

Also note that commands cannot be passed to mpv using socat when mpv is ran using the umpv python wrapper. For example, if you try to pause umpv with `echo '{"command": ["cycle", "pause"]}' | socat - /tmp/mpvsocket`, it will result in an error similar to the following:

```
2025/05/07 22:49:15 socat[115919] E GOPEN: /tmp/mpvsocket: Connection refused
```

## Troubleshooting

#### Error, unknown format

If you get the following sort of error, note that MPV currently uses the small ffmpeg version (ffmpeg\_5) instead of the full version (ffmpeg\_5-full).

```
$ mpv --log-file=foo.log av://v4l2:/dev/video5
[lavf] Unknown lavf format v4l2
Failed to recognize file format.

Exiting... (Errors when loading file)
```

To address this problem, you can use the following package configuration for ffmpeg.

```
programs.mpv = {
  enable = true;

  package = (
    pkgs.mpv-unwrapped.wrapper {
      mpv = pkgs.mpv-unwrapped.override {
        ffmpeg = pkgs.ffmpeg-full;
      };
    }
  );
};
```

## References

1. [https://github.com/mpv-player/mpv/wiki](https://github.com/mpv-player/mpv/wiki)
2. [https://en.wikipedia.org/wiki/Mpv\_(media\_player)](https://en.wikipedia.org/wiki/Mpv_\(media_player\))
3. [https://search.nixos.org/packages?query=mpv](https://search.nixos.org/packages?query=mpv)
4. [https://home-manager-options.extranix.com/?query=mpv](https://home-manager-options.extranix.com/?query=mpv)
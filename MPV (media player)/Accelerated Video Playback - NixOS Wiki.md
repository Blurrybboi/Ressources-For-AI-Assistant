---
title: Accelerated Video Playback - NixOS Wiki
source: https://nixos.wiki/wiki/Accelerated_Video_Playback
author: 
published: 
created: 2025-06-16
description: 
tags:
  - clippings
---



This page is meant to help with techniques for getting accelerated video playback working in NixOS. This is generally done via libva and vaapi (and sometimes vdpau).

This is done by adding relevant `libva` -related packages to the `hardware.opengl.extraPackages` (or `hardware.graphics.extraPackages` on unstable) option.

Intel users should enable `intel-media-driver` if their CPU is on the [supported list](https://github.com/intel/media-driver?tab=readme-ov-file#supported-platforms) (Broadwell and newer). It can be used at runtime with `LIBVA_DRIVER_NAME=iHD mpv ...` for example, if you use Mic92's mpv settings below.

Other intel CPUs could enable the `intel-vaapi-driver`. This may have better results in some cases where the media driver doesn't work. However, this driver is unmaintained.

Additionally, the `intel-vaapi-driver` (previously `vaapiIntel`) package can be overridden to enable [Intel's Hybrid Driver](https://github.com/01org/intel-hybrid-driver).

  
Sample configuration:

```
{
  ...
  nixpkgs.config.packageOverrides = pkgs: {
    intel-vaapi-driver = pkgs.intel-vaapi-driver.override { enableHybridCodec = true; };
  };
  hardware.opengl = { # hardware.graphics since NixOS 24.11
    enable = true;
    extraPackages = with pkgs; [
      intel-media-driver # LIBVA_DRIVER_NAME=iHD
      intel-vaapi-driver # LIBVA_DRIVER_NAME=i965 (older but works better for Firefox/Chromium)
      libvdpau-va-gl
    ];
  };
  environment.sessionVariables = { LIBVA_DRIVER_NAME = "iHD"; }; # Force intel-media-driver
  ...
}
```

32 bit example:

```
hardware.opengl.extraPackages32 = with pkgs.pkgsi686Linux; [ intel-vaapi-driver ];
```

On unstable:

```
hardware.graphics.extraPackages32 = with pkgs.pkgsi686Linux; [ intel-vaapi-driver ];
```

## Prepared Hardware configuration

Sometimes different opengl packages are required to achieve full performance. You can check different configuration repositories for similar hardware configuration:

- [The NixOS-Hardware Repository](https://github.com/NixOS/nixos-hardware)

## Testing your configuration

You can test your configuration by running: `nix-shell -p libva-utils --run vainfo`

See [Hardware video acceleration: Verification (Arch Wiki)](https://wiki.archlinux.org/index.php/Hardware_video_acceleration#Verification) for more information.

## Applications

### Chromium

See [Chromium](https://nixos.wiki/wiki/Chromium#Enable_GPU_accelerated_video_decoding_.28VA-API.29).

### Firefox

See [Firefox#Hardware\_video\_acceleration (ArchWiki)](https://wiki.archlinux.org/index.php/Firefox#Hardware_video_acceleration).

### MPV

You can place the following configuration in `~/.config/mpv/mpv.conf` for mpv to use hardware acceleration for VP9 on Intel Broadwell (and probably later):

```
hwdec=auto-safe
vo=gpu
profile=gpu-hq
```

With Wayland, you need to nudge mpv to do the right thing:

```
gpu-context=wayland
```

This is based on the [Arch Linux mpv article](https://wiki.archlinux.org/title/mpv#Hardware_video_acceleration).

### Other

See the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Hardware_video_acceleration#Application_support).
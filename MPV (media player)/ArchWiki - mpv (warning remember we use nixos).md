---
title: "mpv - ArchWiki"
source: "https://wiki.archlinux.org/title/Mpv"
author:
published:
created: 2025-06-17
description:
tags:
  - "clippings"
---
[mpv](https://mpv.io/) is a media player based on [MPlayer](https://wiki.archlinux.org/title/MPlayer "MPlayer") and the now unmaintained *mplayer2*. It supports a wide variety of video file formats, audio and video codecs, and subtitle types. A detailed (although admittedly incomplete) list of differences between *mpv* and the aforementioned players can be found [here](https://github.com/mpv-player/mpv/blob/master/DOCS/mplayer-changes.rst).

## Installation

[Install](https://wiki.archlinux.org/title/Install "Install") the [mpv](https://archlinux.org/packages/?name=mpv) package or [mpv-git](https://aur.archlinux.org/packages/mpv-git/) <sup><small>AUR</small></sup> for the development version.

### Front ends

See [List of applications/Multimedia#mpv-based](https://wiki.archlinux.org/title/List_of_applications/Multimedia#mpv-based "List of applications/Multimedia").

## Configuration

*mpv* comes with good all-around defaults that should work well on computers with weaker/older video cards. However, if you have a computer with a more modern video card, *mpv* allows you to do a great deal of configuration to achieve better video quality (limited only by the power of your video card). To do this, one only needs to create a few configuration files (as they do not exist by default).

**Note:** Configuration files are read system-wide from `/etc/mpv/` and per-user from `~/.config/mpv/` (unless the [environment variable](https://wiki.archlinux.org/title/Environment_variable "Environment variable") `XDG_CONFIG_HOME` is set), where per-user settings override system-wide settings, all of which are overridden by the command line. User specific configuration is suggested since it may require some trial and error.

To help you get started, *mpv* provides sample configuration files with default settings. Copy them to use as a starting point:

```
$ cp -r /usr/share/doc/mpv/ ~/.config/
```

`mpv.conf` contains the majority of *mpv'* s settings, `input.conf` contains key bindings. Read through both of them to get an idea of how they work and what options are available.

### General settings

Add the following settings to `~/.config/mpv/mpv.conf`.

#### Subtitle configurations

Enable fuzzy searching:

```
sub-auto=fuzzy
```

Change font:

```
sub-font="fontName"
```

Bold the subtitles to increase readability:

```
sub-bold=yes
```

#### High quality configurations

By default, mpv utilizes settings that balance quality and performance. Additionally, two predefined profiles are available: `fast` for maximum performance and `high-quality` for superior rendering quality. You can apply a specific profile using the `--profile=*name*` option and inspect its contents using `--show-profile=*name*`.

```
profile=high-quality
```

Live statistics showing how well *mpv* is performing can be brought up with the `i` key. It is very useful for making sure that your hardware can keep up with your configuration and for comparing different configurations.

These last two options are a little more complicated. `video-sync=display-resample` makes it so that if audio and video go out of sync, then instead of dropping video frames, it will resample the audio (a slight change in audio pitch is often less noticeable than dropped frames). The mpv wiki has an in depth article on it titled [Display Synchronization](https://github.com/mpv-player/mpv/wiki/Display-synchronization). `interpolation` makes motion appear smoother on your display by changing the way that frames are shown so that the source framerate jives better with your display's refresh rate (not to be confused with SVP's technique which actually converts video to 60fps). The mpv wiki has an in depth article on it titled [Interpolation](https://github.com/mpv-player/mpv/wiki/Interpolation) though it is also commonly known as *smoothmotion*.

```
profile=high-quality
video-sync=display-resample
interpolation
```

**Note:** If [NVIDIA Optimus](https://wiki.archlinux.org/title/NVIDIA_Optimus "NVIDIA Optimus") is being used, the line `video-sync=display-resample` may cause video to be sped up. It also completely messes up frame pacing on some systems, seemingly preventing interpolation from working at all.

Beyond this, there is still a lot you can do, but things become more complicated, require more powerful video cards, and are in constant development. As a brief overview, it is possible to load special shaders that perform exotic scaling and sharpening techniques including some that actually use deep neural networks trained on images (for both real world and animated content). To learn more about this, take a look around the [mpv wiki](https://github.com/mpv-player/mpv/wiki), particularly the [user shader's section](https://github.com/mpv-player/mpv/wiki/User-Scripts#user-shaders).

There are also plenty of other options you may find desirable as well. It is worthwhile taking a look at [mpv(1)](https://man.archlinux.org/man/mpv.1). It is also helpful to run *mpv* from the command line to check for error messages about the config.

In `mpv.conf` it is possible to create *profiles* which are essentially just "groups of options" with which you can:

- Quickly switch between different configurations without having to rewrite the file.
- Create special profiles for special content.
- *nest* profiles so that you can make more complicated *profiles* out of simpler ones.

Creating a profile is easy. The area at the top of `mpv.conf` is called the top level, any options you write there will kick into effect once *mpv* is started. However, once you define a profile by writing its name in brackets, every option you write below it (until you define a new profile) is considered part of that profile. Here is an example `mpv.conf`:

```
profile=myprofile2        #Top level area, load myprofile2
ontop=yes                 #Always on top

[myprofile1]              #A simple profile, top level area ends here
profile-desc="a profile"  #Optional description for profile
fs=yes                    #Start in full screen

[myprofile2]              #Another simple profile
profile=high-quality      #A built in profile that comes with mpv
log-file=~~/log           #Sets a location for writing a log file, ~~/ translates to ~/.config/mpv
```

There are only two lines within the top level area and there are two separate profiles defined below it. When *mpv* starts, it sees the first line, loads the options in `myprofile2` (which means it loads the options in `high-quality` and `log-file=~~/log`) finally it loads `ontop=yes` and finishes starting up. Note, `myprofile1` is never loaded because it is never called in the top level area.

Alternatively, one could call *mpv* from the command line with:

```
$ mpv --profile=myprofile1 video.mkv
```

and it would ignore all options except the ones for `myprofile1`.

Certain types of profiles will be loaded automatically based on either the file extension or the protocol used.

These profiles will be loaded for all files with a matching file extension (for all *.mkv* and *.gif* files respectively):

```
[extension.mkv]
keep-open
volume-max=150

[extension.gif]
osc=no
loop-file
```

This profile will be loaded automatically whenever any http or https streams are played (e.g. `mpv https://example.com/video.mp4`):

```
[protocol.https]
speed=2
keep-open

[protocol.http]
profile=protocol.https
```

Run `mpv --list-protocols` to see the different protocols supported by mpv.

### Key bindings

Key bindings are fairly straightforward given the examples in `/usr/share/doc/mpv/input.conf` and [mpv(1) § COMMAND INTERFACE](https://man.archlinux.org/man/mpv.1#COMMAND_INTERFACE).

Add the following examples to `~/.config/mpv/input.conf`:

```
shift+s         screenshot each-frame
Shift+UP        seek  600
Shift+DOWN      seek -600
=               cycle video-unscaled
-               cycle-values window-scale 2 3 1 .5
WHEEL_UP        add volume 5
WHEEL_DOWN      add volume -5
WHEEL_LEFT      ignore
WHEEL_RIGHT     ignore
Alt+RIGHT       add video-rotate 90
Alt+LEFT        add video-rotate -90
Alt+-           add video-zoom -0.25
Alt+=           add video-zoom 0.25
Alt+j           add video-pan-x -0.05
Alt+l           add video-pan-x 0.05
Alt+i           add video-pan-y 0.05
Alt+k           add video-pan-y -0.05
Alt+BS          set video-zoom 0; set video-pan-x 0; set video-pan-y 0
```

For an attempt to reproduce MPC-HC key bindings in mpv, see [\[1\]](https://github.com/dragons4life/MPC-HC-config-for-MPV/blob/master/input.conf).

### Additional configuration files

In addition there are a few more configuration files and directories that can be created, among which:

- `~/.config/mpv/script-opts/osc.conf` manages the on Screen Controller. See [mpv(1) § ON SCREEN CONTROLLER](https://man.archlinux.org/man/mpv.1#ON_SCREEN_CONTROLLER) for more information.
- `~/.config/mpv/scripts/*script-name*.lua` for Lua scripts. See [\[2\]](https://github.com/mpv-player/mpv/issues/3500#issuecomment-305646994) for an example.

See [mpv(1) § FILES](https://man.archlinux.org/man/mpv.1#FILES) for information on other files and directories.

## Scripts

*mpv* has a [large variety of scripts](https://github.com/mpv-player/mpv/wiki/User-Scripts) that extend the functionality of the player. To this end, it has internal bindings for both Lua and JavaScript.

Scripts are typically installed by putting them in the `~/.config/mpv/scripts/` directory (you may have to create it first). After that they will be automatically loaded when mpv starts (this behavior can be altered with other *mpv* options). Some scripts come with their own installation and configuration instructions, so make sure to have a look. In addition some scripts are old, broken, and unmaintained.

### JavaScript

JavaScript (ES5 via [MuJS](https://mujs.com/)) has been supported as an mpv scripting language since 2014. Currently only [a few scripts](https://github.com/mpv-player/mpv/wiki/User-Scripts#javascript) are available, but documentation exists at [mpv(1) § JAVASCRIPT](https://man.archlinux.org/man/mpv.1#JAVASCRIPT) for anyone interested in making their own.

To get started, drop a script with a `.js` extension in the mpv `scripts` directory, e.g.:

```
~/.config/mpv/scripts/fullscreen-off-on-pause.js
```
```
function onPauseChange (prop, enabled) {
    if (enabled) {
        mp.set_property('fullscreen', 'no')
    }
}

mp.observe_property('pause', 'bool', onPauseChange)
```

For more details, e.g. on using `require` to load CommonJS modules, see [mpv(1) § CommonJS modules and require(id)](https://man.archlinux.org/man/mpv.1#CommonJS_modules_and_require\(id\)).

JavaScript support is available in the [mpv](https://archlinux.org/packages/?name=mpv) package, as well as some AUR packages, e.g. [mpv-full](https://aur.archlinux.org/packages/mpv-full/) <sup><small>AUR</small></sup> and [mpv-full-git](https://aur.archlinux.org/packages/mpv-full-git/) <sup><small>AUR</small></sup>.

### Lua

The development of *mpv'* s Lua scripts is documented in [mpv(1) § LUA SCRIPTING](https://man.archlinux.org/man/mpv.1#LUA_SCRIPTING) with examples in [TOOLS/lua](https://github.com/mpv-player/mpv/tree/master/TOOLS/lua), which are installed to `/usr/share/mpv/scripts`.

For example, you can enable the builtin script to automatically crop videos with black bars:

```
$ ln -s /usr/share/mpv/scripts/autocrop.lua ~/.config/mpv/scripts
```

#### mpv-ytdlAutoFormat

[mpv-ytdlautoformat](https://github.com/Samillion/mpv-ytdlautoformat) is a Lua script to auto change ytdl-format for Youtube and Twitch or the domains you desire, to 480p or the quality you desire.

#### mpv-webm

[mpv-webm](https://github.com/ekisu/mpv-webm) (or simply *webm*) is a very easy to use Lua script that allows one to create WebM files while watching videos. It includes several features and does not have any extra dependencies (relies entirely on mpv).

#### ytdl-preload

[ytdl-preload](https://gist.github.com/bitingsock/17d90e3deeb35b5f75e55adb19098f58) is a Lua script to preload the next ytdl-link in your playlist.

**Note:** The script is still in active developing process.

### C

#### mpv-mpris

The C plugin [mpv-mpris](https://github.com/hoyon/mpv-mpris) allows other applications to integrate with *mpv* via the [MPRIS](https://wiki.archlinux.org/title/MPRIS "MPRIS") protocol. For example, with *mpv-mpris* installed, [kdeconnect](https://archlinux.org/packages/?name=kdeconnect) can automatically pause video playback in *mpv* when a phone call arrives. Another example is buttons (play\\pause etc) on bluetooth audio-devices.

To use the plugin, install [mpv-mpris](https://archlinux.org/packages/?name=mpv-mpris).

## Vapoursynth

Vapoursynth is an alternative to AviSynth that can be used on Linux and allows for Video manipulation via python scripts. Vapoursynths python scripts can be used as video filters for *mpv*.

The [mpv](https://archlinux.org/packages/?name=mpv) package now enables Vapoursynth support by default.

### SVP 4 Linux (SmoothVideoProject)

[SmoothVideoProject SVP](https://www.svp-team.com/wiki/Main_Page) is a program that is primarily known for converting video to 60fps. It is free \[as in beer\] and full featured for 64bit Linux (costs money for Windows and OS X and is incompatible with 32bit Linux).

It has three main features and each one can be disabled/enabled as one chooses (you are not forced to use motion interpolation).

1. [Motion interpolation](https://www.svp-team.com/wiki/Manual:FRC) ([youtube video](https://www.youtube.com/watch?v=Wjb6CSe4708)) - An algorithm that converts video to 60fps. This creates the somewhat controversial "soap opera effect" that some people love and others hate. Unfortunately, the algorithm is not perfect and it also introduces more than its share of weird artifacts. The algorithm can be tuned (via a slider) for either performance or quality. It also has some artifact reduction settings that interpolate actual frames with the generated frames reducing the noticeability of the artifacts. The framerate detection can be set to automatic or manual (manual seems to resolve performance issues for some users).
2. [Black bar lighting](https://www.svp-team.com/wiki/Manual:Outer_lighting) ([youtube video](https://www.youtube.com/watch?v=yTzTpW3kTBE)) - If the image has an aspect ratio that produces black bars on your display, SVP will illuminate the black bars with "lights" generated by the content on the screen. It has some amount of customization, but the defaults are pretty close to optimal.
3. [LED ambient lighting control](https://www.svp-team.com/wiki/Manual:SVPlight) ([youtube video](https://www.youtube.com/watch?v=UUM2n-8kIJ8)) - Has the ability to control LED ambient lighting attached to your television.

Once you have *mpv* compiled with Vapoursynth support, it is fairly easy to get SVP working with *mpv*. Simply install [svp-bin](https://aur.archlinux.org/packages/svp-bin/) <sup><small>AUR</small></sup>, open the SVP program to let it assess your system performance (you may want to close other programs first so that it gets an accurate reading), and finally add the following *mpv* profile to your mpv.conf [\[3\]](https://www.svp-team.com/wiki/SVP:mpv):

```
mpv.conf
```
```
[svp]
input-ipc-server=/tmp/mpvsocket     # Receives input from SVP
hr-seek-framedrop=no                # Fixes audio desync
watch-later-options-remove=vf       # Do not remember SVP's video filters

# Can fix stuttering in some cases, in other cases probably causes it. Try it if you experience stuttering.
#opengl-early-flush=yes
```

Then, in order to use SVP, you must have the SVP program running in the background before opening the file using *mpv* with that profile. Either do:

```
$ mpv --profile=svp video.mkv
```

or set `profile=svp` in the top-level portion of the *mpv* [configuration](https://wiki.archlinux.org/title/#Custom_profiles).

If you want to use hardware decoding, you must use a copy-back decoder since normal decoders are not compatible with Vapoursynth (choose a `hwdec` option that ends in `-copy`). For instance:

```
hwdec=auto-copy
hwdec-codecs=all
```

Either way, hardware decoding is discouraged by *mpv* developers and is not likely to make a significant difference in performance.

## Tips and Tricks

### Picture

#### Hardware video acceleration

See [Hardware video acceleration](https://wiki.archlinux.org/title/Hardware_video_acceleration "Hardware video acceleration").

Hardware accelerated video decoding is available via the `--hwdec=*API*` option. For a list of all supported APIs and other required options, see [mpv(1) § hwdec](https://man.archlinux.org/man/mpv.1#hwdec=_api1,api2,..._no_auto_auto).

To make it permanent (for example when playing videos from a desktop environment), add it to the configuration file:

```
~/.config/mpv/mpv.conf
```
```
hwdec=auto
```

To allow CPU processing with video filters, choose a `*-copy` API.

Use the keyboard shortcut `Ctrl+h` while a video is running to toggle hardware decoding.

To troubleshoot hardware acceleration, adjusting the logging levels (see [mpv(1) § msg-level](https://man.archlinux.org/man/mpv.1#msg-level)) may be necessary. For instance, `--msg-level=vd=v,vo=v,vo/gpu/vaapi-egl=trace` enables the following:

- *Verbose* messages from the video decoder (`vd`) and video output (`vo`) modules.
- Even more detailed *trace* messages for the module responsible for video decoding. Here, after running mpv once without any log levels adjusted, the module of interest was empirically determined to be `vo/gpu/vaapi-egl`.

#### Quickly cycle between aspect ratios

You can cycle between aspect ratios using `Shift+a`.

#### Ignoring aspect ratio

You can ignore the aspect ratio using `--keepaspect=*no*`. To make the option permanent, add the line `keepaspect=*no*` to the configuration file.

#### Draw to the root window

Run *mpv* with `--wid=0`. *mpv* will draw to the window with a window ID of 0.

#### Always show the application window

To show the application window even for audio files when launching mpv from the command line, use the `--force-window` option. To make the option permanent, add the line `force-window=yes` to the configuration file.

#### Disable video output

To disable video output when launching from command line, use the `--vid=no` option, or its alias, `--no-video`.

#### Terminal video

- `--vo=tct` "Color Unicode art video output driver that works on a text console."
- `--vo=caca` "Color ASCII art video output driver that works on a text console." [libcaca](https://archlinux.org/packages/?name=libcaca) support has been disabled on Arch due to vulnerabilities (see [FS#70962](https://bugs.archlinux.org/task/70962)) and has not been added back in as its upstream is inactive: install [mpv-full](https://aur.archlinux.org/packages/mpv-full/) <sup><small>AUR</small></sup>.

### Audio

#### Volume is too low

Set `volume-max=*value*` in your configuration file to a reasonable amount, such as `volume-max=150`, which then allows you to increase your volume up to 150%, which is more than twice as loud. Increasing your volume too high will result in clipping artefacts. Additionally (or alternatively), you can utilize [dynamic range compression](https://en.wikipedia.org/wiki/Dynamic_range_compression "wikipedia:Dynamic range compression") with `af=acompressor`.

#### Specify an audio output

Run the following command to get a list of available audio output devices

```
$ mpv --audio-device=help
```

Then add one to `~/.config/mpv/mpv.conf`. For example:

```
audio-device=alsa/hdmi:CARD=NVidia,DEV=1
```

#### HD Audio passthrough

To enable HD audio codecs like TrueHD and DTS-MA to passthrough to an AV receiver, add the following to `~/.config/mpv/mpv.conf`

```
audio-spdif=ac3,eac3,dts-hd,truehd
```

#### Volume normalization

Different sources may have different or inconsistent loudness, so *mpv* users may need to configure automatic volume normalization. For example:

```
~/.config/mpv/input.conf
```
```
n cycle_values af loudnorm=I=-30 loudnorm=I=-15 anull
```

This binds the key `n` to cycle the audio filter settings (`af`) through the specified values:

- `loudnorm=I=-30`: loudnorm setting with `I=-30`, soft volume, might be suitable for background music
- `loudnorm=I=-15`: louder volume, might be good for the video currently in view
- `anull`: reset audio filter to null, i.e., disable the audio filter

**Note:** Binding a key does not change the default audio filter. To change the default, add e.g. `af=loudnorm=I=-30` to the main configuration file.

Audio filtering in *mpv* is provided by the [FFmpeg](https://wiki.archlinux.org/title/FFmpeg "FFmpeg") backend. See [Wikipedia:EBU R 128](https://en.wikipedia.org/wiki/EBU_R_128 "wikipedia:EBU R 128") and [ffmpeg loudnorm filter](https://ffmpeg.org/ffmpeg-filters.html#loudnorm) for details.

See also upstream issues [\[5\]](https://github.com/mpv-player/mpv/issues/3979) and [\[6\]](https://github.com/mpv-player/mpv/issues/2883) which mention different options.

#### Improving mpv as a music player with Lua scripts

[This blog post](https://web.archive.org/web/20160320001546/http://bamos.github.io/2014/07/05/mpv-lua-scripting/) introduces the [music.lua](https://github.com/bamos/dotfiles/blob/master/.mpv/scripts.old/music.lua) script, which shows how Lua scripts can be used to improve *mpv* as a music player.

### Save position on quit

By default, you can save the position and quit by pressing `Shift+q`. The shortcut can be changed by setting `quit_watch_later` in the key bindings configuration file.

To automatically save the current playback position on quit, start *mpv* with `--save-position-on-quit`, or add `save-position-on-quit` to the configuration file.

#### Save position of a playlist and pause on next file

A playlist could simply be a list of files, see [mpv(1) § playlist](https://man.archlinux.org/man/mpv.1#playlist=_filename_). To play a playlist and remember its position:

```
$ mpv --save-position-on-quit --pause --reset-on-next-file=pause --playlist=/path/to/playlist
```

With the option `--pause` *mpv* will start in paused state and `--reset-on-next-file=pause` will reset the pause mode when switching to the next file.

### Play a DVD

mpv does not support DVD menus. To start the main stream with the longest title of a video DVD, use the command:

```
$ mpv dvd://
```

An optional title specifier is a number (starting at 0) which selects between separate video streams on the DVD:

```
$ mpv dvd://[title]
```

DVDs which have been copied on to a local file system (by e.g. the [dvdbackup](https://wiki.archlinux.org/title/Dvdbackup "Dvdbackup") tool) are accommodated by specifying the path to the local copy: `--dvd-device=*PATH*`.

See the following [desktop file](https://wiki.archlinux.org/title/Desktop_file "Desktop file") example for playing DVDs from a local file system:

```
[Desktop Entry]
Type=Application
Name=mpv Media Player DVD 
GenericName=Multimedia player
Comment=Play movies and songs
Icon=mpv
Exec=mpv dvd:// --player-operation-mode=pseudo-gui --force-window --idle --dvd-device=%f
Terminal=false
Categories=AudioVideo;Audio;Video;Player;TV;
# (MimeType and X-KDE-Protocols omitted, see original mpv.desktop file)
```

By replacing the Exec line with

```
Exec=mpv dvd://0 dvd://1 dvd://2 dvd://3 dvd://4 dvd://5 dvd://6 dvd://7 dvd://8 dvd://9  --player-operation-mode=pseudo-gui --force-window --idle --dvd-device=%f
```

the mpv player will queue DVD title 0 to 9 in the playlist, which allows the user to play the titles consecutively or jump forward and backward in the DVD titles with the mpv GUI.

Install [libdvdcss](https://archlinux.org/packages/?name=libdvdcss), to fix the error:

```
[dvdnav] Error getting next block from DVD 1 (Error reading from DVD.)
```

### Restoring old OSC

Since version 0.21.0, *mpv* has replaced the on-screen controls by a bottombar. In case you want on-screen controls back, you can edit the *mpv* configuration [as described here](https://github.com/mpv-player/mpv/wiki/FAQ#i-want-the-old-osc-back).

### Reproducible screenshots

The screenshot template option can include the precise timecode (HH:MM:SS.mmm) of the screenshoted frame. The meaningful filename makes it easy to know the origin of the screenshot. It can be set like this:

```
~/.config/mpv/mpv.conf
```
```
screenshot-template="%F - [%P] (%#01n)"
```

This expands to `*filename* - [HH:MM:SS.mmm] (*number*).jpg`. Example result:

```
Gunsmith Cats/
├── Gunsmith Cats Ep. 01 - [00:00:50.217] (1).jpg
├── Gunsmith Cats Ep. 01 - [00:22:55.874] (1).jpg
├── Gunsmith Cats Ep. 01 - [00:22:55.874] (2).jpg
└── Gunsmith Cats Ep. 02 - [00:15:05.778] (1).jpg
```

A bonus is it sorts nicely because alphabetically, the timecode is sorted within the episode number.

See [mpv(1) § screenshot-template](https://man.archlinux.org/man/mpv.1#screenshot-template) for more information.

### Creating a single screenshot

An example of creating a single screenshot, by using a start time (`HH:MM:SS`):

```
$ mpv --no-audio --start=00:01:30 --frames=1 /path/to/video/file --o=/path/to/screenshot.png
```

Screenshots will be saved in /path/to/screenshot.png.

### Streaming

#### Twitch.tv streaming over mpv

If [yt-dlp](https://wiki.archlinux.org/title/Yt-dlp "Yt-dlp") or [youtube-dl](https://aur.archlinux.org/packages/youtube-dl/) <sup><small>AUR</small></sup> is installed, *mpv* can directly open a Twitch livestream.

Alternatively, see [Streamlink#Twitch](https://wiki.archlinux.org/title/Streamlink#Twitch "Streamlink").

Another alternative based on Livestreamer is this Lua script: [https://gist.github.com/ChrisK2/8701184fe3ea7701c9cc](https://gist.github.com/ChrisK2/8701184fe3ea7701c9cc)

#### youtube-dl and choosing formats

The default `--ytdl-format` is `bestvideo+bestaudio/best`. For youtube videos that have 4K resolutions available, this may mean that your device will struggle to decode 4K VP9 encoded video in software even if the attached monitor is much lower resolution.

Setting the right youtube-dl format selectors can fix this easily though. In the following configuration example, only videos with a vertical resolution of 1080 pixels or less will be considered.

```
ytdl-format="bestvideo[height<=?1080]+bestaudio/best"
```

If you wish to avoid a certain codec altogether because you cannot hardware-decode it, you can add this to the format selector. For example, we can additionally choose to ignore VP9 as follows:

```
ytdl-format="bestvideo[height<=?1080][vcodec!~='vp0?9']+bestaudio/best"
```

If you prefer best quality open codecs (VP9 and Opus), use:

```
ytdl-format="((bestvideo[vcodec^=vp9]/bestvideo)+(bestaudio[acodec=opus]/bestaudio[acodec=vorbis]/bestaudio[acodec=aac]/bestaudio))/best"
```

To find and stream audio from your terminal emulator with `yta *search terms*`, put the following function in your `.bashrc`:

```
function yta() {
    mpv --ytdl-format=bestaudio ytdl://ytsearch:"$*"
}
```

### System integration

#### Opening video links from the KDE clipboard

If [youtube-dl](https://aur.archlinux.org/packages/youtube-dl/) <sup><small>AUR</small></sup> or [yt-dlp](https://archlinux.org/packages/?name=yt-dlp) is installed and [KDE Plasma](https://wiki.archlinux.org/title/KDE_Plasma "KDE Plasma") is being used, it is possible to create a custom action in the KDE clipboard to conveniently play links from video sharing sites.

1. Open the clipboard configuration menu (typically by right-clicking its icon in the system tray) and go to the *Actions* tab.
2. Click *Add Action* then enter a regular expression to detect the sites you would like to play video from (e.g. `^http.+(youtu|twitch)` to detect YouTube and Twitch URLs).
3. Click *Add Command*, under *Command* enter `mpv %s` and under *Description* enter `mpv`.

Now, you can play video links from your clipboard in *mpv* by pressing `Ctrl+Alt+r` and selecting *mpv* from the context menu. You may need to go to *Advanced Settings* and remove Firefox from the section *Disable Actions for Windows of Type WM\_CLASS*.

## Troubleshooting

### General debugging

If you are having trouble with *mpv'* s playback (or if it is flat out failing to run) then the first three things you should do are:

1. Run *mpv* from the command line (the -v flag increases verbosity). If you are lucky there will be an error message there telling you what is wrong.  
	`$ mpv -v video.mkv`
2. Have *mpv* output a log file. The log file might be difficult to sift through but if something is broken you might see it there.  
	`$ mpv -v --log-file=./log video.mkv`
3. Run *mpv* without a configuration. If this runs well then the problem is somewhere in your configuration (perhaps your hardware cannot keep up with your settings).  
	`$ mpv --no-config video.mkv`

If *mpv* runs but it just does not run well then a fourth thing that might be worth taking a look at is the live statistics (with `i`) to see exactly how it is performing.

### Fix jerky playback and tearing

*mpv* defaults to using the OpenGL video output device setting on hardware that supports it. In cases such as trying to play video back on a 4K display using an Intel HD4XXX series card or similar, you will find video playback unreliable, jerky to the point of stopping entirely at times and with major tearing when using any OpenGL output setting. If you experience any of these issues, using the XV ([Xorg](https://wiki.archlinux.org/title/Xorg "Xorg") only) video output device may help:

```
~/.config/mpv/mpv.conf
```
```
vo=xv
```

**Note:** This is the most compatible VO on X, but may be low-quality, and has issues with OSD and subtitle display.

It is possible to increase playback performance even more (especially on lower hardware), but this decreases the video quality dramatically in most cases.

The following [options](https://wiki.archlinux.org/title/#Configuration) may be considered to increase the video playback performance:

```
~/.config/mpv/mpv.conf
```
```
vd-lavc-fast
vd-lavc-skiploopfilter=skipvalue
vd-lavc-skipframe=skipvalue
vd-lavc-framedrop=skipvalue
vd-lavc-threads=threads
```

### Problems with window compositors

As described in [mpv(1) § Window](https://man.archlinux.org/man/mpv.1#Window), mpv by default disables any active window [compositor](https://wiki.archlinux.org/title/Xorg#Composite "Xorg") while in fullscreen mode. This is done to prevent potential performance issues during playback.

For window compositors such as KWin or Mutter, it can be advantageous to disable window compositing even while in windowed mode. This can be achieved by using setting the `x11-bypass-compositor=yes` option.

There are two disadvantages to disabling compositing:

- Re-enabling compositing may introduce stutter for a period of time, particularly if using KWin compositing.
- Any effects provided by compositing will be temporarily unavailable (until mpv re-enables it), which in [Plasma](https://wiki.archlinux.org/title/Plasma "Plasma") prevents the default app switcher from working.

To sidestep these issues, you can try keeping your compositor enabled with `x11-bypass-compositor=no`

### No volume bar, cannot change volume

Spin the mouse wheel over the volume icon.

### GNOME Blank screen (Wayland)

*mpv* may not suspend GNOME's Power Saving Settings if using Wayland resulting in screen saver turning off the monitor during video playback. A workaround is to add `gnome-session-inhibit` to the beginning of the `Exec=` line in `mpv.desktop`.

In order to inhibit the screensaver only during playback, use [mpv\_inhibit\_gnome](https://aur.archlinux.org/packages/mpv_inhibit_gnome/) <sup><small>AUR</small></sup>. Alternatively, a [mpv lua script](https://gist.github.com/crazygolem/a7d3a2d3c0cee5d072c0cbbbdee69286) based on `gnome-session-inhibit` may be used.

**Tip:** The `io.mpv.Mpv` flatpak app already includes the [mpv\_inhibit\_gnome](https://github.com/Guldoman/mpv_inhibit_gnome) plugin.

### Cursor theme not respected under GNOME Wayland

See [GNOME/Troubleshooting#Cursor size or theme issues on Wayland](https://wiki.archlinux.org/title/GNOME/Troubleshooting#Cursor_size_or_theme_issues_on_Wayland "GNOME/Troubleshooting").

### Error message about missing CUDA libraries on AMD GPUs

While using VAAPI hardware acceleration on AMD GPUs on versions and older, you may see a persistent error message saying `Cannot load libcuda.so.1`. This can be suppressed by setting `gpu-hwdec-interop=vaapi`.

Related bug reports: [Github issue #9691](https://github.com/mpv-player/mpv/issues/9691), [Github issue #8765](https://github.com/mpv-player/mpv/issues/8765)

This issue has been fixed upstream in [pull request #9842](https://github.com/mpv-player/mpv/pull/9842).

### Unable to play audio if PipeWire is masked

If *mpv* crashes or fails to play audio on systems where [PipeWire](https://wiki.archlinux.org/title/PipeWire "PipeWire") is [masked](https://wiki.archlinux.org/title/Mask "Mask"), reporting no outputs or broken pipe, set the `--ao` option to match your environment. Set it in `mpv.conf` for persistent configuration.

### mpv will not start playing a DVD from file

If *mpv* will not play a DVD from file in plain VIDEO\_TS/VOB structure, there could be a problem with the restore playback position function. Try either cleaning `.config/mpv/watch_later` folder, or start *mpv* with the `no-resume-playback` option and/or set the `save-position-on-quit=no` option.

### Fix stuttering after resuming playback from pause

If video is stuttering with [PulseAudio](https://wiki.archlinux.org/title/PulseAudio "PulseAudio"), try the `pulse-latency-hacks` option discussed at [mpv(1) § --pulse-latency-hacks](https://man.archlinux.org/man/mpv.1#pulse~4):

```
~/.config/mpv/mpv.conf
```
```
pulse-latency-hacks=yes
```
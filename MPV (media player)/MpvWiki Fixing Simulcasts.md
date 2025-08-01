---
title: "Fixing Simulcasts"
source: "https://github.com/mpv-player/mpv/wiki/Fixing-Simulcasts"
author:
  - "[[GitHub]]"
published:
created: 2025-06-17
description: "🎥 Command line media player. Contribute to mpv-player/mpv development by creating an account on GitHub."
tags:
  - "clippings"
---
## Motivation

Due to massive incompetence, time and resource constraints simulcasts often suffer from various quality degrading issues. This document gives a summary of frequent issues and how to fix some of those as best as possible during playback with mpv's means.

## Video

### Banding

The only consistently occurring problem these days is banding, which can now be fixed using a simple integrated shader.

- To use the debanding shader, use the opengl-hq profile in your `mpv.conf` like so:
	```
	profile=opengl-hq
	```
- If you wish to have a keybind (in this example, `b`) to disable the debanding shader, add the following to your `input.conf`:
	```
	b cycle deband
	```

### Wrong Framerate

Some simulcast encoders are so incompetent that they can't even get the frame-rate right and end up encoding a 24fps video at 30fps which will lead to annoying judder (Frame pattern: ABCDD).

To fix this: `--vf=lavfi=[fps=30000/1001,decimate,fps=24000/1001]`

Sometimes something seems to go wrong with the decimation mid-show and a show that is encoded at 24fps and playing smoothly at first suddenly starts to judder. For whatever reason, a frame that wasn't a dupe got removed, and the frame that actually is a dupe remains. This means a whole frame of motion is lost and pans get very jerky (Frame pattern: ABDD). Due to a frame actually getting lost, this is pretty much impossible to fix.

(Obsolete as of Summer 2015 as HorribleSubs fixes this during ripping)

Rips from Funimation are encoded at full-range but are tagged as limited range. As a result the player will "cut off" a lot of important image information. Add the command-line option `--vf-add=format=colorlevels=full` to correct this at startup or add `<key> vf toggle format=colorlevels=full` to your input.conf to toggle the setting during playback.

## Subtitles

### Timing

The subtitles are sometimes a few frames out of sync, causing scene bleeds all over the place. Use `--sub-delay=0.125125` to apply the fix at startup or add `<key> cycle_values sub-delay "0.125125" "0"` to your input.conf to toggle it during playback.

This is caused in particular by Crunchyroll’s broken stream muxing, which sometimes drops the first frame and then delays the video stream by two frames (rounded to milliseconds), hence delaying the subtitles by `(1 / FPS) * 3` usually fixes the issue (the value above assumes 23.976 FPS video).

### Distorted signs/typesetting

Use `--sub-ass-vsfilter-blur-compat=no`.

(Note: This was apparently a one-time issue only)

When "é" shows up as "Ã©", or similar, the script's character-encoding is messed up (First spotted in SAO2 Ep 03 by "Daisuki"). This can sadly not be fixed during playback, here's what you need to do:

- Demux the script using: `mkvextract tracks <file.mkv> <sid>:<file.ass>`
- Get an editor that can convert between character-encodings (Sublime Text)
- Open the script as UTF-8
- Save the script as "Windows 1252" or something like that
- Open it as UTF-8 again. It should now look correctly.
- If your movie is named `file.mkv`, save the fixed script as `file.ass` and put it in the same folder as `file.mkv`, mpv will pick it up and show it automatically.
- (Optionally: Mux your fixed script back into the mkv file)
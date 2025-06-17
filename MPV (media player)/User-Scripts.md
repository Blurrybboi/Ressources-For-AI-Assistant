# User Scripts

Here is a list of scripts that users of mpv have published, adding functionality that is not part of the core mpv player.
Most of these scripts are **unofficial 3rd party scripts**. Anyone can add their own script by editing this wiki. On GitHub mpv scripts are tagged as [mpv-script](https://github.com/topics/mpv-script).

Scripts are usually placed in:
| OS | Location |
| --- | --- |
| GNU/Linux or macOS | `~/.config/mpv/scripts/` |
| Windows | `C:/Users/Username/AppData/Roaming/mpv/scripts/` |

## Lists of mpv scripts

* **[Awesome-mpv](https://github.com/stax76/awesome-mpv)**  
  Categorized list, updated 1-2 times per year.

## JavaScript

* **[Auto Load Fonts](https://github.com/Hill-98/mpv-config/blob/main/scripts/auto-load-fonts.js)**  
  Auto load the font files in the fonts folder under the play file path.

* **[copyTime](https://github.com/Arieleg/mpv-copyTime)**  
  Get the current time of the video and copy it to the clipboard with the format HH:MM:SS.MS .

* **[gallery-dl-view](https://github.com/noctuid/gallery-dl-view)**  
  Load image galleries directly in mpv like gallery-dl_hook but with extra functionality like binding a key to download images, optionally only loading images that are new since the gallery was last opened, and more.

* **[mpv-assrt](https://github.com/AssrtOSS/mpv-assrt)**  
  Download subtitles from [assrt.net](http://assrt.net), with interactive OSD menu.

* **[mpv-chapters](https://github.com/zxhzxhz/mpv-chapters)**  
  Display chapters and allow you to jump to them with a mouse click. ([Preview](https://i.imgur.com/f7WtKYN.png))

* **[mpvDLNA](https://github.com/chachmu/mpvDLNA)**  
  A plugin to allow mpv to browse and watch content hosted on DLNA servers. Also supports sending wake on lan packets by MAC Address.

* **[mpv-javascript-http (for developers)](https://github.com/Hill-98/mpv-javascript-http)**  
  Http client for mpv javascript scripts (based on curl)

* **[mpv-remote-node](https://github.com/husudosu/mpv-remote-node)**  
  Hosts a Node.js server, which then can be used to control mpv remotely from an [Android app](https://github.com/husudosu/mpv-remote-app).

* **[mpvcontextmenu](https://gitlab.com/carmanaught/mpvcontextmenu)**  
  Comprehensive context-menu forked from [Tcl/Tk context menu](https://gist.github.com/avih/bee746200b5712220b8bd2f230e535de). Uses other scripts (see Requirements).

* **[mpvselectmenu](https://gitlab.com/carmanaught/mpvselectmenu)**  
  Context-menu inspired by `select.lua` utilising mpv's `input` and `console` script functionality. Uses other scripts (see Requirements).

* **[mute-on-specifc-subtitle-words](https://github.com/jtaala/mpv-mute-on-specific-subtitle-words)**  
  Mutes & hides subtitles that contain specified words (can be user defined). Restores previous volume and subtitle visibility when the subtitle that contained specified word(s) finishes.  Uses _word boundary_ `regex` matching to minimise false positive matches.

* **[PureMPV](https://github.com/4ndrs/PureMPV)**  
  Get the file path, timestamps, and cropping coordinates, for ffmpeg, all from within mpv with just one copy.

* **[screenshot-mosaic](https://github.com/noaione/mpv-js-scripts)**
  Create a mosaic of an images like what MPC-HC does.
  ([Preview](https://user-images.githubusercontent.com/93109835/223640160-c57b5358-2a3c-4586-aff5-d2ef5417f94b.png))

* **[screenshot-to-clipboard](https://github.com/zc62/mpv-scripts/blob/master/screenshot-to-clipboard.js)**  
  Generates a temp screenshot file on desktop then copy to clipboard. (Windows only)

* **[seek-show-position-v2](https://github.com/someonelike-u/mpv.net/blob/master/src/Scripts/JavaScript/seek-show-position.js)**  
  Shows the position and duration when seeking formatted as 01:10:00 / 01:20:00.

* **[btime](https://github.com/butterw/bShaders/blob/master/mpv/settings/scripts/btime.js)**  
  Shows a shorter time format when seeking: 0:15 / 3:10, 08:20 / 55:00, 0:00:05 / 1:30:14. Now configurable with format=mpc-hc or youtube.

* **[bstat](https://github.com/butterw/bShaders/blob/master/mpv/settings/scripts/bstat.js)**  
  Calculates new user-data properties (req mpv v0.36) including avg-bitrate, rounded file-size, exact aspect ratio, etc. Output to terminal or OSD. Updates when a new file is loaded or on demand.

* **[store-shaders](https://github.com/butterw/bShaders/blob/master/mpv/settings/scripts/store-shaders.js)**  
  Store current glsl-shaders config on first run, this config will then be restored by subsequent calls.

* **[switch-shader](https://github.com/butterw/bShaders/blob/master/mpv/settings/scripts/switch-shader.js)**  
  Provide a switch to disable/restore shaders and vf filters.

* **[takeSsSequence](https://github.com/Arieleg/mpv-takeSsSequence)**  
  Take a sequence of equispaced screenshots.

* **[toggle-shuffle](https://github.com/NaiveInvestigator/toggle-shuffle)**  
  This simple mpv script allows you to toggle shuffle on/off during playback.

* **[webtorrent-mpv-hook](https://github.com/mrxdst/webtorrent-mpv-hook)**  
  Adds a hook that allows mpv to stream torrents. It also provides a osd overlay to show info/progress.

* **[writeedits](https://github.com/paradox460/mpv-scripts/tree/master/writeedits)**  
  Writes a selection of filters (crop, rotate, flip, delogo, start/end loop time) to a file for later batch processing with ffmpeg.

* **npm packages (for developers)** **[by tag](https://www.npmjs.com/search?q=keywords:mpv-script)**
  * **[@types/mpv-script](https://www.npmjs.com/package/@types/mpv-script)**  
    TypeScript definitions for builtin `mp` modules and globals.

  * **[mpv.d.ts](https://www.npmjs.com/package/mpv.d.ts)**  
    Another TypeScript definitions for mpv JavaScript API.

  * **[mpv-promise](https://www.npmjs.com/package/mpv-promise)**  
    Promise polyfill for mpv JavaScript runtime.

  * **[mpv-assdraw](https://www.npmjs.com/package/mpv-assdraw)**  
    mpv assdraw module for JavaScript.

* **VideoPlayerCode scripts** (see Install-Notes below)

  * **[Blackbox](https://github.com/VideoPlayerCode/mpv-tools/)** - Advanced,
    modular media browser, file manager and playlist manager for mpv.

  * **[Colorbox](https://github.com/VideoPlayerCode/mpv-tools/)** - Apply color
    correction presets.

  * **[Gallerizer](https://github.com/VideoPlayerCode/mpv-tools/)** - Image
    gallery autoloader for mpv.

  * **[Leapfrog](https://github.com/VideoPlayerCode/mpv-tools/)** - Effortlessly
    jump through your playlist, with your own custom jump size and direction,
    including the ability to jump randomly. Excellent when queuing lots of
    images and using mpv as an image viewer.
  
  * **[JS Modules for developers](https://github.com/VideoPlayerCode/mpv-tools/tree/master/scripts/modules.js)** -
    Tons of pre-written, open source JavaScript modules which helps you
    rapidly create your own JS user scripts (including a very helpful
    [script config](https://github.com/VideoPlayerCode/mpv-tools/blob/master/scripts/modules.js/Options.js)
    system based on mpv's Lua `mp.options` API). All modules are free to use
    (and extend) in your own scripts!

  **VideoPlayerCode Install-Notes**

    * The VideoPlayerCode scripts and modules use options at the dir
      ``~~/script-settings/`` (instead of the standard ``~~/script-opts/`` which
      is used by the builtin ``mp.options.read_options``).
  
    * The original installation instructions for the scripts are outdated. To
      install one of the VideoPlayerCode scripts, e.g. ``Blackbox.js``, do the
      following:
      * Inside your ``scripts`` dir create a dir ``Blackbox``, and into it copy
        the file ``Blackbox.js`` from the original distribution, as well as the
        directory ``modules.js`` (with all the files it contains).
      * Inside the ``Blackbox`` dir: rename the file ``Blackbox.js`` to
        ``main.js``, and rename the dir ``modules.js`` to ``modules``.
* **[mpv-easy](https://github.com/mpv-easy/mpv-easy)**  
  TS and React toolkit for mpv script. https://github.com/mpv-easy/mpsm-scripts.

* **[mpsm](https://github.com/mpv-easy/mpv-easy/tree/main/mpv-mpsm)**  
  mpsm is a mpv script manager, you can install scripts provided by [mpsm-scripts](https://github.com/mpv-easy/mpsm-scripts), or install any script with added [meta info](https://github.com/mpv-easy/mpsm-scripts?tab=readme-ov-file#meta-info) via url.

## Lua Scripts

If you want to write your own Lua scripts, have a look at the [documentation of mpv's Lua interface](https://mpv.io/manual/master/#lua-scripting).

* **[abs-screenshot](https://github.com/Thann/mpv-abs-screenshot/blob/master/abs-screenshot.lua)**  
  Uses Exiftool to get the "Date/Time Original" and saves a screenshot with the name being the actual time the video was taken.

* **[acompressor](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/acompressor.lua)**  
  Dynamic range compressor using acompressor ffmpeg filter with controls to dynamically adjust parameters.

* **[adevice-list](https://github.com/dyphire/mpv-scripts/blob/main/adevice-list.lua)**  
  Interractive audio-device list menu.

* **[afilter](https://github.com/he2a/mpv-scripts)**  
  Script for easy access to certain audio compressors and HRTF sofalizer in mpv with option to whitelist filters based on type of media. Settings are located in afilter.conf in ./script-opts folder and the SOFA files are located in ./script-opts/sofa folder.

* **[anilist-updater](https://github.com/AzuredBlue/mpv-anilist-updater)**  
  Automatically updates your AniList when reaching 80% completion based on the file name. (Requires Python)

* **[aspeed.lua](https://github.com/TinosNitso/mpv-scripts/blob/main/aspeed.lua)**  
  Multi-stereo speed randomization & tri-color clocks. Applies arbitrary speed formula & has chipmunk mode for left-channel. Also has double-mute insta-toggle. Primary channel may be left or right. A filterchain applies to all speakers - each its own mpv. Has many script-messages.  For mpv v0.34→v0.38, SMPlayer, Windows, Linux, MacOS, Android, YouTube, mp4, mp3, jpg, etc. But no randomization for Android. ([Example](https://raw.githubusercontent.com/TinosNitso/mpv-scripts/main/SCREENSHOT.webp) clock).

* **[audio-balance](https://github.com/wiiaboo/mpv-scripts/blob/master/audio-balance.lua)**  
  Port of mpv's balance property to FFmpeg lavfi pan filter.

* **[audio-dupe](https://gist.github.com/bitingsock/5e9714efff963c9689b0671d68f195ad)**  
  Runs a child process to play a second audio stream. Synced through named pipe. Recommend using with [cycle-adevice](https://gist.github.com/bitingsock/ad58ee5da560ecb922fa4a867ac0ecfd) to change the output device of the parent process.

* **[audio-file-keys](https://github.com/fbriere/mpv-scripts/blob/master/scripts/audio-file-keys.lua)**  
  Automatically apply key bindings when playing audio files.

* **[Audio WebDAV & Sub WebDAV](https://github.com/Kibakus/mpv-scripts)**  
  Auto connection of external subtitles and sound, using the "WEBDAV" protocol. The connection is explicit due to explicitly specifying folders on the WebDAV server.

* **[autochapters](https://github.com/po5/mpv-auto-chapters)**  
  Automatically finds chapters for your anime files.

* **[autocomplex.lua](https://github.com/TinosNitso/mpv-scripts/blob/main/autocomplex.lua)**  
  Animated accurate stereo spectrum overlay, with volume bars. Has many options for showfreqs, showvolume, moving overlays, colormixes, normalizers, interpolation, etc. Easy to distinguish stereo from mono.  Has many script-messages. For mpv v0.34→v0.38, SMPlayer, Windows, Linux, MacOS, Android, YouTube, mp4, mp3, etc.  [Example](https://github.com/TinosNitso/mpv-scripts/releases/download/v1.5.5/SCREENSHOT.webp) of dual-complex.

* **[autocrop](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autocrop.lua)**  
  Automatically crop the video by using lavfi's cropdetect filter to detect black bars.

* **[autocrop.lua](https://github.com/TinosNitso/mpv-scripts/blob/main/autocrop.lua)**  
  Variation crops black bars off videos & images while maintaining center in horizontal & vertical. Double-mute toggles the crop & auto_aspect. Has tolerance options, & varies limit (& start/end limits) with media-title. Can display all cropdetect or bbox metadata. Handles transparent input.  Has many script-messages.  For mpv v0.34→v0.38, SMPlayer, Windows, Linux, MacOS, Android, YouTube, mp4, mp3, jpg, etc. [Example](https://raw.githubusercontent.com/TinosNitso/mpv-scripts/main/SCREENSHOT.webp) of auto_aspect btwn 16:9 & 4:3.

* **[autodeint](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autodeint.lua)**  
  Automatically deinterlace the video by using lavfi's idet filter to detect interlaced content.

* **[auto-keep-gui-open](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Intelligently switches mpv's "keep-open" behavior based on whether you are running in video-mode or audio-only mode.

* **[auto-mode](https://github.com/stax76/mpv-scripts)**  
  Allows to automatically switch between video, audio and image mode.

* **[autoload](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autoload.lua)**  
  Automatically load playlist entries before and after the currently playing file, by scanning the directory.

* **[autoloop](https://github.com/zc62/mpv-scripts/blob/master/autoloop.lua)**  
  Automatically loops files that are under a given duration (default 5 seconds).

* **[automask.lua](https://github.com/TinosNitso/mpv-scripts/blob/main/automask.lua)**  
  Applies filterchain to animated masked region with inversion (blinking) & invisibility. `geq` uses any formula. Smooth toggle with double-mute. Comes with 14 examples, including blinking monacle, binacles, pentagon, spinning triangle, scanning visors etc. Has many script-messages.  For mpv v0.34→v0.38, SMPlayer, Windows, Linux, MacOS, Android, YouTube, mp4, mp3, jpg, etc. [Example](https://raw.githubusercontent.com/TinosNitso/mpv-scripts/main/SCREENSHOT.webp) mask.

* **[auto-save-state](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/scripts/auto-save-state.lua)**  
  Periodically saves progress with write-watch-later-config, and also cleans up the watch later data after the file is finished playing (so playlists may continue at the correct file).

* **[autosave](https://gist.github.com/Hakkin/5489e511bd6c8068a0fc09304c9c5a82)**  
  Periodically saves "watch later" data during playback, rather than only saving on quit.
  Newer fork: https://gist.github.com/CyberShadow/2f71a97fb85ed42146f6d9f522bc34ef

* **[autoselect-forced-sub](https://github.com/pierretom/autoselect-forced-sub)**  
  Automatically select forced subtitles in a different way.

* **[autospeed](https://github.com/kevinlekiller/mpv_scripts/blob/master/autospeed/)**  
  To adjust monitor refresh rate and video speed for almost 1:1 playback. (*nix)

* **[autospeedwin](https://github.com/kevinlekiller/mpv_scripts/tree/master/autospeedwin)**  
  To adjust monitor refresh rate and video speed for almost 1:1 playback. (Windows)

* **[autosub](https://github.com/davidde/mpv-autosub)**  
  Fully automatic subtitle downloading. No hotkeys required.  
  Clear setup instructions for **Windows, Mac and Linux**.

* **[autosub](https://github.com/vayan/autosub-mpv/blob/master/autosub.lua)**  
  Automatically download subtitles using **subliminal**.

* **[autosubsync](https://github.com/joaquintorres/autosubsync-mpv)**  
  Automatically sync subtitles using **ffsubsync**.

* **[betterchapters](https://gist.github.com/Hakkin/4f978a5c87c31f7fe3ae) ([update](https://github.com/mpv-player/mpv/issues/4738#issuecomment-321298846))**  
  Loads the next or previous playlist entry if there are no more chapters in the seek direction.

* **[blackout](https://github.com/sibwaf/mpv-scripts)**  
  A fast crossplatform boss-key, but without window minimization (and possible problems with some VO drivers).

* **[blur-edges](https://github.com/occivink/mpv-scripts#blur-edgeslua)**  
  Replace black bars with a blurry copy of the video

* **[bookmarker-menu](https://github.com/NurioHin/mpv-bookmarker)**  
  A bookmarker menu to manage all your bookmarks in MPV, based on [mpv-bookmarker](https://github.com/nimatrueway/mpv-bookmark-lua-script) but with a menu

* **[bookmark](https://github.com/sorayuki-winter/mpv-plugin-bookmark)**  
  Record and resume last play in current playing folder

* **[boss-key](https://github.com/detuur/mpv-scripts)**  
  Minimise and pause video at the same time. Windows/Linux. Eliminated the time lag in previous versions.

* **[boss-key-waylnad](https://github.com/Man2Dev/mpv-wayland-Boss-key)**
  Minimise and pause video at the same time in Linux through xdg-portals.

* **[btfs-hook](https://github.com/aitet/mpv-btfs-hook)**  
  Allows streaming torrents using FUSE via btfs. 

* **[btfs-stream](https://github.com/noctuid/mpv-btfs-stream)**  
  Allows streaming torrents using btfs. As far as I can tell, it is much simpler than the above scripts (no long shell script execution) and much more configurable (the other scripts have no settings). This is much slower than using webtorrent though, so I recommend using webtorrent-hook instead.

* **[celebi](https://github.com/po5/celebi)**  
  An optimized script to restore properties from past sessions. Alternative to persist-properties and remember-props scripts.

* **[censor](https://github.com/zenyd/mpv-scripts)**  
  Skip over parts of videos you don't want (others) to view

* **[channel mixer](https://gist.github.com/bitingsock/1e7ef04a151963b38e347a723d7e3201)**  
  A set of keybindings using a modifier (Shift or Ctrl) and the function keys (F8-F12) to can adjust the mixing level of surround channels on the fly.

* **[chapter-converter](https://github.com/VimWei/mpv-config/blob/main/scripts/chapter-converter.lua)**  
  Converts chapter format between YouTube (e.g., "00:10 chapter title") and mpv (FFmpeg metadata).

* **[chapter-make-read](https://github.com/dyphire/mpv-scripts/blob/main/chapter-make-read.lua)**  
  - Automatically read an load the namesake external chapter file with extension of CHP.
  - Temporarily mark the current playback position as a chapter so you can seek to it later. Also allows writing current chapters as CHP or XML. Based on `createchapter`.

* **[chapters_for_mpv](https://github.com/mar04/chapters_for_mpv)**  
  Add, remove and edit chapters of the currently played media, be it video or audio, local file or a stream. Chapters you create can be saved into a separate text file and automatically loaded when you open the same media file again.

* **[chapterskip](https://github.com/po5/chapterskip)**  
  Automatically skip chapters based on title.

* **[chapter-list](https://github.com/CogentRedTester/mpv-scroll-list/blob/master/examples/chapter-list.lua)**  
  Interractive chapter-list menu.

* **[chapters-menu](https://github.com/Seme4eg/mpv-scripts/tree/master#chapters-menu)**  
  List all chapters of current video, search and choose any.

* **[clipboard](https://github.com/CogentRedTester/mpv-clipboard)**  
  Provides a set of generic commands to interact with the clipboard.
  Specifically it allows user to copy arbitrary text to the clipboard
  and provides the ability to paste the contents of the clipboard into other commands.

* **[command_palette](https://github.com/stax76/mpv-scripts)**  
  Searchable menu for bindings, playlist, chapters, profiles, all tracks,
  audio tracks, video tracks, subtitle tracks, secondary subtitle tracks,
  subtitle lines, commands, properties, options, audio devices, Blu-ray titles,
  stream quality, aspect ratio, recent files.

* **[control](https://github.com/oe-d/control)**  
  Various features mainly for controlling playback.

* **[copy to music](https://github.com/yazeed44/mpv-scripts)**  
  Copies the current media file you're playing to a predefined directory, and plays the next entry in the playlist (Unix-like)

* **[copyTime](https://github.com/Arieleg/mpv-copyTime)**  
  Get the current time of the video and copy it to the clipboard with the format HH:MM:SS.MS .

* **[copyStuff](https://github.com/rofe33/mpv-copyStuff)**  
  Copy to clipboard the filename or URL, full filename path, current video time, current displayed subtitle text, video duration/metadata.   
  Based on [Arieleg's mpv-copyTime](https://github.com/Arieleg/mpv-copyTime).  

* **[copy-paste-URL](https://github.com/zenyd/mpv-scripts)**  
  Paste URLs directly from clipboard into mpv.  

* **[countdown](https://github.com/butterw/bShaders/blob/master/mpv/settings/scripts/countdown.lua)**  
  Display a countdown on OSD for the final seconds of the video (or music file).

* **[cp-paste-URL](https://github.com/yassin-l/cp-paste-url.git)**  
  a fork of [copy-paste-URL](https://github.com/zenyd/mpv-scripts) with support for **linux**.

* **[Tcl/Tk context menu](https://gist.github.com/avih/bee746200b5712220b8bd2f230e535de)**  
  Configurable context-menu based on Tcl/Tk, for *nix/Windows and probably macOS too.

* **[change-screen-by-aspect-ratio](https://gist.github.com/stt/9e55ffa7f5047605b2dd8af417cf36f0)**  
  Change the active fs-screen based on video's aspect ratio (for systems with monitors in landscape and portrait orientations)

* **[clock](https://gitlab.com/mozbugbox/mpv-script-mozbugbox)**  
  Constantly show current time on the lower left corner of the video screen.

* **[clipshot](https://github.com/ObserverOfTime/mpv-scripts/blob/master/clipshot.lua)**  
  Screenshot the video (with subs, without subs or the whole window) and copy it to the clipboard. For Windows, Linux/BSD and MacOs

* **[config-saver](https://github.com/Static39/mpv-scripts/tree/main/config-saver)**  
  Saves current audio track, subtitle track, subtitle position, etc. for all videos in the folder.

* **[confluence](https://github.com/ftk/mpv-confluence)**  
  Open magnet links using [confluence](https://github.com/anacrolix/confluence) HTTP service. Recommended to use [modified script](https://github.com/ftk/mpv-confluence/tree/torrserver) for [TorrServer](https://github.com/YouROK/TorrServer) instead.

* **[contact-sheet](https://github.com/occivink/mpv-gallery-view)**  
  Display thumbnails of the current file in the style of a contact sheet

* **[convert_script](https://gist.github.com/Zehkul/25ea7ae77b30af959be0)**  
  Script to quickly convert and crop videos from within mpv, with a GUI.

* **[coverart](https://github.com/CogentRedTester/mpv-coverart)**  
  Automatically load external music cover art

* **[copy-permalink](https://gist.github.com/olejorgenb/a5194d9bc183dbe0bfb02aac18fe37f9)**  
  Copy `mpv --time=<current-position> <path-playing>` to clipboard. Useful for sharing when playing URLs.

* **[copy-subtitle](https://github.com/linguisticmind/mpv-scripts/tree/master/copy-subtitle)**  
  Copies currently displayed subtitle line to clipboard. Cross-platform (Mac, Windows, Linux)  
  [Video demonstration](https://www.youtube.com/watch?v=b-5XOZpXZMg&t=1h8m16s)

* **[copy-timestamp](https://github.com/linguisticmind/mpv-scripts/tree/master/copy-timestamp)**  
  Copies current timecode in HH:MM:SS.MS format to clipboard. Cross-platform (Mac, Windows, Linux)  
  Based on [Arieleg's mpv-copyTime](https://github.com/Arieleg/mpv-copyTime)  
  [Video demonstration](https://www.youtube.com/watch?v=b-5XOZpXZMg&t=1h9m37s)

* **[createchapter](https://github.com/shinchiro/mpv-createchapter)**  
  Temporarily mark the current playback position as a chapter so you can seek to it later. Also allows writing current chapters as XML.

* **[crop](https://github.com/occivink/mpv-scripts#croplua)**  
  Crop the video by defining the target rectangle with the cursor

* **[cropmode](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/scripts/cropmode.lua)**  
  Adds a keyboard-oriented mode for cropping, outputting the result in a format suitable for ffmpeg.

* **[curvesman](https://gitlab.com/mozbugbox/mpv-script-mozbugbox)**  
  Manipulate color curves filter of FFmpeg with hotkeys. Brighten up color, change color temperature/tone, hopefully more. Adjust yellow light tone to white light tone.

* **[cycle-audio-device](https://gist.github.com/bitingsock/ad58ee5da560ecb922fa4a867ac0ecfd)**  
  Cycle through available audio devices with key binds.

* **[cycle-commands](https://github.com/CogentRedTester/mpv-scripts/blob/master/cycle-commands.lua)**  
Allows input.conf commands to be cycled through with keybinds.

* **[cycle-deinterlace-pullup](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/cycle-deinterlace-pullup.lua)**  
  Cycle between deinterlacing, pullup (IVTC), and both filters off.

* **[cycle-denoise](https://gist.github.com/myfreeer/d744c445aa71c0eeb165ca39cf6c0511)**  
  Cycle between lavfi's denoise filters (press n)

* **[cycle_messages](https://gist.github.com/rrooij/59f57ff5f5a952e56bbb)**  
  Cycle between custom OSD messages.

* **[cycle-through-existing](https://github.com/viniciusbm/mpv-cycle-through-existing)**  
  Cycle through existing video/audio/subtitle tracks, skipping the "none" option.

* **[cycle-video-rotate](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Allows you to perform video rotation which perfectly cycles through all 360 degrees without any glitches.

* **[dbvol](https://gist.github.com/Artefact2/0a9c87d6d0f0ef6a565e44d830943fff)**  
  Replaces the default volume controls with a decibel (dB) scale instead of arbitrary percentages.

* **[dessubdb](https://github.com/demanuel/dessubdb/blob/master/mpv.lua)**  
  Download automatically subtitles from the thesubdb.com using [DESSubdb](https://github.com/demanuel/dessubdb).

* **[delete-current-file](https://github.com/stax76/mpv-scripts)**  
  Move the currently playing file instantly to the recycle bin.

* **[delete-file](https://github.com/zenyd/mpv-scripts)**  
  Provides the ability to delete files being played through mpv

* **[locate-file](https://github.com/nimatrueway/mpv-locatefile-lua-script)**  
  Locate current media file on your OS file browser 

* **[deframe](https://github.com/dimitris888/mpv-deframe)**  
  It removes the frame of youtube videos (press g)

* **[delogo](https://github.com/GitHubUserKaito/mpv-delogo)**  
  Remove channel logo from videos

* **[drag-to-pan](https://github.com/occivink/mpv-image-viewer)**  
  Pan the current video or image with the cursor.

* **[drcbox](https://gist.github.com/richardpl/0c8011dc23d7ac7b7831b2e6d680114f)**  
  Dynamic Audio Normalizer filter with visual feedback.

* **[dualsubs utils](https://github.com/VimWei/mpv-config)**  
  Auto load dual subs; Auto reload dual subs; Swap primary/secondary subs position; Merge dual subs to one ASS sub.

* **[dvd-browser](https://github.com/CogentRedTester/mpv-dvd-browser)**  
  A script to browse and load DVD titles using the lsdvd command-line utility

* **[dynamic-crop](https://github.com/Ashyni/mpv-scripts#dynamic-croplua)**  
  Dynamically crop the video by using lavfi's cropdetect filter to detect hard-coded black bars for Ultra Wide Screen (21:9) or any screen different from 16:9 (phone/old TV).

* **[dyn_menu](https://github.com/tsl0922/mpv-menu-plugin/blob/main/src/lua/dyn_menu.lua)**  
  [Context Menu](https://mpv.io/manual/stable/#context-menu) script for mpv, with support for loading menu from `input.conf`.

* **[easycrop](https://github.com/aidanholm/mpv-easycrop)**  
  Manually crop a video during playback.

* **[encode](https://github.com/occivink/mpv-scripts#encodelua)**  
  Re-encode or remux part of the current video. Can also preserve some filters, such as "crop".

* **[equalizer](https://github.com/he2a/mpv-scripts)**  
  Script for togglable parametric equalizer with EQ configuration similar to EqualizerAPO format present in a csv format. Script can be whitelisted based on whether the content is audio, video or a movie. Settings are located in equalizer.conf in ./script-opts folder and equalizer configuration in ./script-opts/equalizer folder.

* **[equalizer](https://gist.github.com/avih/41acff712abd32e1f436235388c8b523)**  
  5-bands equalizer with colorful display.

* **[evafast](https://github.com/po5/evafast)**  
  Fast-forwarding and seeking on a single key, with quality of life features like slowing down a bit when subtitles are shown.

* **[excerpt](https://gitlab.com/lvml/mpv-plugin-excerpt)**  
  Allows you to quickly create excerpts from media files, you just have to set begin and end markers.

* **[excessive-history](https://gist.github.com/Abject-Web/3f4f0e85dad73303b9dd1ef1f55c3147)**  
  Excessive played media logger. Logs file name, time, and which parts were played. Will generate a `history.txt` in the mpv config folder. Only tested on Windows.

* **[exit-fullscreen](https://github.com/zc62/mpv-scripts/blob/master/exit-fullscreen.lua)**  
  If you use `--keep-open=yes`, this script exits fullscreen mode when the playback reaches the end of file/playlist.

* **[epgtv](https://github.com/blogdron/EPGTV)**  
  Simple EPG information for IPTV M3U playlist in mpv. 

* **[fade-on-exit](https://github.com/logiclrd/MPVFadeOnExit/blob/main/mfoe.lua)**
  Adds an additional key binding Ctrl-Q that, like Q, exits playback, but gracefully fades to black first instead of just cutting the video.

* **[fastforward](https://github.com/jgreco/mpv-scripts/blob/master/fastforward.lua)**  
  Instead of skipping forward in media files, speed up the playback for a few seconds.  Playback speed decays back to 1x after a few seconds.  Tap rapidly or hold down to go faster.

* **[fast-forward](https://github.com/zsugabubus/mpv-fastforward)**  
  Another fast-forward plugin with some added features and a bit more customization options.

* **[ff-silence](https://github.com/mesvam/ff-silence)**  
  Fast forward through silences and quiet parts of audio. This is especially useful on videos where the speaker uses many long pauses.

* **[filenavigator](https://github.com/jonniek/mpv-filenavigator)**  
  Navigate directories and open files from your system.

* **[file-browser](https://github.com/CogentRedTester/mpv-file-browser)**  
  A script that implements an interactive file browser on the OSD, which allows one to browse their system and open or append files and folders to the playlist. The user can specify keybinds to perform custom commands on items and can download addons for advanced additional behaviour.

* **[file-rating](https://github.com/stax76/mpv-scripts)**  
  Write a star rating to the filename of the currently playing file.

* **[filter-test](https://gitlab.com/mozbugbox/mpv-script-mozbugbox)**  
  Test mpv/FFmpeg video filter(vf) strings with editable popup dialog. 

* **[find_subtitles](https://github.com/directorscut82/find_subtitles)**  
  (Down)load subtitles with subliminal.

* **[firequalizer15](https://github.com/mfcc64/mpv-scripts/blob/master/firequalizer15.lua)**  
  Linear phase 15-bands equalizer.

* **[fix_sub_timing](https://github.com/wiiaboo/mpv-scripts/blob/master/fix-sub-timing.lua)**  
  Compute the correct speed/delay of subtitles by manually synching two points in time.

* **[force-window-profile](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/scripts/force-window-profile.lua)**  
  Applies the force-window profile when force-window is set (i.e. when starting mpv from the .desktop file)

* **[fpsadjust](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/scripts/avail/fpsadjust.lua)**  
  Automatically adjust playback speed to synchronize the video to the display if possible (eg. by adjusting 23.976 Hz to 24 Hz for better compatibility with a 60 Hz display).
**Obsolete:** mpv now has a native display-sync option.

* **[fuzzydir](https://github.com/sibwaf/mpv-scripts)**  
  Allows using wildcards for `sub-file-paths` and `audio-file-paths`.

* **[gallery-dl_hook](https://github.com/jgreco/mpv-scripts/blob/master/gallery-dl_hook.lua)**  
  Load online image galleries (imgur, etc) as playlists using [gallery-dl](https://github.com/mikf/gallery-dl/).

* **[generate-edl](https://gist.github.com/guidocella/5f05794d0a8400b2393fe7a9995ebb43)**  
  Bookmark scenes in EDL files.

* **[gestures](https://github.com/omeryagmurlu/mpv-gestures)**  
  Touchscreen and mouse gestures for mpv.

* **[gnome-inhibit](https://gist.github.com/crazygolem/a7d3a2d3c0cee5d072c0cbbbdee69286)**
  Prevent the screen from blanking under GNOME+Wayland while a video is playing.

* **[gpufreq](https://github.com/CounterPillow/mpv-gpufreq)**  
  Show current and maximum GPU frequencies for GPUs using the DRM stack on Linux.

* **[groupwatch_sync](https://github.com/po5/groupwatch_sync)**  
  Quickly get back in sync with a group watch by adjusting playback speed.

* **[guess-media-title](https://github.com/zenwarr/mpv-config/blob/master/scripts/guess-media-title.lua)**  
  Uses [guessit](https://github.com/guessit-io/guessit) to detect a media title by filename and set `force-media-title` variable. Useful for getting cleaner screenshot file names.

* **[histogram](https://github.com/detuur/mpv-scripts)**  
  Exposes a configurable way to overlay ffmpeg histograms in mpv. There is a substantial amount of config available.

* **[history](https://github.com/stax76/mpv-scripts)**  
  Writes date, time, playtime and filename to a log file:  
  `10.09.2022 19:50  3 D:\Samples\Big Buck Bunny.mkv`

* **[history](http://git.smrk.net/mpv-scripts/file/history.lua.html)**  
  Autosave played media items in an SQLite database, restore last played
  position, select (with dmenu(1)) and play item from history.
  Very simple, easy to customize/modify (no options, just edit the code).

* **[history-bookmark](https://github.com/yuukidach/mpv-scripts)**  
  Create a history file to store the episode we watched last time. And let us easily jump to the video we watched last time.
    * [history-bookmark](https://github.com/dyphire/mpv-scripts/blob/main/history-bookmark.lua): more powerful

* **[KDialog-open-files](https://gist.github.com/ntasos/d1d846abd7d25e4e83a78d22ee067a22)**  
Use KDE's KDialog to add files to playlist, subtitles to playing video or open URLs.

* **[zenity-open-files](https://github.com/alifarazz/mpv-zenity-open-files)**  
Use GTK's zenity to add files to playlist, subtitles to playing video or open URLs.

* **[mpv-youtube-search](https://github.com/rozari0/mpv-youtube-search)**  
Use Zenity and youtube-dl to search youtube videos. Linux only.

* **[mpv-playlist-kdialog](https://gist.github.com/ftk/5e26656a2ec9a6cb0fef46918f741d0a)**  
Use KDE's KDialog or GTK's zenity to show current playlist or select playlist entry.

* **[image-config](https://github.com/guidocella/mpv-image-config)**  
  A configuration to use mpv as an image viewer.

* **[image-viewer](https://github.com/occivink/mpv-image-viewer)**  
   Configurations, scripts and tips for using mpv as an image viewer.

* **[Immersive](https://github.com/Ben-Kerman/immersive)**  
  Versatile language learning script for generating Anki notes/cards with dictionary definitions, audio clips and screenshots from the current video, and word pronunciation audio. Also includes some other features that are useful for language immersion.

* **[lang-learner](https://github.com/liberlanco/mpv-lang-learner)**
  Turn MPV into language learner tool. Includes:  AB-loop current subtitle or auto loop each one, quick switch between lang you know and lang you are learning, forward to browser (dictionaries, translators), record for future extra learning, export to external script for integrations, and a bit more.

* **[input-event](https://github.com/natural-harmonia-gropius/input-event)**  
  Script for Enhanced input.conf with better, conflict-free, low-latency event mechanism.

* **[interactive-video](https://github.com/mosquito-byte/mpv-interactive-video)**  
  Script for watching interactive videos (such as Netflix's *Black Mirror: Bandersnatch*).

* **[interSubs](https://github.com/oltodosel/interSubs)**  
  Interactive subtitles. Instantly translate selected word/sentence. Works on Linux, macOS.

* **[mpv subber](https://framagit.org/Midgard/mpv-subber)**  
  Write subtitles in mpv.

* **[rikai-mpv](https://github.com/fxmarty/rikai-mpv)**  
  Integrated Japanese dictionary and parser to translate by hovering over words. Works on Linux.

* **[kodi-mpv-hook](https://github.com/Eskander/kodi-mpv-hook)**  
  Allows Kodi streaming add-ons to work correctly when using mpv as an [external player for Kodi](https://kodi.wiki/view/External_players) by parsing and extracting protocol options from Kodi's [custom URL format](https://kodi.wiki/view/HTTP).

* **[lats](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/lats.lua)**  
  The Low ATtention Span mpv script. Plays brief segments from random positions of one or more files, kinda like flipping through TV channels.

* **[last.fm scrobbler](https://github.com/l29ah/w3crapcli/blob/master/last.fm/mpv-lastfm.lua)**  
  Sends the information about playing tracks to [last.fm](http://last.fm/), see http://www.last.fm/help/faq?category=99 for more info.

* **[leader key](https://github.com/Seme4eg/mpv-scripts/tree/master#leader)**  
  Adds _leader_ key to your mpv. With prefixes and [which-key](https://github.com/justbur/emacs-which-key) functionality. [demo](https://i.imgur.com/dUWFu3u.gif)

* **[libass_sub_selector](https://github.com/po5/libass_sub_selector)**  
  Visually select individual subtitles a la PotPlayer.

* **[lilskippa](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/scripts/lilskippa.lua)**  
  Skip to black, skip to silence, skip to scene change.

* **[List chapters](https://github.com/oltodosel/mpv-scripts#show_chapterslua)**  
  Shows chapters and their time at the bottom left corner. [example](https://github.com/oltodosel/mpv-scripts/raw/master/show_chapters.jpeg)

* **[live-filters](https://github.com/hdb/mpv-live-filters)**  
  Add, remove or toggle ffmpeg video filters during mpv playback.

* **[llm-subtrans](https://github.com/sorz/mpv-llm-subtrans/)**  
  Extract & translate subtitles with OpenAI API. Streaming & contextual.

* **[local-language](https://github.com/422658476/MPV-EASY-Player/blob/master/portable-data/scripts/local-language.lua)**  
  Let the text displayed by mpv osd become the language you are most familiar with, that is, language localization, such as 【volume: 100%】 becomes 【音量:100%】.

* **[LoopToFile](https://github.com/NovaFormaLab/LoopToFile)**  
  Functional script for mpv that allows you to generate playback loops and extract media fragments into new files. L∞p → file.ext

* **[loop-until](https://github.com/ZreXoc/mpv-loop-until)**  
  Loop the video until a specified amount of time. (e.g. loop a 30s wallpaper video to 30min)

* **[lrc](https://github.com/guidocella/mpv-lrc)**  
  Download synchronized lyrics of the currently playing song.

* **[lua-mpris](https://github.com/dodo/lua-mpris)**  
  Adds mpris support to mpv.

* **[lua-repl](https://github.com/guidocella/mpv-lua-repl)**  
  A Lua REPL in the console with autocompletion and pretty-printing of returned tables. It lets you test mpv's and Lua's API without writing a script.

* **[main.lua](https://github.com/TinosNitso/mpv-scripts/blob/main/main.lua)**  
  Loads other scripts, hooks in yt-dlp, displays title, has subtitle override, loops short files, sets options (with delay), & has detailed commentary. Has many script-messages. For mpv v0.34→v0.38, SMPlayer, Windows, Linux, MacOS, Android, YouTube, mp4, mp3, jpg, etc. But no yt-dlp for Android. [Example](https://youtu.be/le2JGgjRJBw) title. 

* **[matroska-crop](https://github.com/sbruder/mpv-matroska-crop)**  
  Automatically crop video using the Matroska PixelCrop properties. Includes optional workaround for hardware decoding.

* **[mdmenu](https://codeberg.org/NRK/mpv-toolbox/src/branch/master/mdmenu)**  
  A script to use dmenu for selecting audio/subtitle/chapters etc.

* **[memo](https://github.com/po5/memo)**  
  A recent files/history menu for mpv with optional uosc integration.

* **[metadata-osd](https://github.com/vc-01/metadata-osd)**  
  Adds OSD showing song name, album name and other metadata.

* **[mfpbar](https://codeberg.org/NRK/mpv-toolbox/src/branch/master/mfpbar)**  
  A minimalistic progressbar and osc replacement.

* **[mfpbar-drag](https://github.com/layercak3/mfpbar-drag)**  
  mfpbar with support for dragging the bar.

* **[minesweeper](https://github.com/wiiaboo/mpv-scripts/blob/master/mines.lua)**  
  Minesweeper game.

* **[misc](https://github.com/stax76/mpv-scripts)**  
  - Show detailed media info on screen
  - Cycle audio and subtitle tracks, include only languages you know
  - Load or append files/URLs from clipboard
  - Jump to a random position in the playlist
  - Navigate in playlist to next/previous/first/last file
  - Restart mpv restoring the properties path, time-pos, pause and volume
  - Execute Lua code from input.conf
  - When seeking display position and duration like so: 70:00 / 80:00

* **[ModernX](https://github.com/cyl0/ModernX)**  
  A modern OSC UI replacement for MPV that retains the functionality of the default OSC.

* **[ModernX](https://github.com/zydezu/ModernX) (fork by zydezu)**  
  A fork of ModernX with many additional features and customization.

* **[ModernZ](https://github.com/Samillion/ModernZ)**  
  A fork of ModernX designed to enhance functionality by adding more features, all while preserving the core standards of mpv's OSC.

* **[move-file](https://github.com/ayghub/move-file)**  
  A simple lua script to move your files to the watched folder for example. 

* **[awesome-osc](https://github.com/Qiyue0726/awesome-osc)**  
  An awesome osc UI replacement for MPV player.

* **[mpegts-truncate](https://github.com/hoehermann/mpv-mpegts-truncate)**  
  Removes beginning of MPEG TS file up to current position without re-writing the whole file.

* **[mpv-acestream](https://github.com/Digitalone1/mpv-acestream)**  
  Add AceStream protocol handler to mpv. Let the user open streams by dropping Acestream links into mpv GUI or by passing them as command line argument.

* **[mpv-bluetooth-av-delay](https://github.com/fatihkaan22/mpv-bluetooth-av-delay)**  
  Adds desired A-V delay automatically, if default audio sink is a bluetooth device.

* **[mpv-bookmarker](https://github.com/nimatrueway/mpv-bookmark-lua-script)**  
  Bookmark your favorite time on media files

* **[mpv-BoxToWide](https://github.com/Samillion/mpv-boxtowide)**  
  A simple mpv script to change 4:3 aspect-ratio of video files/streams to 16:9 automatically.

* **[mpv-Change-OSD-Media-Title](https://github.com/nmoorthy1/mpv-Change-OSD-Media-Title)**  
  Displays filename, percentage watched, current chapter, and number of frames dropped in the OSD media title and updates it whenever one of the values has changed.

* **[mpv_crop_script](https://github.com/TheAMM/mpv_crop_script)**  
  Take cropped screenshots directly within mpv, without the need for external dependencies.

* **[mpv_discordRPC](https://github.com/noaione/mpv-discordRPC)**  
  Discord RPC integration for mpv using lua-discordRPC as base.

* **[mpv_discordRPC](https://github.com/cniw/mpv-discordRPC) *(alternative version)***  
  Discord Rich Presence integration for mpv Media Player. Added some features and support: Linux, MacOS and Windows.

* **[mpv-discord](https://github.com/tnychn/mpv-discord)**  
  A cross-platform Discord Rich Presence integration for mpv with no external dependencies. Consists of a Go binary for updating the presence and a Lua script for launching it.

* **[mpv-lines-meme-generator](https://github.com/WatanabeChika/mpv-lines-meme-generator)**  
  Allow users to take screenshots in MPV, crop them to keep only the bottom portion, and stitch them together into a long vertical image, just like a meme of lines.

* **[mpvcord](https://github.com/yutotakano/mpvcord)**  
  Discord integration for mpv, using the Game SDK instead of Discord RPC. Supports: MacOS and Windows. (Linux is not supported by Game SDK)

* **[mpvcut](https://github.com/zydezu/mpvconfig/blob/main/scripts/mpvcut.lua)**  
  Easily clip, compress and re-encode selected clips.

* **[mpv_frame_info](https://github.com/Kagami/mpv_frame_info)**  
  Show frame info, similar to ffdshow's OSD.

* **[mpv-history](https://gist.github.com/garoto/e0eb539b210ee077c980e01fb2daef4a)**  
  Simple played media logger. Will generate a `mpvhistory.log` in the default mpv config folder (%APPDATA%/mpv/ or $HOME/.config/mpv/) in the format `[$DATE $TIME] $PATH ($?MEDIA-TITLE)`. Only tested on Windows.

* **[mpv-i3-floating-centered](https://github.com/mdnghtman/mpv-i3-floating-centered)**  
  Show mpv window in the center of the display when it is in floating mode (i3wm)

* **[mpv-jellyfin](https://github.com/EmperorPenguin18/mpv-jellyfin)**  
  Plugin that turns mpv into a Jellyfin client.

* **[mpv_manager](https://github.com/po5/mpv_manager)**  
  User script and shader manager for mpv

* **[mpv-manga-reader](https://github.com/Dudemanguy/mpv-manga-reader)**  
  Script for using mpv as a manga reader.

* **[mpvMatroska](https://github.com/hubblec4/mpvMatroska)**  
  mpvMatroska turns mpv into a Matroska player.

* **[mpv-osc-framework](https://github.com/maoiscat/mpv-osc-framework)**  
  A simple toolbox to help you build your own osc.

* **[mpv-osc-orange](https://github.com/maoiscat/mpv-osc-orange)**  
  An osc/ui replacement of dark theme.

* **[mpv-osc-simple](https://github.com/maoiscat/mpv-osc-simple)**

  An osc/ui replacement of white theme.

* **[mpv-osc-modern-f](https://github.com/FinnRaze/mpv-osc-modern-f)**  
  mpv osc script forked from [mpv-osc-modern](https://github.com/maoiscat/mpv-osc-modern).

* **[mpv-pdf](https://github.com/jgreco/mpv-pdf)**  
  View PDFs in mpv using ImageMagick.   Supports: Linux, MacOS

* **[mpv_reduce_stream_cache](https://github.com/divout/mpv_reduce_stream_cache)**  
  Reduces MPV cache for streams by increasing playback speed. Works with Twitch through Streamlink.

* **[mpv_irc](https://github.com/po5/mpv_irc)**  
  Display lines from an IRC channel or any text file.

* **[mpv_sponsorblock](https://github.com/po5/mpv_sponsorblock)**  
  Script to skip sponsored segments of YouTube videos.

* **[mpv-webp-generator](https://github.com/DonCanjas/mpv-webp-generator)**  
  Creates high quality animated webp using mpv hotkeys. (For windows only)

* **[mpv-yledl](https://github.com/pekkarr/mpv-yledl)**  
  Watch videos from YLE Areena in mpv using yle-dl

* **[mpv-ytdlAutoFormat](https://github.com/Samillion/mpv-ytdlautoformat)**  
  A simple mpv script that automatically adjusts `ytdl-format` (yt-dlp) for specified domains.

* **[mpv2anki](https://github.com/SenneH/mpv2anki)**  
A simple way to add notes to Anki with Audio, screenshots and/or subtitles, with few dependencies.

* **[mpvacious](https://github.com/Ajatt-Tools/mpvacious)**  
Make subs2srs-style Anki cards with automatically generated audio-clips and snapshots. Media files are saved in `ogg/opus` and `webp` formats to save space on AnkiWeb.

* **[mpv-rename](https://github.com/Kayizoku/mpv-rename)**  
  Rename files on the go directly from within MPV player window without leaving it.

* **[mpvSockets](https://github.com/wis/mpvSockets)**  
  creates one IPC sockets per mpv instance, instead of one socket for the last started instance.   _Supports_: Linux, MacOS and Windows.

* **[mpv_socket](https://github.com/Farzat07/mpv_socket)**  
  Creates one IPC socket per mpv instance. Configurable. Socket name can be modified while playing.

* **[mpv_segment_length](https://github.com/shadax1/mpv_segment_length)**  
  Displays the length of a segment from a designated point to any other point in a video.

* **[mpv_sort_script](https://github.com/TheAMM/mpv_sort_script)**  
  Sort files and directories by name, age, size or randomly, recursively or when coming across a directory.

* **[mpv_slicing](https://github.com/Kagami/mpv_slicing)**  
  Cut uncompressed fragments of the video.

* **[mpv_slicing_copying](https://github.com/snylonue/mpv_slicing_copy)**  
  A fork from [mpv_slicing](https://github.com/Kagami/mpv_slicing). It will cut fragments of the video in original format instead of RGB

* **[mpv_thumbnail_script](https://github.com/TheAMM/mpv_thumbnail_script)** ⚠️ *original, outdated release file*   
  **[mpv_thumbnail_script](https://github.com/marzzzello/mpv_thumbnail_script)** *fork, updated release file*   
  Show preview thumbnails when hovering over the seekbar, without the need for external dependencies.

* **[mpv-scripts](https://github.com/dya-tel/mpv-scripts)**  
  * blackout - Couldn't find the "Boss key", but you don't want someone (or simply anyone) to see what you are watching?
  * fuzzydir - This script will read your paths from `mpv.conf`, find those which end with `**` and explode them for good! For example, imagine we have a directory named `subs`, which contains `a` and `b` subdirectories.
  * reload - Sometimes you have unstable internet connection, or YouTube server dies, or your computer was sleeping for too long, or whatever. The thing is: you were watching something, you lost the connection, MPV doesn't want to play it further, you don't want to find the video again and then seek it to the moment you were watching.

* **[mpv-slash-search](https://codeberg.org/Anakiev/mpv-slash-search)**  
  Simple and lightweight script that allows you to search for a file in the playlist and play the first match.

* **[mpv-sorted-screenshots](https://github.com/BanchouBoo/mpv-sorted-screenshots)**  
  Script to sort screenshots based on the file they're screenshotted from and nested directories.

* **[mpv-taskbar-buttons](https://github.com/qwerty12/mpv-taskbar-buttons)**  
  Hackish script to add [thumbbar media control buttons](https://raw.githubusercontent.com/qwerty12/mpv-taskbar-buttons/preview/screenshot.png) for mpv on Windows

* **[mpv-twitch-chat](https://github.com/CrendKing/mpv-twitch-chat/)**  
  Show Twitch chat messages as subtitles when watching Twitch VOD with mpv.

* **[mpv-twitch-chat-irc](https://github.com/morrah/mpv-twitch-chat-irc)**  
  Show Twitch chat messages as subtitles when watching Twitch LIVE with mpv.

  Based on [mpv Twitch Chat](https://github.com/CrendKing/mpv-twitch-chat/) for VODs, but since `mpv-twitch-chat` uses Twitch API to retrieve comments history, it doesn't support live chat comments. This script uses a python subprocess to keep a background irc connection to a channel and dump last 10 messages to file in SubRip format.

* **[mpv-youtube-chat](https://github.com/BanchouBoo/mpv-youtube-chat)**  
  Overlay YouTube chat replays in mpv using yt-dlp.

* **[mpv-txt](https://github.com/jgreco/mpv-txt)**  
  Play text files using text-to-speech (TTS). (Works on Linux, MacOS; see Dependencies).

* **[MPVMediaControl](https://github.com/datasone/MPVMediaControl)**  
  Integrate MPV with Windows System Media Transport Controls (the control buttons near the volume indicator thingy). See [pic](https://raw.githubusercontent.com/datasone/MPVMediaControl/master/img/screenshot.png) for reference.

* **[mpv-volnorm](https://gitlab.com/derobert/mpv-volnorm)**  
  Client-server setup to provide EBU R.128 volume leveling to MPV, even if files stored on a server and played on multiple machines. (Works on Linux, probably all Unix-like; server in Perl).

* **[mpvmenu](https://github.com/nezumisama/mpvmenu)**  
  Adds a pop-up menu to mpv, which can be bound to a key or button

* **[multi-command-if](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Very powerful conditional logic and multiple action engine for your keybindings, without having to write a single line of code!

* **[multiloop](https://github.com/unusualpepe/mpv-multiloop)**  
  Loop over multiple A-B points (and save them for future use)

* **[multisocket](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/scripts/multisocket.lua)**  
  Creates a numbered socket for each instance of mpv

* **[M-x](https://github.com/Seme4eg/mpv-scripts/tree/master#m-x)**  
  A menu that shows all commands you have available, key bindings and commends (if present) and from which you can call any of those commands. [demo](https://i.imgur.com/8zTPTzK.gif)

* **[myshows](https://github.com/gim-/mpv-plugin-myshows)**  
  Marks currently watched episode on MyShows website.

* **[nextfile](https://github.com/jonniek/mpv-nextfile)**  
  Force opens next or previous file in the currently playing files directory.

* **[noAFK](https://gist.github.com/bitingsock/a56dddb1e953fdd40e3035b37c387f28)**  
  send virtual keystroke (default F15) during playback to prevent auto-AFK of some applications (requires Windows powershell).

* **[notify](https://github.com/rohieb/mpv-notify)**  
  Adds desktop notifications to the mpv media player, which show metadata like artist, album name and track name when the track changes.

* **[mpv-notify](https://github.com/mpv-notify/mpv-notify)**
  Converging point for all forks of rohieb's notify scrip.

* **[notify-send](https://github.com/emilazy/mpv-notify-send)**  
  A simpler and more recent notifications script for libnotify-compatible (i.e. Unix-like) notifications daemons only. Supports cover art.

* **[oled-screensaver](https://github.com/Akemi/mpv-oled-screensaver)**  
  To prevent burn-ins on OLED TVs, this script fades-in a black screen after 15 seconds when paused in fullscreen.

* **[ontop-playback](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/ontop-playback.lua)**  
  Disables the ontop property when pausing, and enables it again when unpausing the video, if it was disabled. Change it only when the player is not in fullscreen to prevent screen flickering.

* **[ontop-only-while-playing](https://github.com/kungfubeaner/mpv-ontop-only-while-playing-lua/blob/master/on_top_only_while_playing.lua)** 
Ontop is only active during video playback. Ontop is automatically disabled during idle, pause and is able
to be dynamically disabled without having to restart unlike the previous script.

* **[ontop-window](https://github.com/wishyu/mpv-ontop-window/blob/main/ontop-window.lua)**  
  Disables the ontop property when in fullscreen, and enables it again when in window mode, if it was disabled. Heavily inspired by [ontop-playback](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/ontop-playback.lua).

* **[open-anilist-page](https://github.com/ehoneyse/mpv-open-anilist-page)**  
  Opens the Anilist page that corresponds to the currently playing (anime) file.

* **[open-dir](https://github.com/ayghub/open-dir)**  
  A simple script that opens the current path of the file in the file explorer.

* **[open-imdb-page](https://github.com/ctlaltdefeat/mpv-open-imdb-page)**  
  Opens the IMDb page that corresponds to the currently playing media file.

* **[open-in-explorer](https://gist.github.com/Sneakpeakcss/05a97d509b8be67a6f11400b0bee54ab)**  
  Opens directory and selects the currently playing file (Windows).

* **[open-kinopoisk-page](https://github.com/WANDEX/mpv-open-kinopoisk-page)**  
  Opens the kinopoisk page that corresponds to the currently playing media file.

* **[open-file-dialog](https://github.com/rossy/mpv-open-file-dialog)**  
  (Windows) Launches a regular Windows file open dialog for loading videos.

* **[osc-style](https://github.com/422658476/MPV-EASY-Player/tree/master/mpv-easy-data/osc-style)**  
  Change the mpv osc to a more beautiful and practical look, which is the osc theme feature, a variety of styles to choose from,this is a [tutorial and a preview](https://github.com/422658476/MPV-EASY-Player#%E7%9C%8B%E5%88%B0%E4%B8%8A%E9%9D%A2%E5%9B%BE%E4%B8%8A%E8%BF%99%E4%BA%9Bosc%E6%A0%B7%E5%BC%8F%E4%BA%86%E5%90%97%E5%AE%83%E4%BB%AC%E4%B8%8D%E4%BB%85%E5%8F%AF%E4%BB%A5%E5%AD%98%E5%9C%A8%E4%BA%8Empv-easy-player%E4%B8%AD%E4%BD%A0%E4%BD%BF%E7%94%A8%E7%9A%84mpv%E7%9A%84osc%E4%B9%9F%E5%8F%AF%E4%BB%A5%E5%8F%98%E6%88%90%E8%BF%99%E6%A0%B7).

* **[osc-show-hide](https://github.com/linguisticmind/mpv-scripts/tree/master/osc-show-hide)**  
  Toggles the on-screen controller with a hotkey  
  [Video demonstration](https://www.youtube.com/watch?v=b-5XOZpXZMg&t=1h7m17s)

* **[osd-bar](https://github.com/422658476/MPV-EASY-Player/blob/master/portable-data/scripts/osd-bar.lua)**  
  Always show osd progress bar, with the more beautiful color matching in the [configuration file](https://github.com/422658476/MPV-EASY-Player/blob/master/mpv-easy-data/rjno1.conf), you can make the osd progress bar display the current progress at the bottom of the window beautifully,this is a [preview](https://raw.githubusercontent.com/422658476/MPV-EASY-Player/master/img/mpv-easy-player-osd-bar-lua.jpg).

* **[osd-clock](https://github.com/blue-sky-r/mpv/blob/master/scripts/osd-clock.lua)**  
  Periodically shows OSD clock (many configurable options).

* **[osm](https://github.com/stax76/mpv-scripts)**  
  Shows a customizable on screen menu, which is useful to navigate via remote control.

* **[pause-indicator](https://gist.github.com/torque/9dbc69543118347d2e5f43239a7e609a)**  
  Displays a momentary icon that flashes in the middle of the screen, similar to YouTube.

* **[pause-indicator-lite](https://github.com/Samillion/ModernZ/tree/main/extras/pause-indicator-lite)**  
  A simple script that displays an indicator on pause, with options to adjust icon, color, height, width, opacity and whether to toggle pause with a keybind or not.

* **[permanent-pause-indicator](https://github.com/oltodosel/mpv-scripts#pause-indicatorlua)**  
  Displays a permanent indicator in the middle of the screen while mpv is paused.
[Preview](https://github.com/oltodosel/mpv-scripts/raw/master/pause-indicator.jpg)

* **[pause-when-minimize](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/pause-when-minimize.lua)**  
  Pauses the player video when minimizing, and unpauses it when brought up again.

* **[peerflix-hook](https://gist.github.com/ekisu/bba287693830055a6bad90081c1ad4e2)**  
  Allows streaming of magnet links using peerflix, similar to youtube-dl.

* **[mpv-peerflix-hook](https://github.com/noctuid/mpv-peerflix-hook)**  
  Alternate version of the above gist that works with multiple running peerflix instances and only kills the correct peerflix instance when exiting.

* **[pickshader](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/scripts/pickshader.lua)**  
  Provides a `^R`-esque interface for easily setting/appending to `--glsl-shaders` (this does not install shaders for you)

* **[webtorrent-hook](https://github.com/noctuid/mpv-webtorrent-hook)**  
  Allows streaming torrents using webtorrent (same as mpv-peerflix-hook but using webtorrent instead). Webtorrent-cli can play in mpv with `webtorrent --mpv`, but this script allows using torrent identifiers as the file argument to mpv or pasting them into the current playlist using one of the pasting scripts listed here. It also supports additional functionality like automatic file cleanup and the ability to remember the last file played in the torrent. See the readme for more information. See [here](https://github.com/noctuid/mpv-webtorrent-hook#comparison-with-webtorrent-mpv-hook) for a comparison with the other javascript webtorrent plugin. I recommend this plugin over my others (mpv-peerflix-hook and btfs-stream).

* **[persist-properties](https://github.com/d87/mpv-persist-properties)**  
  Keeps volume and other properties between sessions

* **[pitchcontrol](https://github.com/FichteFoll/mpv-scripts/blob/master/pitchcontrol.lua)**  
  Adjusts audio pitch in half-tone steps.

* **[playlistmanager](https://github.com/jonniek/mpv-playlistmanager)**  
  This script allows you to see and interact with your playlist in an intuitive way.

* **[playlist-navigator](https://github.com/drogers141/mpv-playlist-navigator)**
  OSD display features easy navigation with scrolling and search to select files to play or remove from playlist.

* **[playlistnoplayback](https://github.com/422658476/MPV-EASY-Player/blob/master/portable-data/scripts/playlistnoplayback.lua)**  
  If you enable the save play history and progress function, this lua script can solve the problem of automatically jumping to the previous playback progress when playing the next file when playing the playlist, that is, let the playlist always play the next file from the beginning every time. the limitations of this script, please see the comments section in the content.

* **[playlist-view](https://github.com/occivink/mpv-gallery-view)**  
  Display and navigate the playlist in a grid view of thumbnails.

* **[pointer-event](https://github.com/christoph-heinrich/mpv-pointer-event)**  
  Mutually exclusive, low latency mouse/touch input event detection.  
  Executes configurable commands on single-click, double-click, long-click and dragging.

* **[progressbar](https://github.com/torque/mpv-progressbar)**  
  A minimalistic OSC replacement. It provides a small, unintrusive progress bar that persists at the bottom of the video window.

* **[profile-cycle](https://github.com/Funami580/dotfiles/blob/master/.config/mpv/scripts/profile-cycle.lua)**  
  Cycle between your custom defined profiles while watching the video.

* **[quack](https://github.com/CounterPillow/mpv-quack)**  
  Temporarily lower the volume after a seek to save your ears from unpleasant sudden volume changes.

* **[quick-scale](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Quickly scale the video player to a target size, with full control over target scale and max scale. Helps you effortlessly resize a video to fit on your desktop, or any other video dimensions you need!

* **[radio-title](https://github.com/olivierlemoal/mpv-radio-title-script/)**  
  Automatically fetch current playing title from webradio website when not provided by stream.

* **[recent](https://github.com/hacel/recent)**  
  Recently played menu using a history log file in `config` directory, display using a hotkey or automatically when idle.

* **[redshift_toggle](https://git.sr.ht/~q3cpma/dotfiles/tree/master/.config/mpv/scripts/redshift_toggle.lua)**  
  Toggle redshift when loading a video file and when reaching the end of said file. Now also handles pause.

* **[rename-sub](https://github.com/ayghub/rename-sub)**  
  Rename current subtitle file as the playing video 

* **[rewindPlaylist](https://gist.github.com/bitingsock/0f22c631295273d5a53e4337c25fe161)**  
  keybind to rewind to the end of the previous playlist entry

* **[toggle-redshift-on-play](https://gist.github.com/CreamyCookie/d036b66af4e17ea527d08e303eb96145)** (**[kill-restart-version](https://gist.github.com/CreamyCookie/079570ad0dd27d322421f6637c828ab8)**)  
  Based on the above one, this one also re-enables redshift when pausing and disables it again when unpausing.

  The alternative version achieves the same by killing and restarting redshift (more consistent).

* **[touch-gestures](https://github.com/christoph-heinrich/mpv-touch-gestures)**  
  Gestures for play/pause, speed, volume, seeking and next/previous playlist-item.  

* **[trakt-mpv](https://github.com/LiTO773/trakt-mpv)**  
  Connects trakt.tv with mpv and automatically scrobbles movies/shows. (Python is also needed for this script to function)

    * [trakt-mpv fork](https://github.com/qwerty12/mpv-config/tree/main/scripts/trakt-mpv) that lets you add episodes to your Trakt watched history instead of checking in

* **[trakt-scrobble](https://github.com/dyphire/trakt-scrobble)**  
  Connects trakt.tv with mpv and automatically scrobbles movies/shows.


* **[recent-menu](https://github.com/natural-harmonia-gropius/recent-menu)**  
  Recently played menu for mpv integrated with uosc.

* **[reload](https://github.com/4e6/mpv-reload)**  
  When an online video is stuck during buffering or got slow CDN source, restarting often helps. This script provides automatic reloading of videos that didn't have buffering progress for some time, keeping the current time position. It also adds `Ctrl+r` keybinding to reload video manually.

* **[remember-props](https://github.com/zenwarr/mpv-config/blob/master/scripts/remember-props.lua)**  
  When a property changes, it saves it to restore on next start. Saved values are not file-specific. List of properties to save is configured in `script-opts/remember-props.conf` file.

* **[repl](https://github.com/rossy/mpv-repl)**  
  A REPL for input commands that is displayed on the video window.

* **[restore-subtitles](https://github.com/zenwarr/mpv-config/blob/master/scripts/restore-subtitles.lua)**  
  Saves selected subtitle tracks and visibility state to `saved-subs.json` file in config directory and restores them whenever file is loaded. Differs from `watch-later`-saved data in that it saves secondary subtitles too (and uses subtitle file paths instead of ids).

* **[review](https://gitlab.com/lvml/mpv-plugin-review)**  
  Allows to remove files viewed quickly from within mpv

* **[russian-layout-bindings](https://github.com/zenwarr/mpv-config/blob/master/scripts/russian-layout-bindings.lua)**  
  As mpv does not support shortcuts independent of the keyboard layout (https://github.com/mpv-player/mpv/issues/351), this script tries to workaround this issue for some limited cases with russian (йцукен) keyboard layout. Upon startup, it takes currently active bindings from `input-bindings` property and duplicates them for russian layout. You can adapt the script for your preferred layout, but it won't (of course) work for layouts sharing unicode characters with english.

* **[save-sub-delay](https://github.com/zc62/mpv-scripts/blob/master/save-sub-delay.lua)**  
  This script saves the sub-delay quantity for each file. When next time the file is opened, sub-delay is automatically restored.

* **[save-playlist](https://github.com/NaiveInvestigator/save-playlist)**  
  This script saves your playlist to the working directory of the mpv process.

* **[screenshotfolder](https://github.com/zydezu/mpvconfig/blob/main/scripts/screenshotfolder.lua)**  
  Place screenshots into folders for each video, along with timestamping them.

* **[seek-to](https://github.com/occivink/mpv-scripts#seek-tolua)**  
  Seek to an absolute timestamp specified via keyboard input.

* **[Serkio Tagger](https://github.com/SerkioTeam/Tagger)**  
  Annotate videos with tags while you watch.

* **[scale-win](https://gist.github.com/garoto/920b7456d2bdd8f48aa8e7094a12ce47)**  
  Restore old "window-scale" behavior, so to make "add window-scale +/-<value>" keybinds work again when any of the autofit-* options are defined.

* **[search-menu](https://github.com/stax76/mpv-scripts)**  
  A searchable menu to quickly find keybinds, commands, properties and audio/subtitle tracks.

* **[search-page](https://github.com/CogentRedTester/mpv-search-page)**  
  Allows users to search for keybinds, commands, options, and properties, and have the results display on the OSD. Good for reminding oneself about   forgotten keybinds without leaving the player.

* **[segment-linking](https://github.com/CogentRedTester/mpv-segment-linking)**  
  Adds support for matroska next/prev segment linking using the mkvinfo commandline tool.

* **[separator](https://github.com/pvpscript/mpv-separator)**  
  Interactively copy or move the videos you wanna keep from a given playlist.

* **[show-conf-osd](https://github.com/pierretom/show-conf-osd)**  
  Display configuration files on the OSD.

* **[show-filename](https://github.com/yuukidach/mpv-scripts)**  
  Show the name of the current playing file.

* **[show-stream-title](https://github.com/blue-sky-r/mpv/blob/master/scripts/show-stream-title.lua)**  
  Show OSD stream/channel title when switching the IPTV channels from m3u playlist.

* **[simple-loader](https://github.com/fhlfibh/simple-loader)**  
  (Linux) Browse dirs and files on OSD, and launch them with mpv.

* **[simple-mpv-webui](https://github.com/open-dynaMIX/simple-mpv-webui)**  
  Web-based remote control.

* **[skipchapters](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/scripts/avail/skipchapters.lua)**  
  Automatically skip chapters matching a given list of regular expressions (eg. "OP" or "Opening").

* **[skipsilence](https://github.com/ferreum/mpv-skipsilence)**  
  Increase playback speed during quiet parts of the file. Similar to the "Fast-forward during silence" feature of the NewPipe app.

* **[skiptofade](https://gist.github.com/bossen/3cfe86a6cdd61452dbb96865128fb327)**  
  Seeks forward until a black screen appears. Built to skip openings. Uses the lavfi blackdetect filter. 

* **[skiptosilence](https://github.com/detuur/mpv-scripts)**  
  This script skips to the next silence in the file. The intended use for this is to skip until the end of an opening or ending sequence, at which point there's often a short period of silence.
    *[skiptosilence](https://github.com/dyphire/mpv-scripts/blob/main/skiptosilence.lua): more powerful

* **[SmartSkip](https://github.com/Eisa01/mpv-scripts/#smartskip)**  
Automatically or manually skip opening, intro, outro, and preview, like never before. Jump to next file, previous file, and save your chapter changes! Much more explained in the link above.

* **[SimpleBookmark](https://github.com/Eisa01/mpv-scripts#simplebookmark)**  
  Bookmark with a [ctrl]+[b], then list and access your bookmarks with [b]. Assign your favorites to a keybind then access your favorites with that same keybind. Much more explained in the link above.

* **[SmartCopyPaste](https://github.com/Eisa01/mpv-scripts#smartcopypaste)**  
  Powerful copy paste features. Paste URL or local videos directly to mpv. Copy URL or currently playing video in mpv player then paste to access at a later time. Add videos to playlist simply by pasting. Much more explained in the link above.

* **[SmartCopyPaste_II](https://github.com/Eisa01/mpv-scripts#smartcopypaste_ii)**  
  Powerful copy paste and clipboard list features using a log file. Select, filter, and search from your clipboard list. Paste URL or local videos directly to mpv. Copy URL or currently playing video in mpv player then paste to access at a later time. Paste to access previously copied times of same video. Much more explained in the link above.

* **[smart-volume](https://github.com/stax76/mpv-scripts)**  
  Records the volume per file in order to restore it in future sessions. What is recorded and restored is the volume offset relative to the session average volume. For every song the last six sessions are recorded, the average of that is used.

* **[SimpleHistory](https://github.com/Eisa01/mpv-scripts#simplehistory)**  
  Powerful history features that logs videos that you opened into a log file along with the time you have reached on each video. Select, filter, and search from your history list, Optional resume by [ctrl]+[r] for all videos you have played. Much more explained in the link above.

* **[SimpleUndo](https://github.com/Eisa01/mpv-scripts#simpleundo)**  
  Simple undo feature. If you accidentally seek/jump to a different time in the video, press undo [ctrl]+[z] to return to your previous time and vice-versa. More details in the link above.

* **[sosc](https://github.com/christoph-heinrich/sosc)**  
An OSC supplement for OSC replacements. Provides the idle message and script messages from the original OSC.

* **[UndoRedo](https://github.com/Eisa01/mpv-scripts#undoredo)**  
  Undo and Redo feature for mpv. If you seek/jump to a different time in the video, press undo [ctrl]+[z] to linearly undo the seeks/jumps in the video, and press redo [ctrl]+[y] to linearly return to previous undo positions. More details in the link above.

* **[Sofalizer](https://gist.github.com/kevinlekiller/9fd21936411d8dc5998793470c6e3d16#file-sofalizer-lua)**  
  Simulates 7.1 surround sound to your headset. Get the sofa file from [here](https://sofacoustics.org/data/database/clubfritz/ClubFritz6.sofa)

* **[sopcast](https://github.com/Akemi/mpv-sopcast-hook)**  
  Adds support for sop:// urls.

* **[speed-transition](https://github.com/zenyd/mpv-scripts)**  
  Increases playback speed if a subtitle will not be displayed soon. Resumes normal speed just before the subtitle shows up.

* **[speed-transition-Audio](https://gist.github.com/bitingsock/e8a56446ad9c1ed92d872aeb38edf124)**  
  Experiment similar to [speed-transition](https://github.com/zenyd/mpv-scripts). changes playback speed based on volume thresholds.

* **[speed](https://github.com/oltodosel/mpv-scripts#speedlua)**  
  Changing speed based on regex of filename/path.

* **[speed](https://github.com/vflorelle/mpv-scripts#speed)**  
  Always show current playback speed on the OSD

* **[speed - adjusted timings](https://github.com/oltodosel/mpv-scripts#speed_osd3lua)**  
  Recalculates osd-msg3 timecodes with speed != 1

* **[splice](https://github.com/pvpscript/mpv-video-splice)**  
  A script that helps you create a video out of cuts made in the current playing video. 

* **[spotify](https://github.com/olivierlemoal/mpv-spotify-script)**  
  Add current playing title to an user defined Spotify playlist.

* **[srt-resegment](https://github.com/VimWei/mpv-config/blob/main/scripts/srt-resegment.lua)**  
  Resegment srt by synchronize plain text with whisper's word-level timestamps JSON.

* **[submpv](https://github.com/yassin-l/submpv)**  
  submpv is a python script to automate downloading and loading subtitle from subscence. 

* **[sub](https://github.com/vflorelle/mpv-scripts#sub)**  
  Select subtitle by id via input box (Windows)

* **[stopCache](https://gist.github.com/bitingsock/19c3094cc8680bb7b97b09aaf7d11176)**  
  stops the demuxer from downloading more if it is already past --end 

* **[subit](https://github.com/wiiaboo/mpv-scripts/blob/master/subit.lua)**  
  Yet another script for downloading subtitles using subliminal. Supports better customization of options, such as easy language selection, authentication for providers that need it, and support for URLs.

* **[subselect Tk](https://github.com/zenyd/mpv-scripts)**  
  Download subtitles with a GUI - select the one you want and automatically load them up in mpv. Supports searching for arbitrary names and different subtitle languages. Works on Windows and Linux, possibly macOS.

* **[sub-assrt](https://github.com/dyphire/mpv-sub-assrt)**  
  Download Chinese subtitles from assrt.

* **[sub-cut](https://github.com/kelciour/mpv-scripts/blob/master/sub-cut.lua)**  
  Extract a part of the video as audio or video with subtitles.

* **[sub-bilingual](https://github.com/kelciour/mpv-scripts/blob/master/sub-bilingual.lua)**  
  Generate bilingual subtitles.

* **[sub-bookmarks](https://github.com/kelciour/mpv-scripts/blob/master/sub-bookmarks.lua)**  
  Save current position and subtitles in .txt file.

* **[sub-export](https://github.com/kelciour/mpv-scripts/blob/master/sub-export.lua)** ⚠️ *original, outdated*  
  **[sub_export](https://github.com/dyphire/mpv-scripts/blob/main/sub_export.lua)** *fork, updated*  
  Extract selected subtitles from .mkv file.

* **[sub-fastwhisper](https://github.com/dyphire/mpv-sub-fastwhisper)**  
  Generate srt subtitles through voice transcription using faster-whisper.

* **[subtitle-lines](https://github.com/christoph-heinrich/mpv-subtitle-lines)**  
  List and search subtitle lines of the selected subtitle track.

* **[sub-not-forced-not-sdh](https://github.com/pzim-devdata/mpv-scripts)**
  Prevents the selection of FORCED and SDH subtitles when you start playing a video with MPV:
   - Forced subtitles are subtitles that are displayed only for sections of the video that contain non-dialogue elements such as signs, captions, or foreign language translations.
   - SDH means Subtitles for the Deaf or Hard of Hearing.
  By modifying this script (see the README), you can also automatically select a subtitle language.

* **[sub-playback](https://github.com/kelciour/mpv-scripts/blob/master/sub-playback.lua)**  
  Add interactive move, i.e. automatically pause at the end of the fragment with option to continue playback or replay it again with or without subtitles.

* **[sub-replay](https://github.com/kelciour/mpv-scripts/blob/master/sub-replay.lua)**  
  Replay previous sentence.

* **[sub-search](https://github.com/kelciour/mpv-scripts/blob/master/sub-search.lua)**  
  Search for phrase in subtitles and skip to it.

* **[subtitle-search](https://github.com/zenwarr/mpv-config/blob/master/scripts/subtitle-search.lua)**  
  Script to search for a phrase inside an active subtitle. Supports secondary subtitles too. Displays matched lines in OSD list, takes `sub-delay` into account and allows searching for Unicode text in utf8 subtitle files. Supports embedded and youtube-provided remote subtitles.

* **[sub-select](https://github.com/CogentRedTester/mpv-sub-select)**  
  An advanced subtitle track selector that utilises the current audio language, and the language and titles of the subtitle tracks. 

* **[sub-sentences](https://github.com/kelciour/mpv-scripts/blob/master/sub-sentences.lua)**  
  Generate subtitles with sentences.

* **[sub-voracious](https://github.com/kelciour/mpv-scripts/blob/master/sub-voracious.lua)**  
  Reading and listening practice.

* **[sub-pause](https://github.com/Ben-Kerman/mpv-sub-scripts)**  
  Automatically pause just before the end of each subtitle line. Also allows replaying the currently active line.

* **[sub-skip](https://github.com/Ben-Kerman/mpv-sub-scripts)**  
  Automatically skip parts of a video that don't contain any subtitles. Does so by either fast-forwarding or seeking.

* **[subs2srs](https://github.com/kelciour/mpv-scripts/blob/master/subs2srs.lua)**  
  Automatically add new card in Anki with audio, picture and text.

* **[sub-transition](https://github.com/Ajatt-Tools/sub_transition)**  
  Speed up playback when no subtitles are visible. 

* **[stats](https://github.com/Argon-/mpv-stats/)**  
  Display some statistics about the currently played file on-screen.

* **[streamcache](https://gitlab.com/lvml/mpv-plugin-streamcache)**  
  Provides for more network-glitch-robust caching of live streams by adjusting replay speed.

* **[streamsave](https://github.com/Sagnac/streamsave)**  
  Save live streams and clip videos without encoding.

* **[sview](https://github.com/he2a/mpv-scripts)**  
  A lightweight script that displays all loaded shaders in a clean format. It suppresses the default OSD message, allowing the custom list to be viewed by toggling it or when changing shaders.

* **[switch-both-audio](https://github.com/70sh1/mpv-switch-both-audio)**  
  Switch between playing one or two audio tracks simultaneously upon file load or with a hotkey.

* **[tethys](https://github.com/Zren/mpv-osc-tethys)**  
  An OSC UI replacement for MPV with icons from the bomi video player. Also contains thumbnail preview and a picture-in-picture button.

* **[thumbfast](https://github.com/po5/thumbfast)**  
  High-performance on-the-fly thumbnailer for mpv. Can integrate with any UI/custom osc.lua.

* **[time](https://github.com/mustaqimM/mpv-scripts/blob/master/time.lua)**  
  Shows the current time or the time at which playback will end.

* **[timer](https://github.com/AdamD2/mpv-timer)**  
  Allows the user to set a starting time and an ending time and see the time elapsed between those points with millisecond precision.

* **[trackselect](https://github.com/po5/trackselect)**  
  Automatically select your preferred tracks based on title.

* **[track-list](https://github.com/dyphire/mpv-scripts/blob/main/track-list.lua)**  
  Interractive track-list menu.

* **[tree-profiles](https://github.com/fbriere/mpv-scripts/blob/master/scripts/tree-profiles.lua)**  
Automatically apply profiles to certain directories or files.

* **[trim.lua](https://github.com/aerobounce/trim.lua)**  
Adds trim mode for mpv — turn mpv into Lossless Audio / Video Editor.

* **[torrserver_hook.lua](https://github.com/eNV25/mpv-torrserver-hook)** Allows for playback of media from the BitTorrent network using [TorrServer](https://github.com/YouROK/TorrServer).

* **[total_playtime](https://github.com/oltodosel/mpv-scripts/blob/master/total_playtime.lua)**  
Shows total playtime of current playlist.

* **[trueautosub](https://github.com/fullmetalsheep/mpv-iina-scripts)**  
Improved fork of autosub, Automatically downloads subtitles if not present using **subliminal**. (osx/linux only)

* **[tts-subs](https://github.com/jgreco/mpv-scripts/blob/master/tts-subs.lua)**  
Use voice synthesis to read subtitles out-loud (Currently uses `say` on MacOS.  Could be adapted to use espeak.  PR for windows support welcome.)

* **[tv-output](https://github.com/blue-sky-r/mpv/blob/master/scripts/tv.lua)**  
  (Linux) TV output handling - activate on mpv playback and deactivate on mpv shutdown.

* **[use-cpu](https://github.com/422658476/MPV-EASY-Player/blob/master/portable-data/scripts/use-cpu.lua)**  
  If the width of the video is greater than 3000 or the height of the video is greater than 2000, it will automatically switch back to using cpu decoding. If you feel inappropriate, you can modify the default values of the video width and height.

* **[user-data-loader](https://github.com/CogentRedTester/mpv-user-data-loader)**  
Allows the `user-data` property to be set at launch using config files and changed using profiles and script-opts during runtime.

* **[unseen-playlistmaker](https://github.com/donmaiq/unseen-playlistmaker)**  
  Keeps track of watched files locally, and creates playlists of unwatched files.

* **[uosc](https://github.com/tomasklaen/uosc)**  
  Feature-rich minimalist proximity-based UI replacement. ([Preview](https://user-images.githubusercontent.com/47283320/195073006-bfa72bcc-89d2-4dc7-b8dc-f3c13273910c.webm))

* **[uosc_danmaku](https://github.com/Tony15246/uosc_danmaku)**

  Loads DanDanPlay danmaku in MPV player, based on the uosc UI framework and DanDanPlay API.([Preview video](https://github.com/user-attachments/assets/86717e75-9176-4f1a-88cd-71fa94da0c0e))

* **[videoclip](https://github.com/Ajatt-Tools/videoclip)**  
  Create video and audio clips with mpv. Supports `mp4` and `webm` formats.

* **[visualizer](https://github.com/mfcc64/mpv-scripts/blob/master/visualizer.lua)**  
  Various audio visualization.

* **[vlcaspectratio](https://github.com/kism/mpvscripts/blob/main/scripts/vlcaspectratio.lua)**  
  Implements a VLC style aspect ratio hotkey 'a' that stretches the video to different aspect ratios.

* **[vlccrop](https://github.com/kism/mpvscripts/blob/main/scripts/vlccrop.lua)**  
  Implements a VLC style crop hotkey 'c' that cycles through crop settings, useful for cropping letter-boxed or pillar-boxed content.

* **[vo_battery](https://gist.github.com/ekisu/04924e899648e84f2e18)**  
  (Linux) Choose the VO based on if the laptop is on battery or not.

* **[vr-reversal](https://github.com/dfaker/VR-reversal)**  
   View 3D side-by-side video as a 2D video, allows you to look around and zoom within the video, logs the head motions to a file for later rendering out to a 2D video with ffmpeg.

* **[waveform](https://github.com/MikelSotomonte/mpv-waveform/tree/main)**  
   Displays a waveform of the video in real-time using [ffmpeg waveforms](https://trac.ffmpeg.org/wiki/WaveformMonitor). ([Preview](https://cdn.discordapp.com/attachments/446054699439882250/1001900605557710888/mpv-shot0002.jpg))  
   Based on detuur and microraptor's [histogram script](https://github.com/detuur/mpv-scripts), that can also be found on this list.

* **[writename](https://github.com/paradox460/mpv-scripts/tree/master/writename)**
  Write the currently playing filename/path to a file, optionally skipping/removing from current playlist and muting.

* **[webm](https://github.com/ekisu/mpv-webm)**  
  Simple WebM maker for mpv, with no external dependencies.

* **[when-to-loop](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/scripts/when-to-loop.lua)**  
  Intelligently decide when mpv should loop, i.e. while shuffling or while playing a short file.

* **[whisper-subs](https://github.com/GhostNaN/whisper-subs)**  
  A lua script that generates subtitles at runtime with whisper.cpp on Linux.

* **[xfce-genmonify](https://github.com/budRich/mpv-xfce-genmonify)**  
  update a [xfce4-panel](https://docs.xfce.org/xfce/xfce4-panel/start) [genmon](https://docs.xfce.org/panel-plugins/xfce4-genmon-plugin/start) plugin that is set up with [genmonify](https://github.com/budlabs/genmonify) to display the currently playing media file and elpapsed or remaining time in xfce4-panel.

* **[xrandr](https://gitlab.com/lvml/mpv-plugin-xrandr)**  
  Automatically sets the display refresh rate to the one best suitable for the video played
  * **[mpv-kscreen-doctor](https://gitlab.com/smaniottonicola/mpv-kscreen-doctor)**
  A similar project that also works for KDE Plasma Wayland sessions

* **[xscreensaver](https://gist.github.com/elenril/f8ff9475a7882b7a16cdd723c7dce150)**  
   Disables XScreensaver while video playback is active, a replacement for heartbeat-cmd.

* **[Yomichampv](https://github.com/laelnasan/yomichampv)**  
  A simple solution for integration with Yomichan - a browser-based japanese dictionay.

* **[youtube-download](https://github.com/cvzi/mpv-youtube-download)**  
  Download youtube video or audio with one key press

* **[youtube-quality](https://github.com/jgreco/mpv-youtube-quality)** ⚠️ *original, outdated*  
  **[quality-menu](https://github.com/christoph-heinrich/mpv-quality-menu)** *fork, updated*  
  A menu for changing the streamed video and audio quality (ytdl-format) on the fly. [preview](https://github.com/christoph-heinrich/mpv-quality-menu/raw/master/preview.jpg)

* **[youtube-search](https://github.com/CogentRedTester/mpv-scripts/blob/master/youtube-search.lua)**  
  A script that allows users to search youtube and open results from within mpv. Requires a couple of extra API scripts, along with curl and a personal youtube API key.

* **[youtube-upnext](https://github.com/cvzi/mpv-youtube-upnext)**  
  A menu for (auto) playing youtube's "up next"/recommended videos, that show up on the right side on the website.

* **[youtube-queue](https://github.com/ksyasuda/mpv-youtube-queue)**  
  A script that implements the YouTube 'Add to Queue' functionality for mpv. Allows adding video urls to the queue from the clipboard, and provides a menu for interacting with the queue.

* **[ytdl-preload](https://github.com/bitingsock/ytdl-preload)**  
  Precache the next entry in your playlist if it is a network source by downloading it to a temp file ahead of time. Updated to download all streams in parallel so you can watch it while it downloads.

* **[ytsub](https://github.com/Idlusen/mpv-ytsub/)**  
  Load automatic captions from Youtube, can select language interactively or automatically.


* **[zones](https://github.com/wiiaboo/mpv-scripts/blob/master/zones.lua)**  
  Handles commands depending on where the mouse pointer is at, mostly for mouse wheel handling.


## User Shaders

A guide for how to write user shaders [can be found here](https://libplacebo.org/custom-shaders/).

* **[A-Pack](https://github.com/butterw/bShaders/tree/master/A-pack)**  
  Shaders pack for quick Adjustment of (web) video: brightness/contrast curves (tooDark, tooBright, bShadows, bDim, etc.) and color (vibrance, skintones, Black&White). Runs on integrated graphics.

* **[Anime4K](https://github.com/bloc97/Anime4K)**  
  A series of shaders designed to scale and enhance anime. Includes shaders for line sharpening, artefact removal, denoising, upscaling, and more.

* **[LumaSharpenHook](https://gist.github.com/voltmtr/8b4404b4e23129b226b9e64863d3e28b)**  
  A sharpen filter similar to using Unsharp Mask in Photoshop ported from SweetFX shader pack.

* **[SSimDownscaler, SSimSuperRes, Krig, Adaptive Sharpen, etc.](https://gist.github.com/igv)**  
  * SSimDownscaler: Perceptually based downscaler.
  * SSimSuperRes: The aim of this shader is to make corrections to the image upscaled by mpv built-in scaler (removes ringing artifacts, restores original sharpness, etc).
  * Krig: Chroma scaler that uses luma information for high quality upscaling.

* **[Noise](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/shaders/noise.glsl)**  
  Simplistic filter that adds a tunable amount of uniform white noise to the output.

* **[Film Grain v1](https://raw.githubusercontent.com/haasn/gentoo-conf/xor/home/nand/.mpv/shaders/filmgrain.glsl)** and **[Film Grain v2](https://raw.githubusercontent.com/haasn/gentoo-conf/xor/home/nand/.mpv/shaders/filmgrain-smooth.glsl)**  
  Two configurable shaders for applying gaussian-weighted white noise to the image. v2 is a smoothed version of v1, which uses an extra gaussian blur pass to shift the grain frequency spectrum. Both versions can trivially be adapted to add film grain to other channels besides `LUMA` by just adding it to the list of hooks.

* **[Antiringing](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/shaders/antiring.hook)**  
  This is an antiringing filter that works by clamping to the local neighbourhood. Sort of inspired by the mpv built-in antiringing algorithm, but it's extended in such a way that it also works well for polar (EWA) filters, which the mpv built-in algorithm does not support at all.

* **[nnedi3 and ravu](https://github.com/bjin/mpv-prescalers/tree/master)**  
  User shaders for prescaling.

* **[FSRCNN](https://github.com/igv/FSRCNN-TensorFlow/releases)**  
  Prescaler based on layered convolutional networks.

* **[un360](https://gist.github.com/tesu/196db5421559de3e9555d4f9da9d847d)**  
  Converts equirectangular 360 degree video to be watchable, at a fixed perspective.

* **[acme-0.5x](https://gist.github.com/bjin/15f307e7a1bdb55842bbb663ee1950ed)**  
  Simple 0.5x downscaler for mpv, useful for 4K video playback on FHD screen with iGPU (bypass chroma upscaling and color conversion in 4K resolution).

* **[Nonlinear stretch](https://gist.github.com/sarahzrf/c9909aee70e3656895820f20ac395956)**  
  Non-linear stretch scaling. use with `--no-keepaspect`.

* **[lensfix](https://gist.github.com/bjin/33ffbc0fbdbc00aefa21b2e44bbd27cd#file-lensfix-hook)**  
  Fix radial distortion commonly found in wide angle action cameras.

* **[hyperview](https://gist.github.com/bjin/399cb23818ad210941725ef768893499)**  
  Dynamic stretching filter aiming to bring effects similar to GoPro SuperView.

* **[NLS#](https://github.com/NotMithical/mpv-config/blob/main/Personal/portable_config/shaders/AspectRatio/NLS%23.glsl)**  
  Tunable bidirectional nonlinear stretching with optional cropping and padding.

* **[FidelityFX CAS](https://gist.github.com/agyild/bbb4e58298b2f86aa24da3032a0d2ee6)**  
  AMD FidelityFX Contrast Adaptive Sharpening (CAS) provides a mixed ability to sharpen and optionally scale an image. The algorithm adjusts the amount of sharpening per pixel to target an even level of sharpness across the image. Areas of the input image that are already sharp are sharpened less, while areas that lack detail are sharpened more. This allows for higher overall natural visual sharpness with fewer artifacts.


* **[FidelityFX FSR](https://gist.github.com/agyild/82219c545228d70c5604f865ce0b0ce5)**  
  AMD FidelityFX Super Resolution is a spatial upscaler: it works by taking the current anti-aliased frame and upscaling it to display resolution without relying on other data such as frame history or motion vectors. At the heart of FSR is a cutting-edge algorithm that detects and recreates high-resolution edges from the source image. Those high-resolution edges are a critical element required for turning the current frame into a “super resolution” image. FSR provides consistent upscaling quality regardless of whether the frame is in movement, which can provide quality advantages compared to other types of upscalers.

* **[NVIDIA Image Scaling](https://gist.github.com/agyild/7e8951915b2bf24526a9343d951db214)**  
  NVIDIA Image Scaling is a spatial scaling and sharpening algorithm. The scaling algorithm uses a 6-tap scaling filter combined with 4 directional scaling and adaptive sharpening filters, which creates nice smooth images and sharp edges. In addition, an adaptive-directional sharpening-only algorithm is available. The directional scaling and sharpening algorithm is named NVScaler while the adaptive-directional-sharpening-only algorithm is named NVSharpen.

* **[Post upscale unsharp masking](https://github.com/garamond13/unsharp_masking.glsl)**  
  This is mpvs original image sharpening algorithm ported into the shader, in order to work only after upscaling is done.

* **[nlmeans, hdeband, & more](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/shaders/)**  
  * nlmeans is a featureful implementation of the Non-local Means algorithm, it does both denoising and adaptive sharpening
  * hdeband is an implementation of a debanding algorithm that blurs homogeneous regions together

* **[Alt Scale](https://github.com/garamond13/alt-scale)**  
  An alternative to mpv's built in scaling. It can be slightly faster than built in scaling with equivalent quality.

* **[Unsharp mask and Gaussian blur](https://github.com/garamond13/Unsharp-mask-and-Gaussian-blur)**  
  A 2 pass unsharp mask and a 2 pass gaussian blur. Similar to those in Photoshop, Image Magick, Gimp, etc.

* **[2D Image Resampling](https://github.com/garamond13/2D-Image-Resampling)**  
  2D Image Resampling is a general resampling algorithm made for experimental / testing use.

* **[Jinc](https://github.com/garamond13/Jinc)**  
  Jinc based image scaling. Similar to mpv's ewa or polar.

* **[Pixel Clipper](https://github.com/Artoriuz/glsl-pixel-clipper)**  
  Simple anti-ringing filter based on pixel clipping/clamping.

* **[JointBilateral & FastBilateral](https://github.com/Artoriuz/glsl-joint-bilateral)**  
  Chroma upsamplers that use the luma plane as a guide to achieve sharper transitions without introducing any ringing.

* **[Chroma from Luma Prediction](https://github.com/Artoriuz/glsl-chroma-from-luma-prediction)**  
  Chroma upsamplers based on least-squares linear regression.

* **[ArtCNN](https://github.com/Artoriuz/ArtCNN)**  
  Luma doublers trained on Manga109.

* **[CuNNy](https://github.com/funnyplanter/CuNNy)**  
  Cute and funny CNN-based upscaler optimized for anime.

* **[AniSD ArtCNN](https://github.com/Sirosky/Upscale-Hub/releases/tag/AniSD-ArtCNN)**  
  AniSD ArtCNN is for standard definition anime content.

* **[Ani4K v2 ArtCNN](https://github.com/Sirosky/Upscale-Hub/releases/tag/Ani4k-v2-ArtCNN)**  
  Ani4K v2 targets modern anime, from high quality Bluray to crappy WEB releases, for upscaling to either 2K or 4K.

## VapourSynth Scripts

* **[mvtools](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/filters/mvtools.vpy)**  
  Use [MVTools](https://github.com/dubhater/vapoursynth-mvtools)'s BlockFPS function to perform motion interpolation on the video in realtime.

* **[nnedi3](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/filters/nnedi3.vpy)**  
  Use [NNEDI3](https://github.com/dubhater/vapoursynth-nnedi3) to double the resolution of the video. This always performs a single doubling. Note that the vapoursynth-nnedi3 filter is so slow that this practically can't be used in realtime, so it's not much use in practice. 

* **[flash3kyuu](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/filters/flash3kyuu.vpy)**  
  Use [flash3kyuu](https://github.com/SAPikachu/flash3kyuu_deband) to deband the video, with reasonable (mildly grainy) default settings. 
**Obsolete:** mpv now ships with a similar debanding filter as shader.


## C Plugins

* **[mpv-mpris](https://github.com/hoyon/mpv-mpris)**  
  Adds support for MPRIS2 protocol

* **[mpv-libunity](https://github.com/mrlotfi/mpv-libunity)**  
  Shows a progress bar on your panel/dock using libunity

* **[mpv-omniGlass](https://github.com/guarapicci/mpv-omniGlass)**  
  Touchpad gestures for mpv

* **[mpv-rpc](https://github.com/ryze312/mpv-rpc)**  
  Discord Rich Presence integration for mpv written in Rust. Also displays cover art from MusicBrainz archive!

* **[shutup](https://github.com/AN3223/dotfiles/blob/master/.config/mpv/scripts/shutup.c)**  
  Set --quiet when stderr or stdout aren't connected to a terminal

* **[mpv-limited-autoload](https://github.com/glubsy/mpv-limited-autoload)**  
  Auto-load files in a lazy way by limiting how many are loaded into playlist at once

* **[kde-do-not-disturb](https://gitlab.com/smaniottonicola/kde-do-not-disturb)**  
  Disable the notifications while mpv is running

* **[kde-night-color](https://gitlab.com/smaniottonicola/kde-night-color)**  
  Disable Night Color while mpv is running

* **[mpv_inhibit_gnome](https://github.com/Guldoman/mpv_inhibit_gnome)**  
  Prevent screen blanking on GNOME while content is playing

* **[mpv-menu-plugin](https://github.com/tsl0922/mpv-menu-plugin)**  
  Context menu, file dialog, clipboard support for mpv on Windows

* **[mpv-debug-plugin](https://github.com/tsl0922/mpv-debug-plugin)**  
  A debug tool for mpv script developers, with GUI support for properties and console.

## Other

* **[play-with](https://github.com/grmat/play-with)**  
  A WebExtension that can open a video stream on a web page with an external player.

* **[playphrase](https://github.com/kelciour/playphrase)**  
  Search and play phrases from movies and audiobooks.

* **[mpv_sponsorblock_minimal](https://codeberg.org/jouni/mpv_sponsorblock_minimal)**  
  Minimal version of sponsorblock extension.

* **[mpvc-tui](https://github.com/gmt4/mpvc)**  
  mpc command-line and tui for mpv.

* **[mpvclip / mpvival / mpvloop](https://github.com/o770/mpvclip-mpvival-mpvloop)**  
  Run MPV with options for loops and playback start and end times set according to a pattern or intervals of the total duration of a file.

* **[http-ytproxy](https://gist.github.com/ftk/253347b2c9a53bbd6087f086970106b6)**  
  Simple MitM http proxy to modify Range http headers. Can be used to speed up youtube videos in mpv.

* **[mpvf](https://gist.github.com/o770/98b00f5c54e4e134310834e67838b1fa)**  
  Run MPV on files found with GNU Find by including and excluding pathname patterns and setting the depth levels in the directory tree.

* **[mpvif](https://github.com/layercak3/mpvif)**  
  A wayland VO patch and C plugin which forwards keyboard and mouse input to a headless compositor for playing 2D games with upscaling mpv user shaders.
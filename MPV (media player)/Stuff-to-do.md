If you're new to the project, and want to help, here are some suggestions what to work on. You're also welcome to come up with your own ideas.

- We need a community manager. This person would reduce the need for developers to deal with day to day operations, such as communicating with users, adjusting the website and documentation, triaging bugs and feature requests, and other non-developer tasks. Anyone volunteering to help with any of this is welcome too.

- Come up with a way how mpv user scripts (also shaders etc.) can be packaged and updated in a reasonable way. The goal is having a way to automatically manage these scripts.

- Replace Xlib usage with XCB. (Basically writing a new backend for X11, based on XCB instead of Xlib. Preferably without using the old code, so it can be LGPL.)

- Make the gamma curve definitions and tone mapping functions in video_shaders.c work for full-range values, and remove the force clip to [0,1]

- Convert the libmpv documentation from in-place doxygen to external documentation (the way vapoursynth does it might be a good idea).

For all of these you should ask on #mpv-devel for help and guidance.
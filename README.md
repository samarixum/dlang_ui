Dlang UI
========
Cross platform GUI for D. Widgets, layouts, styles, themes, unicode, i18n, OpenGL based acceleration.

copy of buggins/dlangui
GitHub page: [https://github.com/buggins/dlangui](https://github.com/buggins/dlangui)

Project site: [http://buggins.github.io/dlangui](http://buggins.github.io/dlangui)
API Documentation: [http://buggins.github.io/dlangui/ddox](http://buggins.github.io/dlangui/ddox)
Wiki: [https://github.com/buggins/dlangui/wiki/Home](https://github.com/buggins/dlangui/wiki/Home)

Main features:

* Crossplatform (Win32, OSX, Linux and Android are supported in current version)
* Mostly inspired by Android UI API (layouts, styles, two phase layout, ...)
* Supports highly customizable UI themes and styles
* Supports internationalization
* Hardware acceleration using OpenGL (when built with version USE_OPENGL)
* Fallback to pure Win32 API / SDL / X11 when OpenGL is not available (e.g. opengl dynamic library cannot be loaded)
* Actually it's a port (with major refactoring) of GUI library for cross platform OpenGL based implementation of Cool Reader app project from C++.
* Non thread safe - all UI operations should be preformed in single thread
* Simple 3d engine - allows to embed 3D scenes within GUI

D compiler versions supported
-----------------------------

Needs DMD frontend 2.100.2 or newer to build

Win32 builds
------------

* Under windows, uses SDL2 or Win32 API as backend.
* Optionally, may use OpenGL acceleration
* Uses Win32 API for font rendering.
* Optinally can use FreeType for font rendering.
* Executable size for release Win32 API based build is 830K.


Build and run demo app using DUB:
```sh
git clone --recursive https://github.com/buggins/dlangui.git
cd dlangui/examples/example1
dub run --build=release
```

To avoid showing console window add win_app.def file to your package source directory and add line to your dub.json.

win_app.def:
```json
"sourceFiles": ["$PACKAGE_DIR/src/win_app.def"]
```
dub.json:
```json
"sourceFiles-windows": ["$PACKAGE_DIR/src/win_app.def"],
```

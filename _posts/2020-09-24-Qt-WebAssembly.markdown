---
layout: post
title: "Qt WebAssembly Examples"
date: 2020-09-24
---

So happy that [WebAssembly](https://webassembly.org) and [emscripten](https://emscripten.org) has matured to the point that [Qt](https://qt.io) is easily able to deploy apps to the browser.  They provide several [examples](https://www.qt.io/qt-examples-for-webassembly).  I've followed their [wiki](https://wiki.qt.io/Qt_for_WebAssembly) using Qt 5.15.1 with emsk 2.0.2 and sucessfully compiled and ran [these examples](https://ericfontaine.io/qt) you can try out in the browser:

* [Hello Window]({% link qt/hellowindow/index.html %}) test to render a 3D opengl object.
* [Text Editor]({% link qt/texteditor/index.html %}) minimal text editor (though typing doesn't work!)
* [QML Oscilloscope]({% link qt/qmloscilloscope/index.html %}) renders sine waves, resizable.

Qt is currently actively developing this feature, see status of:
* <https://github.com/msorvig/qt-webassembly-examples> updates with new examples.
* <https://msorvig.github.io/qt-webassembly-examples> contains live versions of some.
* <https://bugreports.qt.io/browse/QTBUG-63917> is the "EPIC" bug report reporting progress!

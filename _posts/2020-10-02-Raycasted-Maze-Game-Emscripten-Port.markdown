---
layout: post
title: "Raycasted Maze Game ported to Emscripten with SDL"
date: 2020-10-02
---

In my previous [Qt WebAssembly post]({% post_url 2020-09-24-Qt-WebAssembly %}), I showed some examples of Qt demos in the browser. Though Qt emscripten support is currently shall we say "experimental/beta-quality", however the good news is that [SDL](https://www.libsdl.org) is pretty mature at this point.

I decided to test out porting a [raycasted](https://en.wikipedia.org/wiki/Ray_casting) maze demo I made back in Feb 25 - March 3 of 2002 using [OpenPTC](https://sourceforge.net/p/openptc/wiki/Home/), by converting the graphics, windowing, & keyboard input calls to SDL. It was mostly straightforward, except there were particularlies with resizing the html page's canvas size (see the code inside of #ifdef __EMSCRIPTEN__). I also decided to finalize that demo into a simple game, whereby you must visit every wall of the procedurally-generated random maze within a timelimit. The code is at <https://github.com/ericfont/maze> and you can run it in your browser at:

* [Covid Shopping Maze Game]({% link covidshopping/maze.html %})

Control movement with your keyboard: UP=forward, DOWN=backward, LEFT/RIGHT=turn left/right.
Report any issues to <https://github.com/ericfont/maze/issues>.

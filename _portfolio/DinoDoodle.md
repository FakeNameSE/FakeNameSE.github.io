---
title: "DinoDoodle"
excerpt: "A cross-platform dinosaur themed drawing app"
header:
  overlay_image: /assets/images/dinoDoodle_banner.jpeg
  teaser: /assets/images/dinoDoodle_teaser_and_sidebar.png
sidebar:
  - title: "Role"
    image: /assets/images/dinoDoodle_teaser_and_sidebar.png
    image_alt: "logo"
    text: "Coder and designer"
  - title: "Responsibilities"
    text:  "I dreamt up, designed, and built this!"
gallery:
  - url: /assets/images/dinoDoodle_demo.gif
    image_path: assets/images/dinoDoodle_demo.gif
    alt: "DinoDoodle demo screen recording"
  - url: /assets/images/dinoDoodle_example_doodle.png
    image_path: assets/images/dinoDoodle_example_doodle.png
    alt: "DinoDoodle example drawing"
---
*Header from [Wallpaper Flare](https://www.wallpaperflare.com) and paint brush icon from [Videoplasty.com [CC BY-SA 4.0]](https://creativecommons.org/licenses/by-sa/4.0).*

## What Is This?
This was developed as my final project for the programming studio class CS 126
at the University of Illinois at Urbana-Champaign. It is a drawing app with a
few nice extra features written to follow good coding style (one of that class'
main goals) to the best of my ability.

Features of this app beyond the bare bones of a drawing app include:
  * A two window design with the toolbox and canvas separated.
  * Drag and drop file loading and the ability to load a background image to draw over.
  * Multiple brushes (with adjustable color and width).
  * An interface to ply the user with an assortment of random dinosaur facts
  that they can consult for inspiration.

## Screenshots!
{% include gallery caption="Screenshots of app. From left to right: splash, login, group selection, chat, input dialog, account creation with input validation error, and chat creation screens." %}

## Technical Information!
DinoDoodle is built with:
  * C++ with OpenFramworks for the GUI.
  * OpenFramworks for the canvas framebuffer rendering and the plugin ofxGui for
  the GUI.
  * JsonCPP to parse the dinosaur JSON data.

## Awards
None, but who doesn't like drawing apps and dinosaurs!

The code is open source, and you can check it out on Github [here](https://github.com/FakeNameSE/iFeel).

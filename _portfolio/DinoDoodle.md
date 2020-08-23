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

## More Information and Challenges Encountered
A more complete explanation of the project, its proposal, and a log detailing my work on it are all available and can be found in the `README.md`, `PROPOSAL.md`, and `DEVELOPMENT.md` files in the [project repository](https://github.com/FakeNameSE/CS_126_Final_Project). `DEVELOPMENT.md` does a pretty good job of documenting chronologically in a fun style my approach to the project, the issues encountered, and how I solved them.

## Screenshots!
{% include gallery caption="Screenshots of DinoDoodle. From left to right: screen recording of demo and beautiful example drawing of a dinosaur." %}

## Technical Information!
DinoDoodle is built with:
  * C++ with OpenFramworks for the GUI.
  * OpenFrameworks for the canvas framebuffer rendering and the plugin ofxGui for
  the GUI.
  * JsonCPP to parse the dinosaur JSON data.

## Awards
None, but who doesn't like drawing apps and dinosaurs!

The code is open source, and you can check it out on Github [here](https://github.com/FakeNameSE/CS_126_Final_Project).

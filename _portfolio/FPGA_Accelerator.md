---
title: "FPGA Accelerator"
excerpt: "Offloading computations to custom hardware."
header:
  overlay_image: /assets/images/fpga_accelerator_banner.jpg
  teaser: /assets/images/fpga_accelerator_teaser_and_sidebar.png
sidebar:
  - title: "Role"
    image: /assets/images/fpga_accelerator_teaser_and_sidebar.png
    image_alt: "logo"
    text: "Team member"
  - title: "Responsibilities"
    text:  "I proposed the initial project and worked on both the hardware and software for it."
gallery:
  - url: /assets/images/fpga_accelerator_demo.png
    image_path: assets/images/fpga_accelerator_demo.png
    alt: "Demo of FPGA Accelerator XORing two bytes."
  - url: /assets/images/fpga_accelerator_lighting_up.png
    image_path: assets/images/fpga_accelerator_lighting_up.png
    alt: "FPGA LEDs lighting up in response to byte received while debugging."
  - url: /assets/images/fpga_accelerator_fsm.png
    image_path: assets/images/fpga_accelerator_fsm.png
    alt: "Finite state machine upon which the control circuit of the FPGA is based."
  - url: /assets/images/fpga_accelerator_block_diagram.png
    image_path: assets/images/fpga_accelerator_block_diagram.png
    alt: "Block diagram of the components of the FPGA's datapath."
---

*Attributions:*
- *Header attribution: [ZeptoBars](https://commons.wikimedia.org/wiki/File:Altera-cyclone-1-fpga-HD.jpg) / [CC BY](https://creativecommons.org/licenses/by/3.0)*
- *FPGA diagram on sidebar and portfolio page attribution: Modified from [No machine-readable author provided. Johnteslade~commonswiki assumed (based on copyright claims).](https://commons.wikimedia.org/wiki/File:Fpga_structure.svg) / Public domain*

## What Is This?
This was developed as a team project for the final project of the systems programming honors class CS 296-41
at the University of Illinois at Urbana-Champaign. The project goal was to offload certain computations to an FPGA to accelerate those operations. It was inspired by the rise of domain specific acceleration in computer architecture. We accomplished this by developing three components.
1. A datapath and control circuit for the FPGA capable of receiving data from a computer over UART, performing a computation with it, and transmitting the result back.
2. A Character device driver kernel module to communicate with the FPGA.
3. A user space C library which wrapped around the kernel module to facilitate using the FPGA within existing code by just calling a single function to perform an operation on the FPGA.

## A Few of the Challenges Encountered
Over the course of this project, my teammates and I learned quite a lot about just how tough hardware is. We spent plenty of time debugging our UART modules so that the FPGA could send and receive bytes while still having enough time to learn about systems programming with serial protocols and basic Linux kernel module (specifically character device drivers) development. Ultimately, we managed to get a fully working system capable of sending two bytes to the FPGA, XORing them, and sending them back.

## Pictures!
{% include gallery caption="From left to right: FPGA Accelerator XORing some bytes using the example program, FPGA LEDs lighting up in response to byte received while debugging, diagram of finite state machine upon which the control circuit of the FPGA is based, and block diagram of major components in the FPGA's datapath." %}

## Technical Information!
FPGA Accelerator is built with:
  * Verilog for the accelerator and UART communication on the FPGA.
  * C for the kernel module and user space library.
  * A Makefile for the kernel module and another to make it easy to use the user space library.

## Awards
None, but the project was really cool and I got an A in the class with it!

The code is open source, and you can check it out on Github [here](https://github.com/FakeNameSE/fpga_accelerator).

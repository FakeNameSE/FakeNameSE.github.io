---
title: "Handwritten Digit Recognizer"
excerpt: "Another winning project for my high school science fair"
header:
  overlay_image: /assets/images/mnist-cnn-graph.png
  teaser: /assets/images/mnist-teaser.jpg
sidebar:
  - title: "Role"
    image: /assets/images/boids-side_bar.png
    image_alt: "logo"
    text: "Creator, researcher and coder"
  - title: "Responsibilities"
    text:  "Main researcher and coder for project"
gallery:
  - url: /assets/images/mnist-cnn-1.png
    image_path: assets/images/mnist-cnn-1.png
    alt: "Graph of learning rate"
  - url: /assets/images/mnist-cnn-2.png
    image_path: assets/images/mnist-cnn-2.png
    alt: "Graph of learning accuracy"
  - url: /assets/images/mnist-cnn-graph.png
    image_path: assets/images/mnist-cnn-graph.png
    alt: "Graph of model"
  - url: /assets/images/mnist-cnn-draw.png
    image_path: assets/images/mnist-cnn-draw.png
    alt: "Interactive screenshot"
---

## What is that fancy graph
For my 11th grade science fair project, I studied artificial intelligence and its mathematical roots by building a convolutional neural network (a special deep neural network adapted for images)  capable of recognizing handwritten digits.

This project consists of a pipline:
1. The user inputs the raw drawing
2. The system crops this drawing, turns it into a square, and resizes it
3. This modified image is passed through the CNN (which was trained earlier)
4. A prediction is made

## Awards
This project won 1st place out of the entire high school for the science fair.

## Some more beautiful graphs
{% include gallery caption="A couple of nice graphs of this mode. From left to right: learning rate, training accuracy, a graph representing the model, and a screenshot of the entry window." %}

## But wait, there's more!
I have open sourced the code, and you can check it out on Github [here](https://github.com/FakeNameSE/interactive-MNIST-CNN) . It is pretty neat if I may say so myself, so feel free to just clone and run it if this piques your interest.
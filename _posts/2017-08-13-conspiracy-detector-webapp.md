---
title: "Conspiracy Detector Web App"
related: true
categories:
  - machine learning
  - coding
  - webdev
tags:
  - Support Vector Machine
  - classification
  - webapp
  - Conspiracy Detector
  - Flask
  -  linux
  - server
---
{% include toc %}
## Guess what!
I have finally created the definitive killer app, [Conspiracy Detector](https://conspiracydetector-web.herokuapp.com/).
## Wait, didn't it already exist?
Fair enough, I am plagiarizing myself a little bit. If you have poked around  this site before, you might be aware of my previous [write up](/machine%20learning/coding/conspiracy-detector/) and portfolio item [Conspiracy Detector](/portfolio/conspiracy_detector/). In fact, they are both based off of the same code, with this new version being a responsive web app.
## So what pressing need does it solve?
Why the need to be able to paste a blob of text into some stranger's website and have it spit back out a heavily opinionated verdict on whether or not the text was written by someone off of their lithium of course!
## Is it a sexy, sexy website?
Well, you are welcome to check for yourself, but in my opinion its rather spartan look  is  actually a statement against the oppression and commodification of the worker by the great neoliberal machine, a verbalization of the angst of the common man as the Ideological State Apparatus slowly imprisons us all within the confines of our own minds, all the while eating the orange and throwing away the peel in the words of Arthur Miller.

In all seriousness though, the site is not the most beautiful to ever grace the interwebs. I designed it to be as minimalist as possible. It gets the job done and does not waste your time loading nor does it waste the rather limited resources of my mid 2000's former thinclient server serving.

## So how does it work?
The website is powered by `flask`, a microframework for python websites. Simply put, it takes the input of a text box, puts that string through the exact same code that gives predictions on the terminal (well, minus the tokenizer which slowed my server down too much and also caused some issues with loading my pretrained model), and serves a new page with the verdict.

## Hasta la vista, baby!
And on that note, I hope you enjoyed my write up on Conspiracy Detector. If this interests you, go ahead and check out the web app  [here](https://conspiracydetector-web.herokuapp.com/), the source code to the original [here](https://github.com/FakeNameSE/ConspiracyDetector), or even my portfolio section on the project [here](/portfolio/conspiracy_detector/), not to mention my original and more detailed write up  [here](/machine%20learning/coding/conspiracy-detector/).

**Update**
I have now just gotten around to posting the source code for the web app on GithHub [here](https://github.com/FakeNameSE/conspiracydetector-web).

>I can't shake the feeling that all these conspiracy theorists are in on it.
> <cite>Wynne McLaughlin</cite>

---
title: "iFeel App"
excerpt: "A cross-platform social media app providing pure, vacuous social validation."
header:
  overlay_image: /assets/images/iFeel_banner.jpg
  teaser: /assets/images/iFeel_teaser.png
sidebar:
  - title: "Role"
    image: /assets/images/iFeel_icon.png
    image_alt: "logo"
    text: "Coder and designer"
  - title: "Responsibilities"
    text:  "I dreamt up, designed, and built this!"
gallery:
  - url: /assets/images/iFeel_splash.png
    image_path: assets/images/iFeel_splash.png
    alt: "iFeel splash screen"
  - url: /assets/images/iFeel_login.png
    image_path: assets/images/iFeel_login.png
    alt: "iFeel login screen"
  - url: /assets/images/iFeel_groups.png
    image_path: assets/images/iFeel_groups.png
    alt: "iFeel group selection screen"
  - url: /assets/images/iFeel_chat.png
    image_path: assets/images/iFeel_chat.png
    alt: "iFeel chat screen"
  - url: /assets/images/iFeel_input.png
    image_path: assets/images/iFeel_input.png
    alt: "iFeel input dialog"
  - url: /assets/images/iFeel_create_account.png
    image_path: assets/images/iFeel_create_account.png
    alt: "iFeel account creation screen"
  - url: /assets/images/iFeel_create_chat.png
    image_path: assets/images/iFeel_create_chat.png
    alt: "iFeel chat group creation screen"
---
*Header from [Freepik.com with background vector created by Brgfx](https://www.freepik.com/free-photos-vectors/background)*

## What Is This and Why the Excellent Clashing Color Scheme?
iFeel originated as the final project for the freshman honors class CS 196 at the University of Illinois at Urbana-Champaign. I have since expanded it from a chat app with a *Bot Button* to better achieve my initial vision for it. This included adding:
  * Multiple groups with everything that entails (creation, modification, and selection being the big visible pieces from the frontend).
  * A navbar replete with buttons decked in homegrown icons to give the user access to this functionality and more.
  * A slide-in scollable menu to select messages from.
  * Upgraded bot functionality making use of sentiment analysis to select a somewhat appropriate response to the last post by another user.

Specifically, this is a cross-platform group messaging app that allows people to interact with others using a limited subset of emotions and feign caring about others' emotions with a bot. This is accomplished by limiting the user to posting only from a dropdown of preselected phrases, emojis and emotionally empathetic and supportive responses. This list, compiled by a CS major (who could possibly be more qualified), includes in its twenty-something posts the full possible range of human emotions from "I feel sad" to "I feel very happy". Should actually selecting a message to show that you care about someone else's feelings be too much for you (I mean, you are on the platform to receive validation, not to give it after-all) fear not, for there is the *Bot Button* which will automagically select an emotionally appropriate response (to some approximation) through the marvel that is sentiment analysis.

The inspiration for the name comes from an imaginary app in the novel *The Nix* by Nathan Hill.

As for the color scheme, the answer boils down to a lack of artistic talent rationalized post-hoc as school pride—*ILL-INI!*

## Screenshots!
{% include gallery caption="Screenshots of app. From left to right: splash, login, group selection, chat, input dialog, account creation with input validation error, and chat creation screens." %}

## Technical Information!
iFeel is built with:
  * React-Native: app frontend (actual code written in Javascript, JSX, and CSS for styling).
  * GiftedChat: React Native library used to render chat UI (namely message bubbles).
  * Firebase: backend — authentication and storing message, group, and user data in its NoSQL RealTime Database.
  * Sentiment: a Node library that uses some basic natural language processing to assign an emotional valence ranging between -5 and 5 to text and emojis.
  * Node & Expo: Used to run app locally on iOS and/or Android.

## Awards
None, I just had a lot of fun and learned quite a bit working on this both during the semester and after.

## But wait, there's more!
I have been keeping this project under somewhat active development and any ideas, recommendations, and even code requests are welcome. Currently, I am eyeing possibly adding notifications and adding local caching of some messages. 

The code is open source, and you can check it out on Github [here](https://github.com/FakeNameSE/iFeel).

Alternatively, if you are just interested in playing around with the app, you can just download the Expo Client app, search for [iFeel](https://expo.io/@fakenamese/iFeel) from it, and seamlessly run it on your phone (it will run off of my free tier Firebase project though, so please do not do anything too excessive with it).


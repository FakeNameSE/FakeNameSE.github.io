---
title: "Prisoner's Dilemma Algorithm"
excerpt: "An original strategy now in an actual research tool"
header:
  overlay_image: /assets/images/wargames-banner.jpg
  teaser: /assets/images/pd-teaser.png
sidebar:
  - title: "Role"
    image: /assets/images/boids-side_bar.png
    image_alt: "logo"
    text: "Creator, researcher and coder"
  - title: "Responsibilities"
    text:  "Developed an original strategy, as well as unittests to integrate it into the existing codebase."
gallery:
  - url: /assets/images/AllFairStrategies_boxplot.png
    image_path: /assets/images/AllFairStrategies_boxplot.png
    alt: "Graph of payoff"
  - url: /assets/images/AllFairStrategies_sdvplot.png
    image_path: /assets/images/AllFairStrategies_sdvplot.png
    alt: "Graph of payoff difference"
  - url: /assets/images/AllFairStrategies_winplot.png
    image_path: /assets/images/AllFairStrategies_winplot.png
    alt: "Win Plot"
---
## A Little bit of Context
For a workshop I ran as part of the [United Innovators](/portfolio/united-innovators) project (check out the rest of my portfolio for more information on that), I had the students conceptualize and then implement strategies to solve *Iterated Prisoner's Dilemma* (click [here](/game%20theory/coding/prisoner-dilemma) to see my write up on Prisoner's Dilemma). However, whenever I run an exercise like that, I always try to solve it myself first, and over the course of doing so I actually developed an original strategy for the problem, something that I honestly just find cool enough that I felt like putting it here (it is *my* portfolio after all).

## A Twist on an Age Old Classic
### Tit for Tat
My strategy is a new twist on the now classic *Tit for Tat* strategy which kicks off the match by cooperating and then simply copies the opponents previous move in order to incentise cooperation and punish defection, effectively pushing towards the only mutually beneficial action of both cooperating while trying to avoid the worst case scenario of cooperating when the opponent defects (if you have no clue what this means, I once again encourage you to read through my write up on Prisoner's Dilemma [here](/game%20theory/coding/prisoner-dilemma) before you continue reading).

### Dynamic Two Tits for Tat
#### Two flaws
However, whereas the traditional *Tit for Tat* only looks one move back to decide on its move, mine is based upon one of its variants, *Two Tits for Tat*, which as you may have guess punishes the opponent for defections within the last two turns.

However, vanilla *Tit for Tat*  and its cousin *Two Tits for Tat* both have problems. 
- In *Tit for Tat*'s case, it is pretty vulnerable to stochastic (random) strategies that have no rational logic that *Tit for Tat* can  use to promote mutual cooperation.
- In *Two Tits for Tat*'s case, its longer memory can lead to a vicious cycle of defections.

#### Forgiveness to the rescue!
My new strategy, called *Dynamic Two Tits for Tat*, addresses these deficiencies by incorporating the idea of forgiveness into the *Two Tits for Tat* strategy. In other words, *Dynamic Two Tits for Tat* always has a probability that it will cooperate with the opponent, even if it defected within the last 2 turns. This probability as the ration of the opponents number of defections and total number of moves: ![number of defections over total number of moves](/assets/images/forgiveness.svg  "Calculation of forgiveness").
This represents in a sense just how nice the opponent is, and thus allows my bot to determine how forgiving it should be of its opponent based off of this (which is also the odds that any move by the opponent will be a defection).
 
This forgiveness effectively allows my bot to avoid for the most part entering long, vicious cycles of defection by both sides (unless they really deserve it), while still allowing the bot to maintain a "willingness" to retaliate when necessary. 

Enough words, it is time for some good looking graphs:
{% include gallery caption="From left to right graph of payoff of tournament, graph of payoff difference of tournament, and win plot. Notice that *Dynamic Two Tits for Tat* beats *Two Tits for Tat* and most other versions of *Tit for Tat* with payoff and beats several other variants including *Tit for Tat* with the win plot." %}

## Awards
None, except that this strategy made its way into an actual academic research tool, something that I confess I am pretty proud of. You can take a look at the project's Github page [here](https://github.com/Axelrod-Python/Axelrod) .

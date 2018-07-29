---
title: "Conspiracy Detector"
related: true
categories:
  - machine learning
  - coding
tags:
  - Support Vector Machine
  - classification
  - Quantum Hitler Scale
  - Conspiracy Detector
---
{% include toc %}
## What are you babbling about now?
The scientific detection of clinical paranoia of course! This post is intended to complement my portfolio entry [here](/portfolio/conspiracy_detector/) on my conspiracy detector project, which I posted the code for on Github [here](https://github.com/FakeNameSE/ConspiracyDetector) .

**Update**
 I have also put together a web app that you can access [here](https://conspiracydetector-web.herokuapp.com/). Unfortunately, because I am ~~self hosting (on the same box as this site)~~ now hosting this site on Heroku (because setting it up for their free tier was a whole lot simpler than trying to run a server accessible to the wider world on a university network from my dorm room, that model has a simplified tokenizer to save processing power and is thus less accurate.

## How exactly did this happen?
Over the natural course of reducing false positives with my email spam filter, clearly! In truth, I kid you not, important emails were being filtered as spam and during my quest to fix this deep disturbance in the force, I was completely sidelined by my curiosity in the actual mechanics of spam filters. A few quick searches later and all was revealed to me... The secret sauce is math! Conditional probabilities and a naive Bayesian filter to be exact.I leave the actual specifics of the workings of this model to Wikipedia, but it suffices to say that it is a machine learning model which when given examples of inputs belonging to different categories is trained to draw inferences between certain characteristic of an input and its label, thereby allowing the trained model to make predictions and classify previously unseen inputs such as emails into spam and ham (legitimate).

I then followed the obvious train of thought of using this type of system to determine whether or not Trump was the progenitor of a tweet. This jump was ultimately unsatisfactory, mainly because I was having a hard time finding a corpus of tweets that were not from Trump and training binary classifiers with only examples from one category leads to pretty disappointing results.

Fortunately for my tinkering, I stumbled across this hilarious blog post entitled [The Quantum Hitler Scale](https://www.stilldrinking.org/the-quantum-hitler-scale) shortly thereafter, and decided that what the world was missing is a heavily opinionated bot capable of discerning text containing some semblance of rational and coherent thought from the literary works of the brave resistance fighters who refuse to be brought down by the Man and His Lithium pills, and who instead tell it like it is, staring death by shape-shifting, alien lizard monsters from the center of the Earth right in the eyes.

And so, the conspiracy detector was born, a state of the art system powered by pure math (well really, applied math) with a twist of computer science.
## So what does it actually do?
### What Conspiracy Detector does
Just as its name says, this weekend project (actually developed over summer break over the course of two weekdays) is a system that uses machine learning to detect conspiracy theories. In other words, I applied the miracles of modern mathematics and computer science to the prickly problem of detecting people who are totally off their rocker, or in the words of the verdict that my machine gives, "bonkers!".
### What Conspiracy Detector does not do
An important caveat is that this system does not detect bias or even fake news (a much tougher problem because it can look pretty similar to reputable news sources). Instead it focuses on the previously (at least to the best of my knowledge) untackled problem of statistically determining if a given piece of text is absolutely nuts (shape-shifting, Jewish, alien lizard nuts).

Another important factor is that this system is entirely constructed from my biases. It believes that the New World Order of Dick Cheney and the Communist, gay, Jews is a conspiracy theory (although I would not put it past Cheney), precisely because I think that this is a completely off its rocker conspiracy theory constructed by a lonely and chemically imbalanced talk show host, terrorist, or pseudo-intellectual who forgot to take his or her pills. If you do not agree with my assessment of what constitutes a crazy conspiracy theory, then you will not agree with this systems verdicts which reflect pretty strongly exactly what I think of the likes of Alex Jones, David Duke, Lyndon LaRouche, William Jennings Bryan, and company. In other words, if you believe [Conservapedia](http://www.conservapedia.com/Main_Page), then this bot is probably not for you.

## How does the magic happen?
Yep, almost indistinguishable from dark magic, this system is actually powered by math (also, python)! It uses a support vector machine (SVM), a machine learning model that can be used as a binary classifier, meaning a much fancier spam filter which is capable of assigning new inputs (after training) to one of two categories (so bonkers and not bonkers in this case).
### Give me some technical details!
The code is written in python3 and uses [sklearn](http://scikit-learn.org/stable/), an awesome python library for all types of machine learning that I highly encourage you to check out, for the majority of the machine learning heavy lifting. It also uses nltk (a  python library for natural language processing) as part of the pipeline in the tokenizer for word stemming.
### And what about training?
A large amount of this project, like many machine learning systems, was training data collection. In order to obtain these thousand of plain text samples necessary to train the system, I first quickly put together a web scraper in python to download articles from news sources such as CNN and BBC, as well as from my daily dose of dismay and despair for humanity (Infowars articles). To complement this, I then dove into the bowels of the [Gutenberg Project](https://www.gutenberg.org/)  and [Archive.org](https://archive.org/), using old Infowars magazines, as well as "papers" from esteemed intellectuals like "Dr." David Duke, Lyndon Larouche, William Jennings Bryan, Paul Joseph Watson, and so many more to obtain the irrefutable textual manifestation of clinical paranoia. On the more rational side, I populated the training set with the plain text English translations of several works by Dostoevsky, Tolstoy, Balzac, Flaubert, Hawthorne, and so many more, as well as through several bland scientific papers. I then split these documents into files of 100 lines each and removed all of the bizarre special characters which had infected some of these texts, eventually leaving me with a grand total of over 2000 training files.
## A slight problem
When I initially built this system, it was pretty heavily based off of sklearn's documentation examples. Unfortunately, due to David Duke and his love for Jews and communists, I had to tinker around quit a bit with tokenization, the process by which the words of the input text are split up and prepossessed, in order to prevent my baby from coughing up a lug nut every single time a text had the word "communist" or any variant of the word "Jew" or "Jewish" in it.
### So, how did you fix it?
After quite a bit of tinkering, I ended up adding among several minor things like stripping out white spaces and punctuation. This reduced the number of bizarre two letter features that would dominate the model's conception of a conspiracy theory, but did not solve the underlying problem of the repeated use of certain  similar words. To solve that problem, I added word stemming to the tokenizer of the model. This strips all words to their roots, thereby reducing words like "jews" to "jew' and preventing silly things such as plurals and derivations from causing too many problems. This solved my problem and improved overall accuracy quite a bit, but also slowed down the training process because of the added complexity to tokenization (although it is still very fast, taking only two minutes on my laptop from 2007).
## Does it work?
Short answer: Yes!

Longer answer, quite well. On the test cases during training, the model attains 99% accuracy. Moreover, it has passed my ultimate litmus test of distinguishing between a Washington Post article and an article from [Conservapedia](http://www.conservapedia.com/Main_Page)  (a Christian fundamentalist version of Wikipedia that among other things believes that Obama is an Islamist Terrorist, that Liberals are pretty much genocidal maniacs, and that conversion therapy works).

In case you were curious,, it has also determined that my  [about](/about/) page is for the most part not crazy, and neither is the *Communist Manifesto*.

## And now some charts and tables
After each training session, the system extracts the top ten features that you can see here:

`Top 10 most important features:`
<table>
<thead>
<tr><th style="text-align: right;">  Rank</th><th style="text-align: right;">   Weight</th><th>Bonkers   </th><th style="text-align: right;">  Weight</th><th>Fine     </th></tr>
</thead>
<tbody>
<tr><td style="text-align: right;">     1</td><td style="text-align: right;">-1.91936 </td><td>o         </td><td style="text-align: right;">0.964309</td><td>change   </td></tr>
<tr><td style="text-align: right;">     2</td><td style="text-align: right;">-1.21264 </td><td>jew       </td><td style="text-align: right;">0.87151 </td><td>wildlife </td></tr>
<tr><td style="text-align: right;">     3</td><td style="text-align: right;">-1.09732 </td><td>government</td><td style="text-align: right;">0.82531 </td><td>reynard  </td></tr>
<tr><td style="text-align: right;">     4</td><td style="text-align: right;">-1.09311 </td><td>ei        </td><td style="text-align: right;">0.805876</td><td>trump    </td></tr>
<tr><td style="text-align: right;">     5</td><td style="text-align: right;">-1.08023 </td><td>louse     </td><td style="text-align: right;">0.805513</td><td>senator  </td></tr>
<tr><td style="text-align: right;">     6</td><td style="text-align: right;">-1.06831 </td><td>n         </td><td style="text-align: right;">0.773819</td><td>specie   </td></tr>
<tr><td style="text-align: right;">     7</td><td style="text-align: right;">-1.062   </td><td>txt       </td><td style="text-align: right;">0.753482</td><td>â        </td></tr>
<tr><td style="text-align: right;">     8</td><td style="text-align: right;">-1.01539 </td><td>ee        </td><td style="text-align: right;">0.749294</td><td>prince   </td></tr>
<tr><td style="text-align: right;">     9</td><td style="text-align: right;">-0.999346</td><td>obama     </td><td style="text-align: right;">0.719461</td><td>sea      </td></tr>
<tr><td style="text-align: right;">    10</td><td style="text-align: right;">-0.930854</td><td>written   </td><td style="text-align: right;">0.703385</td><td>energy   </td></tr>
<tr><td style="text-align: right;">    11</td><td style="text-align: right;">-0.91092 </td><td>jewish    </td><td style="text-align: right;">0.678142</td><td>place    </td></tr>
<tr><td style="text-align: right;">    12</td><td style="text-align: right;">-0.901538</td><td>magazine  </td><td style="text-align: right;">0.672481</td><td>climate  </td></tr>
<tr><td style="text-align: right;">    13</td><td style="text-align: right;">-0.886269</td><td>medium    </td><td style="text-align: right;">0.670092</td><td>important</td></tr>
<tr><td style="text-align: right;">    14</td><td style="text-align: right;">-0.885437</td><td>american  </td><td style="text-align: right;">0.655379</td><td>point    </td></tr>
<tr><td style="text-align: right;">    15</td><td style="text-align: right;">-0.829171</td><td>right     </td><td style="text-align: right;">0.651944</td><td>section  </td></tr>
<tr><td style="text-align: right;">    16</td><td style="text-align: right;">-0.807909</td><td>st        </td><td style="text-align: right;">0.648213</td><td>photon   </td></tr>
<tr><td style="text-align: right;">    17</td><td style="text-align: right;">-0.7689  </td><td>d         </td><td style="text-align: right;">0.641958</td><td>orofino  </td></tr>
<tr><td style="text-align: right;">    18</td><td style="text-align: right;">-0.761795</td><td>litical   </td><td style="text-align: right;">0.641508</td><td>king     </td></tr>
<tr><td style="text-align: right;">    19</td><td style="text-align: right;">-0.744603</td><td>generator </td><td style="text-align: right;">0.619919</td><td>conflict </td></tr>
<tr><td style="text-align: right;">    20</td><td style="text-align: right;">-0.742536</td><td>freedom   </td><td style="text-align: right;">0.60663 </td><td>himself  </td></tr>
</tbody>
</table>

Or, if bar charts are more your speed, you can see the top 20 features for each category here:
![Bar chart](/assets/images/conspiracydetector_features.svg  "Top 20 features")

Now, some weird things come up, mainly on the crazy side, because the input text is still a little dirty despite several attempts to clean it up. However, the system actually works quite well as you can see from its confusion matrix and classification report (from the test set):

	Classification Report:
	             precision    recall  f1-score   support

	    bonkers       0.99      0.99      0.99       298
	       fine       0.99      0.99      0.99       303

	avg / total       0.99      0.99      0.99       601


	Confusion Matrix:
	[[294   4]
	 [  4 299]]

Overall, the top 10 features seem to indicate that a lot of conspiracy theories tend to focus on Jews, Obama, and the Government, as well as on our freedom being taken away, as the words "American" and "freedom" seem to indicate.

## Farewell
And on that note, I hope you enjoyed my write up Conspiracy Detector. If this interests you, go ahead and check out the source code [here](https://github.com/FakeNameSE/ConspiracyDetector), or even my portfolio section on the project [here](/portfolio/conspiracy_detector/).

>I stand by these selections and QHP, but a principle is not enough. No, after reading thousands of articles of alluring bullshit promising me oneness with Earth, good health, eternal life, and infinite persecution by secret kabbalahs bent on world domination and keeping me from knowing the truth about vitamin C, I thought, "Why can't my computer sort this out for me?" I wanted a program that I could plug in that would tell me if the author of an article was bulldozing bullshit, and I wanted to know how much and how fast. I wanted a Quantum Hitler Scale.
> <cite>[Peter Welch](https://www.stilldrinking.org)</cite>

---
title: Recommendations on high quality materials
category: Instructors
order: 3
---

These are a few recommendations to design high quality materials.

## Remember the scope! 

It is **critical** that we stay in scope in our learning units. That means not teaching concepts that have been taught before (feel free to make links to past LUs), and not teaching any concepts that aren't in your Learning Unit's scope. 

Before getting started, look up the scope of your learning unit in the [Curriculum repo](https://github.com/LDSSA/curriculum-development), and think about how you will teach those very specific new concepts. 

Throughout your work, you will inevitably be tempted to add "interesting by-the-ways". You must resist the temptation. Adding stuff is easy, it's curating that is hard.

Having said that, if you find that you **really** need to add a concept in order to do your learning unit, reach out on the `#Curriculum` channel on slack to discuss it. 

Remember that your main responsibility as instructor isn't to list, but to curate.

## See how other people explain it.

The topic you're trying to explain might now be too second nature to you. Invest time into thinking about how to explain it intuitively. This step is the more critical the better you know the subject. 

Googling the keywords _“ intuitions on ____ “_ and reading a couple of articles to see how other people explain it is a good way to start. 

You will often find that the best explanations online are great not because they are highly technical, but because they transmit the concepts in a **highly intuitive manner**. You can, and should, copy some of these explanations, naturally giving credit to the author. Searching for intuitive explanations might also provide you with excellent pictures and ways of representing the problem that would otherwise take a long time to build from scratch. 

## Intuitive is more important than Precise 
We are trying to create intuitions that the students can take in and remember. This will sometimes require sacrificing precision for intuition. Examples of this are: 
* Saying "Correlation", when to be precise it should be "Pearson Correlation".
* Saying that "generally using a Random Forest is a good place to start", instead of trying to qualify that _"except when the calibration of the tails of the probability distribution are more important than the rank ... [more advanced stuff which gets lost on the beginner student]"_ 

You can always come back later with a simple _"remember when I said correlation? Well, technically I should have said Pearson correlation, because here's a new concept called Spearman"_ when it becomes relevant.

As an example of intuitive vs. precise, compare these two ways to explain covariance: 
* [Highly precise answer, but useless if you don't have a strong math background](http://mathworld.wolfram.com/Covariance.html)  
* [Highly intuitive explanation](https://stats.stackexchange.com/questions/18058/how-would-you-explain-covariance-to-someone-who-understands-only-the-mean?)

It is important to keep the intuitions at the correct level. Not all the students have a technical background, but you can safely assume that students have completed high school and most of them even university. Explanations that are too simple are equally bad and missing the point as those that are too complicated.

## Use real word motivations 
Always start with _"why this is worth learning"_. Show a practical case in which a concept can be applied. It is much harder for students to reason about "two random variables, X and Y" than it is to reason about "let's take a bunch of kids, where we know their ages (X) and heights (Y)". By anchoring the solution to a real problem you will help the students to form memories and intuitions, as well as being much more motivating. 

## How much theory? 
There is a delicate trade-off between making sure the students know why they are using something, and feeding them theory for theory's sake. Be practical, and think whether a piece of theoretical knowledge has helped you to use a particular concept. 

As an example, having an intuition of Gradient Descent helps understand why a Logistic Regression needs to be normalized, and is therefore worth including. On the other hand being able to derive the Cross Entropy error function is mostly fun-for-nerds, and does not particularly enhance our ability to use it in practice. 

Ensure that everything we teach is there to make the students able to use the concepts, while avoiding teaching only "how to do stuff". Never teach something just because you had to suffer through it yourself, or because you happen to find it cool, as remember that you have years of experience, and a completely different base. Whenever in doubt, ask the Curriculum lead. 

## Add an optional section at the end 
At the end of your Learning Notebook, make a section entitled _"To learn more (Optional)"_, where you put links to further sources. Two rules here: 
* Only put links that you have read and really found useful
* Use markdown links and use the description to say why the link is worth reading
(e.g. [Step by step way to calculate Variance by hand](https://www.wikihow.com/Calculate-Variance))

## Hide peripheral support code 
Sometimes you need a bit of extra code, be it for pre-processing, to create data or some matplotlib code to produce a nice plot. This code, which is irrelevant for the topic taught in the learning unit, should be hidden in the `utils.py` file. Looking at this code is distracting for students because they can't tell what is core and what it peripheral.

## Data, images, and other supporting material

If you include a dataset, be sure that

1. It is small (1mb is ideal, definitely not more than 5mb)
1. It is stored in a `data` directory

If you need to include images or other media and you want to check them into the repo

1. Again, make sure they are small (<1mb, definitely not more than 5mb)
1. Put them in a `media` folder


## Mind your timeline 

Building Learning Units **takes time!** You will probably take at least 8 hours to build every 1 hour of high quality learning material, so budget for it, and ensure you have a lot of time for revisions and corrections.

If you have any questions about Learning Units please ask them in the `#teaching` channel on the LDSA Slack or in the `#instructor` channel on the current Academy Slack.

## Other tips

1. If you are adding new material, take time to let it mature. If you are a busy person, you can work in small chunks of time. Once you start creating, your brain will comtinue thinking in the background even when you are not actively working on the material.

1. Explain concepts in whichever ways you think is best: remember when you were a student and found things that were unclear or could be made better? This is your chance, bring your ideas to life! Don't be afraid to modify things someone else has written, this year you are in charge. There might be some widely accepted ways of explaining things, but maybe they are not enough intuitive. You might be able to come up with a better approach and you have our complete trust.

1. Don't assume that everything is correct just because it was like this last year. Check everything you don't understand - ask your QA, another instructor, google.

1. Avoid technical jargon or cultural references that not all students might understand.

1. Follow Python naming conventions. Let's do things properly to set the example. Simple things such as constants should be capitalized, or class names should normally use the CapWords convention. For further details, check out the [Python style guide](https://www.python.org/dev/peps/pep-0008/).

1. All the material is written in markdown. If you need, you can find many tutorials online.

1. Use gender neutral language: use 'they' instead of 'he'/'she' or at least don't use 'he' automatically if the gender of the character in question is not clear. This really matters (especially if you are not a 'he' because if the world is all happening in "he" you are automatically excluded).

1. Use cells that are not too long and fit approximately on a laptop screen. If there is a large image, such as a terminal screenshot, use an extra cell for it. This will help readability.

1. Use a reasonable figure size. Adjust the image size so that it fits on a laptop screen. When using figures with text, make sure it's readable.

1. Use a reasonable amount of gifs. Too many gifs make it difficult to read the text - imagine reading a text while having a moving gif in your field of view.

1. Make sure that the exercise instructions are clear and complete.

1. Follow the structure of SLU00. Important structural points:
   - Table of contents with links to the sections.
   - Create sections and subsections with different header sizes.
   - Number sections and subsections - it makes the notebook more readable and easier to find things.

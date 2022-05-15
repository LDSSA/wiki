---
title: Recommendations on high quality materials
category: Instructors
order: 4
---

These are some recommendations to design high quality materials

## Remember the scope! 

It is **critical** that we stay in scope in our learning units. That means not teaching concepts that have been taught before (feel free to make links to past LUs), and not teaching any concepts that aren't in your Learning Unit's scope. 

Before getting started, look up the scope of your learning unit in the Curriculum repo, and think about how you will teach those very specific new concepts. 

Throughout your work, you will inevitably be tempted to add "interesting by-the-ways". You must resist the temptation. Adding stuff is easy, it's curating and ensuring that everything we teach is critical that is hard.

Having said that, if you find that you **really** need to add a concept in order to do your learning unit, reach out on the `#Curriculum` channel on slack to discuss it. 

Always remember the following: 
> **As instructors, our main responsibility isn't to list, but to curate.**

## Before writing anything, start by seeing how other people explain it

Start by doing a review of the topics. In particular, review how to explain it intuitively, as the topic might now be too second nature to you. I'd go as far as saying that making time for this step is the more critical the better you know the subject. 

Googling the keywords _“ intuitions on ____ “_ and reading a couple of articles to see how other people explain it is a good way to get warmed up. 

You will often find that the best explanations online are superb not because they are highly technical, but because they transmit the concepts in a **highly intuitive manner**. You can, and should, copy some of these explanations, naturally giving attribution to the author. Searching for intuitive explanations will also probably provide you with excellent pictures and ways of representing the problem that you would otherwise take a long time to build from scratch. 

## Intuitive is more important than Precise 
We are trying to create intuitions that the students can take in and remember. This will sometimes require sacrificing temporarity precision for intuition. Examples of this are: 
> Saying "Correlation", when to be precise it should be "Pearson Correlation"   

> Saying that "generally using a Random Forest is a good place to start", instead of trying to qualify that _"except when the calibration of the tails of the probability distribution are more important than the rank ... [more impressive highly technical stuff which adds nothing to the student learning in the short term]"_ 

This is particularly difficult to us, because as domain experts we like to show how much we know. At this level however, it is much more important that the concepts be intuitive. We can (and should) later come back with a simple _"remember when I said correlation? Well, technically I should have said Pearson correlation, because here's a new concept called Spearman"_, but only when that is relevant to them.

Finally, remember that what we're teaching is all in the public domain, our role is to transform it into intuitive easy-to-digest bits. As an example, compair these two ways to explain covariance: 
> ###### [Highly precise answer, but useless if you don't already have a strong math background](http://mathworld.wolfram.com/Covariance.html)  
> ###### [Highly intuitive explanation](https://stats.stackexchange.com/questions/18058/how-would-you-explain-covariance-to-someone-who-understands-only-the-mean?noredirect=1&lq=1)

## Always use real word motivations 
Always start by _"why this is worth learning"_, by showing a practical case in which a concept can be applied. It is much harder for students to reason about "two random variables, X and Y" than it is to reason about "let's take a bunch of kids, where we know their ages (X) and heights (Y)". By anchoring the solution to a real problem you will help the students to form memories and intuitions, as well as being much more motivating. 

## How much theory? 
There is a delicate trade-off between making sure the students know why they are using something, and feeding them theory for theory's sake. Be practical, and think whether a piece of theoretical knowledge has helped you significantly to use a particular concept. 

As an example, having an intuition of Gradient Descent helps understand why a Logistic Regression needs to be normalized, and is therefore worth including. On the other hand being able to derive the Cross Entropy error function is mostly fun-for-nerds, and arguably does not particularly enhance our ability to use it in practice. 

Ensure that everything we teach is there to make them be able to use the concepts, while avoiding over-correcting and only teaching "how to do stuff". Never teach something just because you had to suffer through it yourself, or because you happen to find it cool, as remember that you have years of experience, and a completely different base. Whenver in doubt, ask the head of Curriculum (in our case João Ascensão). 

## Add an optional section at the end 
At the end of your Learning Notebook, make a section entitled _"To learn more (Optional)"_, where you put links to further sources. Two rules here: 
> 1. Don't put links to anything you haven't read yourself, and really found useful (no link dumping)
> 2. Use markdown links, and use the description to say why the link is worth reading
(e.g. [Step by step way to calculate Variance by hand](https://www.wikihow.com/Calculate-Variance))

## Hide peripheral support code 
When making notebooks, it is inevitable that you will need to do a bit of extra code. This might be a few lines of pre-processing to get or make data to show the new concept (e.g. making a new DataFrame, or using `get_dummies`), or some matplotlib code to produce a good intuitive plot. 

It is essential however that students be isolated from concepts that aren't the ones being taught. In other words, that they don't spend time looking at matplotlib code, because they can't tell what's core from what is peripheral. For this reason, it is best practice to use a small `utils.py` file at the top level where you hide all your code. Don't worry about making this clean or understandable, the student's shouldn't be peaking here. Here is an [example utils file](https://github.com/PedroGFonseca/preping_template_learning_unit/blob/master/SLU6_Intermediate_Statistics/utils.py), in this case for intermediate statistics. 

## Data, images, and other supporting material

If you include a dataset, be sure that

1. It is small (1mb is ideal, definitely not more than 5mb)
1. It is stored in a `data` directory

If you need to include images or other media and you want to check them into the repo

1. Again, make sure they are small (<1mb, definitely not more than 5mb)
1. Put them in a `media` filder


## Mind your timeline 

Building Learning Units **takes time!** You will probably take at least 8 hours to build every 1 hour of high quality learning material, so budget for it, and ensure you have a lot of time for revisions and corrections and that you send the materials to the QA Team by the agreed deadline.

If you have any questions about Learning Units please [add them as issues](https://github.com/LDSSA/wiki/issues),  or bring them up in the `#teaching` Slack channel! 

---
title: How to Build Learning Materials
category: Instructors
order: 2
---

Contents:
- [Academy Moments & Learning Materials](#learning-materials)
  - [Specialization 1 SLUs](#specialization-1-slus)
  - [Specializations 2-6 BLUs](#specializations-2---6)
- [Learning materials](#learning-materials)
  - [Learning Notebooks](#1-learning-notebook)
  - [Example Notebooks](#2-examples-notebook)
  - [Exercise Notebooks](#3-exercise-notebook)
  - [Bootcamp Presentation](#4-bootcamp-presentation)
  - [Hackathon](#5-hackathon)
  - [Hackathon Problem Statement and Dataset](#5.1-hackathon-problem-statement-and-dataset)
  - [Hackathon Evaluation Guidelines](#5.2-hackathon-evaluation-guidelines)
  - [Hackathon Baseline Solution](#5.3-hackathon-instructor-baseline-solution)
- [Development process](#development-process)

---

This page should serve as the source of truth for how to develop a learning unit for the 
Academy. If you are not familiar with the main details about the course, start by checking
out the information [here](../../Starters Academy (LDSSA)/01-Starters-Academy-(Course).md)

# Learning Materials

The Academy is divided into specializations, which are divided into learning units. Each specialization ends
with a hackathon. The learning units are prepared by a teaching instructor in collaboration with a QA instructor.
A hackathon is usually prepared by a larger team.

### Specialization 1 SLUs

The specialization 1 LUs are small learning units. The first three SLU are part of the admission exam. Each SLU consists of:

* 1 [Learning Notebook](#1-learning-notebook)
* 1 [Examples Notebook](#2-examples-notebook)
* 1 [Exercise Notebook](#3-exercise-notebook)

These units are accompanied by virtual classes (#4-bootcamp-presentation) that are given by senior instructors. The specialization ends with a hackathon (#5-hackathon).

### Specializations 2 - 6 BLUs

The specialization 2-6 LUs are big learning units. They consist of:
* 2-3 [Learning Notebooks](#1-learning-notebook)
* 1 [Examples Notebook](#2-examples-notebook)
* 1 [Exercise Notebook](#3-exercise-notebook)

Each specialization ends with a hackathon (#5-hackathon).

# Learning materials

### 1. Learning Notebook
The Learning Notebook explains the materials in high detail. This notebook 
should be focused on intuitions, and provide motivations, visualizations, 
and explain the new concepts in high granularity. It should work with examples 
to showcase why the students are learning the new concepts.

[Example Learning Notebook](https://github.com/LDSSA/bootcamp/blob/master/units/SLU06_Intermediate_Statistics/Learning%20notebook%20-%20SLU6%20(Intermediate%20statistics).ipynb)

### 2. Examples Notebook

This is rather short and is basically like a cheatsheet for common usage patterns. It can have 
extra examples or applications of the content shown in the learning notebooks.

### 3. Exercise Notebook

The exercise notebook is a series of exercises with auto-grading (see **[how to use nbgrader](https://ldssa.github.io/wiki/Instructors/03-Using-nbgrader-for-Exercise-Notebooks/)** 
for details). This is where the students have to apply the new concepts and so consolidate what they learned. 
The exercises should make the students

1. interact with the concepts (often by simply copy-pasting some code from the Learning Notebook)  
2. understand how to use the common code patterns (which they should have in the Examples Notebook). 

Don't worry if the exercises seem absurdly easy, this is the first time the students interact 
with these concepts, so there's 
no need to make things challenging for its own sake. The Exercise Notebook should contain 
only exercises, no explanations (it can have a quick 
bit of context like a formula, as long as it is already in the Learning Notebook). 

[Example Exercise Notebook](https://github.com/LDSSA/bootcamp/blob/master/units/SLU06_Intermediate_Statistics/Exercise%20notebook%20-%20SLU6%20(Intermediate%20statistics).ipynb)

### 4. Bootcamp Presentation
The SLUs in specialization 1 are divided into 6 groups by topic. Each topic is presented in a virtual class. The presentation should not be about the technical implementation, but focus on the concepts, intuitions, and connection to practice. It should be engaging and motivating and prime the student for studying the SLUs. 

The virtual classes take up to 60 min including student questions. They are presented over two days. The presentation should be done using Google Slides, shared in *anyone can view* mode.

Presentations topics (times are orientative):

Day 1
- Topic 1:
   - 30 min: Intro to data science, SLU04 - Basic Stats with Pandas, SLU05 - Covariance and Correlation
   - 30 min: SLU06 - Dealing with Data Problems
- Topic 2:
   - 30 - 60 min: SLU07 - Regression with Linear Regression, SLU08 - Metrics for Regression
- Topic 3:
   - 30 - 60 min, SLU09 - Classification with Logistic Regression, SLU10 - Metrics for Classification

Day 2
- Topic 4:
   - 45-60 min: SLU11 - Tree-Based Models, SLU12 - Feature Engineering
- Topic 5:
   - 60 min: SLU13 - Bias-Variance tradeoff & Model Selection, SLU14 - Model complexity and Overfitting, SLU15 - Hyperparameter Tuning
- Topic 6:
   - 30-60 min: SLU16 - Workflow, SLU17 - Ethics and Fairness

### 5. Hackathon

In the hackathon, the students are presented with a (close to) real-world problem and dataset. They have understand the problem, analyze and clean the dataset, set up a model, and optimize it for the given metric. Finally, they have to present their solution in a 4 min presentation.

Hackathons are a key moment in every specialization. They allow students to
put the skills they learned throughout the units in practice while working 
together with other students. Both the technical and the collaborative aspect can be challenging. 
Working on different datasets and problems
gives students the opportunity to expand their knowledge beyond constrained 
exercises, gaining practice that is as close as possible to a real life scenario.

#### 5.1  Hackathon Problem Statement

The problem statement consists of a small narrative and a set of instructions that 
explain the task - what are we trying to predict and which metric will be used for scoring.
It is shared in a public google document. The link to the document is provided in the README of the hackathon folder.

The problem should be as realistic as possible, something that a data 
scientist would do in real life.

#### 5.2 Hackathon Dataset

The dataset are files with training data with ground truth and test data. 
We typically work with small to medium size datasets to
simplify the type of processing students need to do, given that they work mostly on their own 
computers. GitHub size limit is a good guidance.

Ideally, the dataset should be:
- real (extracted from a web source, for example)
- is should be possible to get a decent baseline from it using the
techniques taught in the specialization

The team preparing the hackathon should explore the dataset and know what to expect from different techniques/splits/etc. This will be important to provide support to students during the hackathon.

The hackathon team should also prepare a baseline solution, the so-called [instructor solution](#7-hackathon-instructor-baseline-solution).

#### 5.3 Hackathon Evaluation Guidelines

The hackathon is evaluated by:

* The score the students achieve (based on the metric you defined in the problem)
* The presentation of the solution

Each point is worth 50% of the final grade. The hackathon grade is not important for the Academy graduation, it is just for fun, but the first three team will be announced on our LinkedIn.

The presentation is evaluated by at least three instructors. The evaluation guidelines for the presentation help 
all instructors grade in a consistent and fair manner. They are shared in a spreadsheet as a table, where each 
column is a parameter to evaluate and each row a team. See examples from previous batches for inspiration.

#### 5.4 Hackathon Instructor Baseline Solution

The final piece of the puzzle for a great hackathon is the baseline solution. This is meant to
help students revisit the hackathon and understand how to approach it. It is important to note 
that, even though the solution doesn't have to be the best (or necessarily beat all students' scores)
it should be a solid solution by all measures of your specialization.  This solution will be shared in the repo after the hackathon.

A great baseline solution usually has the following characteristics:

* Achieves a decent score on the problem - even if not the best, it should be better than a random
or naive approach to the problem
* Uses the techniques taught in the specialization - your solution should serve
as an example of the value of the methods which the students learned
* Represents a well-structured and well-organized notebook - we want to provide examples of good
coding/development practices when using notebooks, showing the value of organized, reusable code 

# Development Process

The development of the material for the current batch builds on top of the existing last batch material.

## Instructor repository 

As mentioned in the [Teaching Process](../01-Teaching-process/), the Learning Units 
are developed in the [Academy GitHub](https://github.com/LDSSA/), in the repository with the 
name format `batchX-instructors`. The README in the repository contains detailed 
instructions around the technical aspects, such as branch naming, setup instructions, 
package requirements, etc.

In short, this is the process:
1. Open the unit tracking issue and an associated PR to indicate the unit is being developed
2. Carefully read the scope of the learning unit in the [Curriculum repo](https://github.com/LDSSA/curriculum-development), and think about what the students should be able to do after they have finished  
3. Go through the learning notebooks and check for anything that needs improvements (check also the open issues)
4. Google around and see how other people teach the concepts. 
5. Submit the Learning Notebook and Example Notebook's improvements  to your PR
6. Go through the Exercise Notebook and define what you will change
7. Change the Exercise Notebook. Remember that students will do this very slowly, so if it doesn't seem absurdly easy, it's probably too hard. 
8. Share with QA.

Recommended execution order whe adding hackathons:
1. Open a tracking issue and an associated PR to indicate the hackathon is being and developed
1. Define the category of problem that you think could be interesting to explore  
1. Search for available datasets online or in your organization that fit your purpose
1. Explore the datasets and pick one that is an interesting challenge
1. Define the  target variable 
1. Split the data into training and test dataset
1. Create the google doc with the problem description 
1. Link the document in the README, add the dataset and push to the PR
1. Create a set of notebooks that compose the instructor baseline. You can have different notebooks for each
stage of the process (exploration, cleaning, model). Explain why
your baseline is valid - it doesn't need to be the best solution, but it should be a reasonable solution 
that uses the techniques taught in the unit.
1. Create a separate PR and share the baseline solution with QA
1. Create the evaluation guidelines in a spreadsheet and share with QA in the PR description

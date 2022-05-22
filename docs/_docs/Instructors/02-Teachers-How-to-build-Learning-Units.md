---
title: How to Build Learning Materials
category: Instructors
order: 2
---

Contents:
- [Academy Moments & Learning Materials](#learning-materials)
  - [Admission SLUs](#admission-slus)
  - [Bootcamp SLUs](#bootcamp-slus)
  - [Hackathon #1](#hackathon-1)
  - [Specializations 2-6](#specializations-2---6)
- [Deliverables](#deliverables)
  - [Learning Notebooks](#1-learning-notebook)
  - [Example Notebooks](#2-examples-notebook)
  - [Exercise Notebooks](#3-exercise-notebook)
  - [Bootcamp Presentation](#4-presentation-bootcamp-only)
  - [Hackathon problem](#5-hackathon-problem-statement-and-dataset)
  - [Hackathon Evaluation Guidelines](#6-hackathon-evaluation-guidelines)
  - [Hackathon Baseline Solkution](#7-hackathon-instructor-baseline-solution)
- [Development process](#development-process)

---

This page should serve as the source of truth for how to develop any unit within the 
academy. If you are not familiar yet with the main details about the course, start by checking
out more information [here](../../Starters Academy (LDSSA)/01-Starters-Academy-(Course).md)

Let's jump in! 

<br/>

# Learning Materials

The academy has different moments that require different learning materials. Typically
these divide into units and hackathons, with different deliverables. Each unit or 
hackathon typically has one person allocated. This is the person 
responsible by ensuring the delivery of all materials listed here. However, there 
may be more contributors if necessary. An example of this is typically the hackathon
content, which most choose to collaborate on as a team.

### Admission SLUs

The admission Small Learning Units (SLUs) are the first contact students have
with the academy. They are designed as introductory material that students need
to tackle to get admitted into the academy. They are composed of:

* 1 [Learning Notebook](#1-learning-notebook)
* 1 [Examples Notebook](#2-examples-notebook)
* 1 [Exercise Notebook](#3-exercise-notebook)

### Bootcamp SLUs

The bootcamp SLUs are a set of small learning units that will be presented to 
students during bootcamp. Each unit is composed of the same structure as the 
admission SLUs and an additional 15 minute presentation

* 1 [Learning Notebook](#1-learning-notebook)
* 1 [Examples Notebook](#2-examples-notebook)
* 1 [Exercise Notebook](#3-exercise-notebook)
* 1 [Presentation](#4-presentation-bootcamp-only)

### Hackathon #1

The first hackathon is the only one detached from a specialization. It is typically a
simple binary classification problem where students can practice the base skills
that they learned during the bootcamp and have a first contact with the hackathon 
structure. It is composed of:

* 1 [Problem statement and dataset](#5-hackathon-problem-statement-and-dataset)
* 1 [Evaluation Guidelines](#6-hackathon-evaluation-guidelines)
* 1 [Instructor Baseline Solution](#7-hackathon-instructor-baseline-solution)

### Specializations 2 - 6

The remaining specializations are longer and meant to be tackled throughout each month
of the academy by students. Each BLU is dimensioned so that it can be done within 1 week
and each hackathon is a moment for students to apply the methods they learned 
throughout the specialization

* Big Learning Units (BLU)
  * 2-3 [Learning Notebooks](#1-learning-notebook)
  * 1 [Examples Notebook](#2-examples-notebook)
  * 1 [Exercise Notebook](#3-exercise-notebook)
* Hackathon
* 1 [Problem statement and dataset](#5-hackathon-problem-statement-and-dataset)
* 1 [Evaluation Guidelines](#6-hackathon-evaluation-guidelines)
* 1 [Instructor Baseline Solution](#7-hackathon-instructor-baseline-solution)

<br/>

# Deliverables

We now list the different deliverables that are used across the academy. 

### 1. Learning Notebook
The Learning Notebook will explain the materials in high detail. This notebook 
should be mostly focused on **intuitions**, and provide motivations, visualizations, 
and explain the new concepts in high granularity. It can and should work with examples 
to showcase why the students are learning the new concepts. Don't worry too about 
overlap with the Examples Notebook, as the Examples Notebook is mainly about common usage patterns. 

**[Template Learning Notebook](https://github.com/LDSSA/bootcamp/blob/master/units/SLU06_Intermediate_Statistics/Learning%20notebook%20-%20SLU6%20(Intermediate%20statistics).ipynb)**

Expected time investment (1 learning notebook): 

| Development | Instructor | Time (hours of investment) |
|---|---|----|
| Review and small fixes | Experienced instructor | 2 |
| Review and small fixes | Junior instructor | 4  |
| Review plus curriculum changes  | Experienced instructor | 8 |
| Review plus curriculum changes  | Junior instructor | 16 |
| Complete re-write / New unit from scratch | Experienced instructor | 24  |

Note: the times presented are indicative and refer to one single learning notebook
of average size. If a unit has multiple notebooks you should consider these times 
multiplied by the number of units.

### 2. Examples Notebook

This will be extremely short, and look a bit like a cheatsheet of "common usage patterns". It can have 
extra examples or applications of the content shown in the learning notebooks.

Expected time investment: 

| Development | Instructor | Time (hours of investment) |
|---|---|----|
| Review/small changes | Any | < 1 |
| Complete re-write / New unit from scratch | Any | 2-4 |

### 3. Exercise Notebook

The exercise notebook is a sequence of exercises with auto-grading (see **[how to use nbgrader](../Using-nbgrader-for-Exercise-Notebooks)** 
for details). This is where the students will try to apply the new concepts. 
Your exercises should be focused on making sure students

1. interact with the concepts (often by simply copy-pasting some code from the Learning Notebook)  
2. understand how to use the common code patterns (which they should have in the Examples Notebook). 

Don't worry if the exercises seem absurdly easy, this is the first time the students interact with these concepts, so there's 
no need to make things challenging for its own sake. The exercises notebook should contain only exercises, no explanations (it can have a quick 
bit of context like a formula, as long as it is already in the Learning Notebook). 

Expected time investment: 

| Development | Instructor | Time (hours of investment) |
|---|---|----|
| Small exercise changes and reshuffle | Experienced instructor | 2 |
| Small exercise changes and reshuffle | Junior instructor | 8 |
| Overall narrative + exercise change | Experienced instructor | 16 |
| Overall narrative + exercise change | Junior instructor | 24 |
| New unit from scratch | Experienced instructor | 24  |

**[Template Exercise Notebook](https://github.com/LDSSA/bootcamp/blob/master/units/SLU06_Intermediate_Statistics/Exercise%20notebook%20-%20SLU6%20(Intermediate%20statistics).ipynb)** (with nbgrader)

### 4. Presentation (Bootcamp only).
The presentation should be **the same content** as the Learning Notebook, displayed in a friendly way. 
Quite simply, you will be "pre-chewing" the material from the Learning Notebook, and giving it to the students 
live on the day. 
 
This means that during the bootcamp, the students will learn the concepts and intuitions from your presentation, 
but not need to take notes, as the Learning Notebook already contains all the material in high granularity. 
Presentations should not contain material which is not in the Learning Unit.   

This also means that your presentation does not need to make sense without a presenter. There's no need to fill 
the presentation with text, and can just have images to support what you are saying. Focus on making sure the 
presentation is intuitive, engaging, motivating, and **fun**.   

The presentation should be done using Google Slides, shared in anyone can view mode and it 
should not take longer than 15 minutes. Your link should be to the presentation itself, not the full screen mode, so that 
other people can clone it and change it. The presentation should be store under the 
academy shared drive, which you will be given access when onboarded.

Expected time investment: 

| Development | Instructor | Time (hours of investment) |
|---|---|----|
| Presentation | Experienced instructor | 4 |
| Presentation | Junior instructor | 8 |

#### What will happen in an bootcamp class (SLU)?   
During the bootcamp, the sequence will be approximately the following: 
> First 15 minutes: instructor goes through the presentation, and introduces new topics 

> Minutes 15 to 20: students ask questions, instructor clarifies main points  

> Last 40 minutes: students solve the exercises, using the Learning Notebook and Examples Notebooks for support. 

As you might have noticed, there is no time dedicated to the students reading the 
Learning Notebook. That is deliberate, as the same content has just been introduced in 
a highly structured and (hopefully) entertaining way by the instructor. The student will, 
however, need the Learning Notebook and Examples Notebook as support, as (s)he 
tries to solve the Exercises. 

### 5. Hackathon Problem Statement and Dataset

The hackathon **dataset** and **problem statement** consist of the
two deliverables that will be presented to students on the hackathon day, at the
end of a specialization. They are released on the day of the hackathon and have the 
format described below:

* The dataset is a file or set of files provided directly in the repository containing
what we consider training data. We typically work with small to medium size datasets to
simplify the type of processing students need to do, given they work mostly on their own 
computers. As such, you shouldn't need to exceed the size limitations that github imposes.
* The problem statement consists of a small narrative and a set of instructions that 
indicates to students what is the task at end - what they are trying to predict and some
guidelines on how they are goign to be scored. This is typically shared through a public
link to a google document, provided in the README of the hackathon folder

Hackathons are a key moment in every specialization. They allow students to
put the skills they learned throughout the units in practice while working 
together with other students. Working on different datasets and problems
gives students the opportunity to expand their knowledge beyond constrained 
exercises, gaining practice that is as close as possible to a real life scenario.

For this purpose, when preparing a hackathon, you should try to keep the following
in mind:

1. The dataset should be real (extracted from a web source, for example), not fabricated
2. The problem should be as realistic as possible, this is, it could be something a data 
scientist would do in real life
3. The data and problem should get a decent baseline using at least part or all of the
techniques taught in the specialization

Finally, building the dataset and problem statement involves more than that. It assumes you
already explored and tested out the dataset yourself (and potentially got more people to help) 
so that you know what to expect from different techniques/splits/etc. This is something 
that takes time, but is important to provide a solid hackathon, and a solid baseline solution (see
 [Instructor Baseline Solution](#7-hackathon-instructor-baseline-solution) below)

Expected time investment: 

| Development | Instructor | Time (hours of investment) |
|---|---|----|
| Hackathon problem | Experienced instructor | 8 |
| Hackathon problem | Junior instructor | 16 |


### 6. Hackathon Evaluation Guidelines

An important part of the hackathon is to establish how students will be evaluated. This 
evaluation will be mostly based on two factors:

* The score they achieve (based on the metric you defined in the problem) - worth 50%
* The presentation score, given by multiple instructors 

The evaluation guidelines focus on the presentation, and are a set of factors and their 
weights to help all instructors grade in a consistent and fair manner. They are usually
shared on a spreadsheet as a table, where each column is a parameter to evaluate
and each row will be a team.

Expected time investment: 

| Development | Instructor | Time (hours of investment) |
|---|---|----|
| Evaluation guidelines | Experienced instructor | < 1 |
| Evaluation guidelines | Junior instructor | 2 |

### 7. Hackathon Instructor Baseline Solution

The final piece of the puzzle for a great hackathon is the baseline solution! This is meant to
help students revisit the hackathon and understand how to approach it. It is important to note 
that, even though the solution doesn't have to be the best (or necessarily beat all students' scores)
it should be a **solid solution** by all measures of your specialization. 

A great baseline solution usually has the following characteristics:

* Achieves a decent score on the problem - even if not the best, it should be better than a random
or naive approach to the problem
* Uses one or many of the techniques taught on the specialization - your solution should serve
as an example of the value of the methods students learned throughout the previous month
* Represents a well-structured and well-organized notebook - we want to provide examples of good
coding/development practices when using notebooks, showing the value of organized, reusable code 

Expected time investment: 

| Development | Instructor | Time (hours of investment) |
|---|---|----|
| Baseline Solution | Experienced instructor | 8 |
| Baseline Solution | Junior instructor | 16 |

<br/>

# Development Process

For most of the specializations and units, the materials from previous batches
already have a high level of quality. Given that, our process assumes the 
development will be done on top of the previous batch. 

## Instructors repository 

As mentioned in the [Teaching Process](./01-Teaching-process.md), the Learning Units 
are pushed to the [Academy GitHub](https://github.com/LDSSA/), to the repository with the 
name format `batchX-instructors`. The README in the repository contains detailed 
instructions around the batch process's technical aspects, such as branch naming, requirement,
etc.

Once the base improvements are done, the unit is shared with the QA team, which will 
review and test the unit. This feedback helps us detect potential bugs and places for 
improvement before the materials reach the students.

Recommended process whe adding units:

1. Open an issue and an associated PR to indicate the unit is being tracked and developed
2. Carefully read the scope of your learning unit in the Curriculum repo, and think about what the students should be able to do after they have finished  
3. Go through the learning notebooks and check for anything that needs improvements
4. Google around and see how other people teach the concepts. 
5. Submit the Learning Notebook and Example Notebook's improvements  to your PR
6. Go through the exercise notebook and define what you will change
7. Change the Exercise Notebook. Don't worry too much about auto-grader at first, you can do that later. Remember that students will do this very slowly, so if it doesn't seem absurdly easy, it's probably too hard. 
8. Share with QA


Recommended execution order whe adding hackathons:
1. Open an issue and an associated PR to indicate the hackathon is being tracked and developed
2. Define the category of problem you think could be interesting to explore  
3. Search for available datasets online that could fit your purpose
4. Explore the datasets and pick one that can make for an interesting challenge
5. Define which target variable students are predicting and create the file split that will
be shared with students
6. Create the google doc with the problem description 
7. Link the document in the README, add the dataset and push to the PR
9. Create a set of notebooks that compose the instructor baseline. You can divide these into different
stages of the process, if you think it will make it easier for students to explore later. Explain why
your baseline is valid - it doesn't need to be the best solution, but it should be a reasonable solution 
that uses the techniques taught in the unit
10. Create a separate PR and share the baseline solution with QA
11. Create the evaluation guidelines in a spreadsheet and share with QA in the PR description

---
title: Curriculum Overview and Main Concepts
category: Starters Academy (LDSSA)
order: 5
---

> ⚠️ Some information in this page might be outdated.

## Structure

A Starters Academy is made of one Bootcamp, 6 to 7 specialisations, and 1 capstone. 

## Bootcamp 
The bootcamp is the launching event of the Academy, where students have to learn and execute a large number of small learning units, and includes one hackathon. 

## Hackathon 
A hackathon is a 1 day event where students, in teams, have to execute and present a well-posed project. In order to keep the students motivated, there is a single number value that they are optimising for, and they compete for position on a leaderboard. Teams are assigned at random, as students will need to work with people they wouldn’t choose in the real world. 

## Specialisation 
A specialization is a set of 3 big learning units and a hackathon, centred on a particular topic (e.g. time series). 

## Capstone
The capstone is the final project of the Starters Academy. It requires each student to individually execute a project, which will be graded.  

## Learning units

A Learning Unit is a concept developed in the Academy. It is composed of the following: 

### 1. Teaching Notebooks (Jupyter Notebooks)
The high granularity teaching should be done in the Teaching Notebooks. These should be sufficient to teach the materials on their own. We should assume that notebooks will be used in future for reference by the students, and therefore shouldn't assume that they remember a presentation or any other immediate context. 

It is critical that Teaching Notebooks also teach only the new concepts, and refer to previously learned concepts to the respective learning units. As happens everywhere in the Academy, there should be no scope bloat, and the Teaching Notebook should explain only the materials from the Learning Unit, and under no circumstances include curiosities or un-requested material. 

Optionally, a final section called _"If you want to learn more (optional)"_ can be added to guide interested students in their independent studies.  

### 2. Exercises with expected output (Jupyter Notebooks) 
Exercises are notebooks that cover the material taught in the same learning unit's Teaching Notebooks. They are based on the Coursera idea of providing an expected output and ensuring the student only needs to worry about a highly granular piece of material. 

Most exercises will demand an exact answer (having therefore to control for random seeds, etc), while exercises which more concerned with workflow may have a slightly more open objective, such as exceeding a certain performance metric. Exercises should be done individual, and will be graded by an auto-grader. This auto-grader should test on the general case, as getting the expected output right can be done with brute-force (e.g. returning the expected output). 

Example of exercise with expected output: 
![Example of exercise with expected output](https://image.ibb.co/chQ7Kn/Screen_Shot_2018_04_01_at_3_03_42_PM.png)

Any learning unit requires a grade of at least 80% to be considered passed, with an unlimited number of attempts (but which can have an end date for attempts). 

### 3. Presentation (optional)  
Presentations only happen in the Small Learning Units, as they are the ones that are taught in person. Presentations are short, motivating introductions to the topic, which should explain only the trickiest concepts, without going into every detail of what is being taught. 

The main objective of a presentation is to ensure that the students understand "why" they are learning a topic, rather than teaching the full topic. 
 
## Big vs small learning units 
Learning units must be highly modular, and serve to teach highly related concepts. There are two types of Learning Units: 

### 1. Small Learning Units (SLU) 
SLUs are taught during the Bootcamp, and take 1 hour. They are the only Learning Units to contain in-person presentations. 
The expected time split for students is: 
- 15 minutes of presentation
- 20 minutes of teaching material
- 25 minutes of exercise. 

### 2. Big Learning Units (BLU) 
BLUs form the backbone of the Academy after the Bootcamp ends. They do not contain presentations, as they will be done exclusively in remote mode. The total time a student is expected to spend on a BLU is 5 hours (this is a minimum requirement, but should be used by instructors as the guideline to avoid excessive content). 
The time expected time split for students is: 
- 2 hours of teaching materials 
- 3 hours of exercise   

A BLU should completely prepare the students for the Hackathon. 



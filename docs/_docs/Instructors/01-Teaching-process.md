---
title: Teaching Process
category: Instructors
order: 1
---

Contents:
- [Material structure](#academy-materials)
- [Areas of responsibility](#areas-of-responsibility)
- [Timeline](#timeline)
- [Key takeaways](#key-takeaways)

---

This page provides an overview of our teaching process and methodology. It describes
the structure and format of our materials, the roles of different areas of responsibility
in the material creation and maintenance, and an example timeline for the process.
Any questions related to teaching should be posted as issues on our wiki 
repo or the slack teaching channel `#teaching`.


# Academy materials

The teaching material has the form of Jupyter notebooks. 
This provides an interactive way of learning, as students can run code while reading the explanations. 
We use learning notebooks to explain the new material and exercise notebooks where the students have to solve graded exercises.
We use the [nbgrader](https://nbgrader.readthedocs.io/en/stable/) package to evaluate the exercises. See [Using nbgrader](../03-Using-nbgrader-for-Exercise-Notebooks/) for usage examples.

All materials are planned, built and reviewed through github. The repositories
are in the [Academy GitHub](https://github.com/LDSSA/). These are three relevant repositories:
* [curriculum-development](https://github.com/LDSSA/curriculum-development) (public): Our curriculum is reviewed and updated in this repository.
* `batchX-instructors` (X = current batch number): Private repo for the material development where instructors and QA collaborate in creating and maintaing the material.
* `batchX-students` (X = current batch number): Public repo where students get the material. The developed material is released here from the instructors repo.

# Areas of responsibility
 
Several areas of responsibility work together to develop and maintain the material. Below 
is an overview of how they interact and their key responsibilities.

<img src="../../images/aors-teaching-process.png"/>

### Curriculum

Overall responsibilities:
* Define which contents should be offered
* Review the relevance of contents and introduce new topics

### Teaching

Overall responsibilities:
* Produce and improve materials
* Release content and provide support during the Academy

We currently have two kinds of teaching instructors:
* Junior instructors: maintain and create the material
* Senior instructors: provide support to junior instructors, give bootcamp presentations, give AMA sessions

### QA

Overall responsibilities:
* Review and test materials produced by teaching

### Student Success

Overall responsibilities:
* Monitor student progress and learning experience
* Collect student feedback

# Timeline

Since batch6 we are aligning the Academy with the school year. The timeline represented here follow that logic and provides rough estimates of the months
where each part of the process happens. This should serve as a base for volunteers to
know when to get involved in different parts of the process.

## Batch kick-start

In between batches we take student feedback and together with the rest of the 
organization debate potential changes to the structure and contents of the academy.
We focus mainly on:
- Revision and update of the contents - the final responsibility lies
on the curriculum AOR
- Revision of the structure in the light of student feedback and learning success - the main responsibility lies on the teaching AOR

The changes are discussed through slack and GitHub issues and finally in a summit. After the decisions are taken, they are documented and we proceed with the preparation of the next batch.

<img src="../../images/batch-start-timeline.png"/>

It's at this point that volunteers should be proactive and share where they would like
to work. All allocation is done through our [wiki](https://github.com/LDSSA/wiki/)
and is coordinated by the teaching and QA leads.

## Learning units development

Most of the time, the curriculum does not change dramatically between batches. 
In the majority of cases there are only slight adjustments.

In general, when improving an existing unit the focus should be:
* Review the existing materials: go through the learning and example notebooks 
and check for potential improvements - maybe something isn't fully clear or would 
benefit from an extra example.
* Correct errors discovered in the previous batch.
* Update the code for the current Python and package versions.
* Revamp the exercises in the admission units SLU01-03.
* Review the exercise notebook: the exercises don't have to change if they fulfill the learning goals. It is possible to add/replace exercises, keeping in mind that the notebook cannot grow too much.

This process usually takes 1-2 months. It is the responsibility of the instructor and QA to start early and coordinate so that the unit is ready in time bwfore the release date.

An example timeline can be seen below:

<img src="../../images/unit-development-timeline.png"/>

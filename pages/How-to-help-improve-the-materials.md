# Context 

Having high quality materials is not just a product of creation, but also of maintenance and iterative improvement. It may not be as exciting as creating new content, but it is arguably just as important. 

That's why it is so crucial that everyone chip in, and look for potential issues, both in the exercise and learning units, and either suggest issues, solve them, or both. 

Before you jump in, please take the time to read this guide (if you haven't read the [How to Build Learning Units guide](pages/How-to-build-Learning-Units), please read that one first.md).

## How to help improve learning units 
There are 3 ways to improve learning units: 
1. [Doing the exercises and/or reading the Learning Notebooks](pages/How-to-help-improve-the-materials#how-to-find-issues) and [creating issues](pages/How-to-help-improve-the-materials#how-to-open-issues)
2. [Fixing known issues](pages/How-to-help-improve-the-materials#how-to-fix-issues) 
3. Both

All the above are valuable and extremely welcome. All development of new material is done on the intructors' versions, which are private repos ([why?](pages/How-to-help-improve-the-materials#why-not-fix-things-directly-in-the-students-repo)). If you need access to contribute, go [here](pages/How-to-help-improve-the-materials#how-to-request-access-to-the-instructors-repos). 

## Where to start 
Go [here](https://docs.google.com/spreadsheets/d/1E_r65ZLUwbtDwbdoSyuU4S2fC17kvRpezRUl-XyU4c4/edit#gid=0), and see which Learning Units you'd like to help QA. Please don't select any that you created yourselves (even though you can and should fix bugs on yours), so that someone other than the author also QAs it. Once you've found a few you like, add your name to it 🥇   

## How to find issues 
The best way to find issues is to pretend to be a student and do the materials. If you wish to contribute it makes sense to use the instructors versions, as there might be some fixed issues there already. 

When doing the exercises, it is imperative that you don't look up the answers in advance, and that you avoid just "checking if the solution runs". Most real problems are related to insufficient clarity in the instructions, or alternative solutions not passing the asserts, so it is extremely important to solve the problems blind to the solution.  

Issues may be of different types: 
1. The exercise or learning notebook is objectively wrong
2. The instructions are unclear or ambiguous 
3. A correct answer does not pass the asserts (often due to the assert being wrong)
4. An incorrect answer passes the asserts 
5. Something could be explained more clearly in a different way 

All of these are valuable, and you should open issues and label them accordingly. 

## How to open issues 
Issues are extremely useful to keep track of what needs fixing, as long as we follow some guidelines. 

1. Keep issues extremely modular. If you found 3 problems, please open 3 issues, otherwise, the person fixing them will need to start and maintain a separate checklist. Also, some of them may be `wontfix` whereas others may be important. 
2. Make them reproducible, and non-ambiguous. Identify the notebook, and which question/paragraph in the notebook the issue relates to. Assume the author must be able to solve the issue without contacting you to ask what you meant. 
3. Label the issue appropriately. If it relates to an SLU, select the appropriate label, which will make tracking fixes much easier. 
4. Optionally, propose a solution to the problem as the first comment, but don't mix the solution with the problem 
> **Good issue:** _"Question 4 in SLU13 does not run on Windows"_ **||** _first comment "Should replace `ls` with `os.listdir`"_  
> **Less good issue:** _"Question 4 in SLU13 should use os.listdir instead of ls"_  
> **Terrible issue:** _"Use os.listdir() in SLU13"_  
5. Open issues on the repo where the problem actually occurs. 
6. Make the title sufficiently descriptive, don't call an issue "problems in SLU3" 

## How to fix issues 

1. Before fixing the issue, please [open one](pages/How-to-help-improve-the-materials#how-to-fix-issues), so that we can keep track of what issues are being worked on. Also, it allows us to know what issues are closed by each PR. 

2. Check if the issue is already being fixed by a pull request (it should be mentioned in the PR, if that is the case) 

3. If it isn't yet mentioned in any PR, open a new branch (locally) and fix the issue. Keep your branch specific to the particular issue (or at least to the particular notebook) on which you are making fixes. Name it in a way that is clear to the reader (e.g. _"SLU4 - fixing issue #17 by changing the output to Series"_)

4. Push the issue to the correct branch, and issue a PR. **Under no circumstances should you push to an open-source repository**, as the solutions should not be visible to the students. If you have any problems with pushing do [this](pages/How-to-help-improve-the-materials#how-to-request-access-to-the-instructors-repos). 

5. Indicate in the PR description which issues it is supposed to solve. You can use the number of the issue (e.g. #14), and github will intelligently link them.
 
6. Once the PR has been issued, it will most likely be reviewed by the original author, and if everything is correct, accepted. 

7. You've made the data science world a little better! Give yourself a pat on the back, or join us for a beer :) 

## IAQ 
_(Infrequently asked questions)_

#### How to request access to the instructor's repos 
If you want to contribute but don't have access to the necessary repos, please contact [Pedro](https://github.com/PedroGFonseca/) on pedro[at]lisbondatascience.org

#### Why not fix things directly in the students' repo? 
The reason for this is two fold: 
1. The Exercise notebooks are often in NBgrader, so they cannot be changed without breaking things.
2. Sometimes it is necessary to change the Accepted Solution, which is evidently not on the student repo 
 
#### Can I just raise issues, and not fix them? 
Absolutely! Generally fixing issues is easier than finding them. 

#### But isn't making pull requests on jupyter notebooks super error prone? 
Jupyter notebooks are quite prone to horrible merge conflicts. Therefore we ask that all fixes be as modular as possible. Also, check whether there are already pull requests open that might be on the same notebook. It's not ideal, but should solve 95% of the problems. 

#### I found something which isn't a bug, but I would have explained it differently. Can I change it? 
If you think it might be a style of teaching problem, it may make sense to contact the author first. Open an issue and @ the author, explaining what alteration you are planning on doing.

#### There is a way more advanced way of solving this! Shouldn't this be the accepted solution?
Remember that the indended audience of most of our material are newbies at Data Science. Often the explanation will be deliberately simple, as we will prioritize something being intuitive over something being cutting edge. 
If you want to propose one of these improvements, it's best to open an issue first, suggest it, and tag the author. 

#### I found a typo or grammar mistake. Should I raise an issue? 
Yes, please! Most of us are not native English speakers, so we're likely to make some ~~ortografic~~ ~~ortographic~~ orthographic mistakes here and there. 

#### I got in trouble with git / repo stuff
The [#devops](https://ldsacademy.slack.com/messages/C9YRC295X) channel has people who actually understand how Git works, in a different way from [the way data scientists understand it]( https://xkcd.com/1597/). 
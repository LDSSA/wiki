There is currently no good way to update SLUs without either

1. Taking about 6 weeks
1. Asking all students to re-upload their answers from a new notebook

With this in mind, here is what we will need to do in order to update. It's really quite simple for the instructors though there's a bit of manual work for dev-ops and the students.

## Steps For Instructors

1. All instructors push their fixes to the [instructors repo](https://github.com/LDSSA/batch2-bootcamp-instructors) with their fixes for any changes corresponding to open issues in the bootcamp repo.
1. All instructors create a temporary assignment on jupyter hub and test it.
1. Once it is tested, create a PR in the instructors repo and assign Sam as the reviewer.
1. That's it! You're all done! (Unless Sam finds a problem with the LU that is)

### Time estimate for instructors

Very low - only the amount of time it takes to fix your notebook, test it, and push it to the instructors repo. For simple fixes, this could be as little as 15 minutes per notebook.

## Steps For Dev-Ops

1. Re-create the newly-released versions of the learning units on jupyter hub and nbgrader
    - This will cause all current work by the students to be lost only on those notebooks
1. Ask students to re-upload any of the notebooks that were lost in the process

## Steps For Students

1. Re-clone the repo
1. Copy-paste your answers into the new versions of the notebooks
1. Re-upload the notebooks


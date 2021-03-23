# The 1,000,000 foot view

The steps for creating your first BLU exercise notebook is the following:

1. Install the dependencies for nbgrader on your local machine
1. Make the exercise notebook on your local machine and push to the instructors BLU repo
1. Test the student version of the exercise notebook on your local machine
1. Get the official reviewer to review it as well and iterate as needed
1. Drop into the #dev-ops channel and let them know it's ready to go out into the world

# What is nbgrader? 
 
nbgrader is "A system for assigning and grading notebooks". For anyone who's ever done a Coursera course, it looks  quite similar to their exercises. 

<img src="https://i.stack.imgur.com/7y2Na.png" width="600" />

In the Academy, we use nbgrader for the Exercise Notebooks. 

# How do I get started? 
Note: One limitation of nbgrader is that your Exercise Notebook(s) need to be on the root of the project.

1. Build your Exercise Notebook on your own machine, don't worry about nbgrader yet. You can add the asnwers too, nbgrader will hide them for you.
1. Install nbgrader locally, depending on your setup use your package manager of choice to install the `nbgrader` package.
1. Activate nbgrader extensions, this is done by running the commands:
```
jupyter nbextension install --sys-prefix --py nbgrader --overwrite
jupyter nbextension enable --sys-prefix --py nbgrader
jupyter serverextension enable --sys-prefix --py nbgrader
```
You might need to reactivate your environment if you're using virtualenvs.
1. Assuming you've already made your Exercises open your notebook.
1. Go to `view —> cell toolbar —> create assignment`
1. By now you should have something like this:

<img src="https://preview.ibb.co/i8nSzx/Screen_Shot_2018_04_08_at_8_38_31_PM.png" width="600" />

# Turning your Exercises Notebook into an auto-graded work of art 

Start by going [here](https://hub.lisbondatascience.org/services/ldssa/)

Note: nbgrader is powerful, but it is a heavy piece of tech to use. We'll try to point out the main points here, but you will probably need to see [the documentation](https://nbgrader.readthedocs.io/en/stable/) when you get stuck. 

<img src="https://preview.ibb.co/cbK1Rc/Screen_Shot_2018_04_08_at_8_45_19_PM.png" width="600" />

There are 4 types of cells: 
1. `Read-only` - use these when you want to make a cell be uneditable. Tests will have a different category.   
2. `Manually Graded Answer` - Not very useful, as we don't want to do manual grading  
3. `Autograded Answer` - Where the students will have to fill in code    
4. `Autograder tests` - The unittests that the student's answer will have to pass  

### Autograded Anwer cells 

To make an auto-graded answer cell, just edit your existing exercises so that the solution is between `### BEGIN SOLUTION` and `### END SOLUTION`. 

In order to give the students stucture, you will probably want to have multiple blocks alternating with some instructions. Ideally the students should be focused only on the new concept they have just learned, not on solving python problems. If the concept is easy you can of course give them a very "bare bones" function to complete, but should there be any level of complexity consider giving them the intermediate steps in the form of comments. 

<img src="https://image.ibb.co/gba5Kx/Screen_Shot_2018_04_08_at_8_57_55_PM.png" width="900" />   

_(note: there is probably a less verbose way to do this, but until [this stackoverflow question](https://stackoverflow.com/questions/49720663/in-nbgrader-how-to-show-an-answer-set-to-none-rather-than-show-empty-rows) gets answered, this is what we've got)_

The students will not see the answers, obviously. To see how the students see it, go to the [Manage Assignments](https://hub.lisbondatascience.org/services/ldssa/formgrader#) section, and click `generate` on your assingment (be careful not to mess with other people's assignments). If it loads without problems, click `preview` (the little magnifying glass), and you can open the notebook from the student's view. 

In our case, this is what the student sees: 
<img src="https://image.ibb.co/fqeeCH/Screen_Shot_2018_04_08_at_9_06_27_PM.png" width="900" />   
*Note: There is no need to add `YOUR CODE HERE`. nbgrader will replace all of the code in the solutions block and replace it with this string*

### Expected output (optional) 
While not strictly required for the Exercises to work, it is useful for the students to have some examples of what the output should be, to help them debug. These can be added as normal cells, and don't actually count for evaluation. You can simply grab some output your expect, and paste it in markdown in a cell.  This allows students to check their logic, without having to submit the notebook or reverse engineer the actual tests (especially as sometimes you might want to hide the tests to prevent sneakiness). 

<img src="https://image.ibb.co/hDdHzx/Screen_Shot_2018_04_08_at_9_11_41_PM.png" width="900" />  


### Autograded Test cells 
Great, now to evaluate that the student's implementation actually works. 
<img src="https://image.ibb.co/dbGLKx/Screen_Shot_2018_04_08_at_9_17_45_PM.png" width="900" />  

A few things to notice here:   
1. The cell is now `Autograder tests` (this is relatively easy to get wrong and write `Autograder answer`, which will give you painful debugging problems).   
2. The cell has points. If it raises errors, the student does not get those points. Make your entire Exercise Notebook's points sum 20, so that the grading system is coherent.   
3. In this case, some tests were hidden, and others weren't. There is generally no particular need to hide the tests, but sometimes the answer might be a string, and then it might be too tempting to look it up. Best use common sense here.  
4. Using `math.isclose` may be better than using `isequal` or `==`. For instance, in that last example, the correct answer was `-15.999999999999996`, so we compared it to `-16`, with a tolerance of `abs_tol=0.001`
5. If you want to hide some of the tests (because they show the answer for example), you need to write them between `### BEGIN HIDDEN TESTS` and `### END HIDDEN TESTS`.

#### Using the `inspect` module for better asserts 
There are a few common patterns that students make, such as forgetting to return, or using globals accidentally. We can use the `inspect` module to check the function as if it were text! 

Here is an example of a messed up student answer 
```
n = 2                             # a global hanging around! 

def multiply_by_n(some_number):   # not enough arguments! 
    print(some_number * n)        # print, instead of return!  
```
Here are some asserts for this situation 
```
sig = inspect.signature(multiply_by_n)       # get the signature from the function 
source = inspect.getsource(multiply_by_n)    # get the source from the function (as a string! Wooow!)

assert len(sig.parameters) > 1, 'Are you sure you are passing the right arguments?'
assert "return" in source, 'Please return to your answer. Return... get it?'
assert "*" in source, 'What operation did we ask you to do again?'
assert "8" not in source, "Did you try to hard code the answer? Tsk, tsk, tsk."
assert "n" not in globals(), "you may be accidentally grabbing a global variable!"
```

#### Hashing the correct answer 
Sometimes we are checking for a particular value (e.g. a string), and we don't want to put it in the assert. In this case we can hash the right answer, for instance by doing the following: 

```
import hashlib

def _hash(s):
    return hashlib.blake2b(bytes(s, encoding='utf8'), digest_size=5).hexdigest()
```

Let's say this is the student's answer: 
```
def what_is_the_capital_of_france():
    return "Rome, I guess"
```

We can check this without having to show "Paris" in the asserts, as we've hashed Paris ahead of time, and are comparing hashes: 
```
assert _hash(what_is_the_capital_of_france()) == '4262400ad8', 'Wrong city!'
```

### Slightly more open form questions 

Not all questions should be "insert code here". Sometimes we want to test them on their workflow, or ability to explore a dataset. 
This is an example of how to make an open form answer, which can still be validated by the auto-grader (it will check if the answers in the `analysis` dictionary are correct, and if more than 1 answer is viable, the auto-grader's test can just do an `or` operation.
 
<img src="https://image.ibb.co/bxO36c/Screen_Shot_2018_04_08_at_9_24_20_PM.png" width="900" />  

Another good example of this might an exercise where the student must create a model and call it `model`, and the auto-grader checks that that model can predict a hidden test set and get a `roc_auc > 0.85`. 

### Releasing the tests to other teachers and then to students 

There will be two repositories one for instructors and another for the students. If these don't exist ask devops on the [#dev-ops](https://ldsacademy.slack.com/messages/C9YRC295X) channel.

Once you are happy with your notebook you will need to
1. Push all changes to the instructors Github repository.
1. Ask devops to update the students Github repository.
1. Make sure that it runs and all exercises can be done

WARNING: Don't make any changes directly to the exercise notebook in the students repository. This includes renaming the file and moving it's location relative to the data.

### Solution to common problems (please add them here as you find and solve new ones) 

#### `Solution detected in a non-solution cell`
> Probably means you forgot to label a cell as Autograded answer. Go back to the notebook, `view —> cell toolbar —> create assignment`, and check if the cells are correctly labeled.
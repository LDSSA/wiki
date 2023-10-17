---
title: Using nbgrader for Exercise Notebooks
category: Instructors
order: 4
---

## What is nbgrader? 
 
[nbgrader](https://nbgrader.readthedocs.io/en/stable/) is "A system for assigning and grading notebooks". For anyone who's ever done a Coursera course, it looks  quite similar to their exercises. 

<img src="https://i.stack.imgur.com/7y2Na.png" width="600" />

In the Academy, we use nbgrader for the Exercise Notebooks. The instructor repo README has a short guide how to use it.

## How do I get started? 
nbgrader is included in the requirements file for your learning unit. You just need to activate the extensions to use it in the instructor mode:

```
jupyter nbextension install --sys-prefix --py nbgrader --overwrite
jupyter nbextension enable --sys-prefix --py nbgrader
jupyter serverextension enable --sys-prefix --py nbgrader
```

You might need to reactivate your virtual environment afterwards.

If you are creating a completely new Exercise Notebook, you need to add the grading. Go to `view —> cell toolbar —> create assignment`. You should start seeing cells in a different mode, like this:

<img src="https://preview.ibb.co/i8nSzx/Screen_Shot_2018_04_08_at_8_38_31_PM.png" width="600" />

## Turning your Exercises Notebook into an auto-graded work of art 

There are 4 types of cells: 
1. `Read-only` - use these when you want to make a cell uneditable. The cells describing the exercise tasks should be like this.
2. `Manually Graded Answer` - We are not using manual grading.
3. `Autograded Answer` - Cells where the students have to fill in code.
4. `Autograder tests` - The tests that the student's answer will have to pass.  

<img src="https://i.ibb.co/mt4b05w/Screen-Shot-2018-04-08-at-8-45-19-PM.png width="600" />

### Autograded Answer cells 

To make an auto-graded answer cell, just edit your existing exercises so that the solution is between `### BEGIN SOLUTION` and `### END SOLUTION`. 

In order to give the students stucture, you will probably want to have multiple blocks alternating with some instructions. Ideally the students should be focused only on the new concept they have just learned, not on solving Python problems. If the concept is easy you can of course give them a very "bare bones" function to complete, but should there be any level of complexity consider giving them the intermediate steps in the form of comments. 

<img src="https://image.ibb.co/gba5Kx/Screen_Shot_2018_04_08_at_8_57_55_PM.png" width="900" />   

The students will not see the answers, obviously. To see how students see the notebook, use `ldsagrader`:

   ```bash
   pip install ldsagrader
   ldsagrader notebook clear "Exercise notebook.ipynb" --output="Exercise notebook student.ipynb" --allow-hidden-tests=true
   ```
The second command will create the student version of the notebook without the solutions. 

In our example, this is what the student sees: 
<img src="https://image.ibb.co/fqeeCH/Screen_Shot_2018_04_08_at_9_06_27_PM.png" width="900" />   
*Note: There is no need to add `YOUR CODE HERE`. nbgrader will replace all of the code in the solutions block and replace it with this string.*

### Expected output
This is useful in the Python prep course where students are beginning with Python. In the Academy, we assume a working level of Python and better debugging skills, so it is not necessary.
  
The expected output can be added as normal cells. You can take some output your expect, and paste it in markdown in a cell. This allows students to check their logic, without having to submit the notebook or reverse engineer the actual tests. See an example of a test cell and an expected output cell:

<img src="https://image.ibb.co/hDdHzx/Screen_Shot_2018_04_08_at_9_11_41_PM.png" width="900" />  

### Autograded Test cells 
Great, now to evaluate that the student's implementation actually works. 
<img src="https://image.ibb.co/dbGLKx/Screen_Shot_2018_04_08_at_9_17_45_PM.png" width="900" />  

A few things to notice here:   
1. The cell is now `Autograder tests`.
2. The cell has points. If it raises errors, the student does not get those points. Make your entire Exercise Notebook's points sum 20, so that the grading system is coherent.   
3. In this case, some tests were hidden, and others weren't. Do not use hidden tests. If you need to hide a simple answer, use hashes.
4. Using `math.isclose` may be better than using `isequal` or `==`. For instance, in that last example, the correct answer was `-15.999999999999996`, so we compared it to `-16`, with a tolerance of `abs_tol=0.001`

#### Using the `inspect` module for better asserts 
There are a few common errors that students make, such as forgetting to return, or using globals accidentally. We can use the `inspect` module to check the function as if it were text. Again, this is more useful in the Python prep course and not really necessary in the Academy.

Here is an example of a messed up student answer: 
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

Not all questions should be "insert code here". Sometimes we want to test the student's workflow or the ability to explore a dataset. 
This is an example of how to make an open form answer, which can still be validated by the auto-grader (it will check if the answers in the `analysis` dictionary are correct, and if more than 1 answer is viable, the auto-grader's test can just do an `or` operation.
 
<img src="https://image.ibb.co/bxO36c/Screen_Shot_2018_04_08_at_9_24_20_PM.png" width="900" />  

Another good example of this might an exercise where the student should create a model and call it `model`, and the autograder checks that the model can predict a hidden test set and get a `roc_auc > 0.85`. 

### Solution to common problems (please add them here as you find and solve new ones) 

* Solution detected in a non-solution cell
   Probably means that you forgot to label a cell as Autograded answer. Go back to the notebook, `view —> cell toolbar —> create assignment`, and check if the cells are correctly labeled.
* Duplicated cell id
  This can happen when you create new cells in the exercise notebook by copying existing cells. You can add a new cell and copy the contents of the duplicated id cell. It can also help to set the cell type to nothing (`-`) and then to the desired type again.

# Notes for Academy Python requirements going forward

## Notes
* [Meaning of major and minor version](https://the-hitchhikers-guide-to-packaging.readthedocs.io/en/latest/specification.html#sequence-based-scheme)
* [Python Wheels](https://pythonwheels.com/)

## Somme issues we've encountered
This is just a small list of issues we've encountered with specifying Python 
requirements.
Most of them occurred during Batch 4, since in previous batches using Conda 
allowed us to avoid most of the issues described in the following sections.


### 1. Missing system libraries (packages without wheels)
Some Python packages require system libraries to build or run.
One example is the `graphviz` package in S01/SLU13 which requires the 
`graphviz` system package.
Another is the `psycopg2` package (although there is `psycopg2-binary` that 
can be used as an alternative).
Installing the requirement will fail if the dependency is not installed no 
matter the version.


### 2. Missing wheel for Python version
Python wheels were developed as a solution for issue 1. and a lot of packages
support them.
Wheels have all the dependencies the package needs to run pre-built, therefore
there's no need to install system packages to install.
However, wheels may be specific for a given Python minor version, and as these 
are produced when the package version is released Python versions released
after the package may not be supported.
Since if a wheel is not found Python tries to build it, this is only an issue 
if 1. is also the case.
This was the case for example with `matplotlib==3.1.1`, it was released before
Python 3.8 and needs different wheels for each Python minor version.
To build locally during install it needs `freetype2` development system
libraries.


### 3. Unsupported python version for the module
Python packages over time drop support for older Python versions, some more 
aggressively than others.
We encountered this with IPython, from the 
[IPython Github Repo](https://github.com/ipython/ipython):
> IPython versions and Python Support
>
> Starting with IPython 7.10, IPython follows NEP 29
>
> IPython 7.17+ requires Python version 3.7 and above.
>
> IPython 7.10+ requires Python version 3.6 and above.
>
> IPython 7.0 requires Python version 3.5 and above.
>
> IPython 6.x requires Python version 3.3 and above.


### 4. Changes in module with unpinned requirements
This issue arises when a Python package changes the name or signature of some
component (e.g. `def fcn(a, b):` is changed to `def fcn(a, b, c):`).

Since we've always had pinned dependencies the only instance of this was during
Batch 3 capstone.
The students produced their models with the current Pandas version and
the requirements for the deployment had an older version (they weren't 
updated after Batch 2).
The between the two versions they had changed signatures for several
model functions.


## Mitigating the issues
Ideally, all of the issues mentioned in the previous section should be caught 
in the CI pipeline and never reach the students.
During Batch 4 several issues conspired and a lot more of these issues
were not caught in the CI pipeline (for Batch 4 we moved from `conda` to `pip`
and dropped support for Windows).

Since we did not enforce a Python minor there were students using versions from
Python 3.6 to Python 3.8 (and even 3.9 after a brew update that was later 
downgraded, I think).
Also, the container running validation and running the notebooks was running
Python 3.7 and some learning units kept the package versions in the 
requirements from Batch 3.

### 1. Missing system libraries (packages without wheels)
All of these issues were caught in the CI pipeline.

### 2. Missing wheel for Python version
Students using Python minors above 3.7+ had this issue in several learning 
units.
There are 3 possible solutions for this issue:

1. Enforce Python minor (both students and instructors).

Means writing student and instructor documentation to install
the supported Python minor on each of the supported setups (Ubuntu, MacOS,
Ubuntu on WSL and Ubuntu on VMWare).

2. Add system dependencies to the learning unit readme for students using

Python minors that don't have a wheel.
Requires identifying which system dependencies are not installed in each
supported setup (really hard task).

3. Run validation on any supported Python minor (which is currently unclear in 
the setup).

Easiest solution and currently being implemented at the CI level (event though
it's late).
Will require updating the versions in requirements (and that may cause
issue 3).
Requires defining what are supported Python minors, in the long-run has the
disadvantage of having us support several combinations.

### 3. Unsupported python version for the module
Students using the default Ubuntu Python minor (3.6 at the time) encountered 
this issue for IPython because the CI container was running Python 3.7.

1. Enforce Python minor (both students and instructors).

See above.

3. Run validation on any supported Python minor (which is currently unclear in 
the setup).

A package version must be selected that runs on all supported Python minors
(usually always possible, but not so sure anymore).


### 4. Changes in module with unpinned requirements
Didn't have this issue.


### Personal opinion
Most of these issues are automatically nulled if we move back to conda
and always include the Python minor in the environment file.
Conda packages also install any system dependency that may be required.
The disadvantages are that instructors have to create the environment
file and pin the Python packages by hand.

Enforcing a Python minor version also deals with most of these issues
but will require more steps during setup and certainly more mistakes
of not using the correct Python if multiple are installed (already 
happens in systems with Python 2.x).

Just a side note, special attention has to be paid in the capstone to ensure 
the same requirements are used to produce and consume the model.
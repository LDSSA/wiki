## Evaluating the capstone

For each of the sections / topics available in the [grading criteria](https://docs.google.com/spreadsheets/d/1K8X7xNIi7CKIjtO2bEqWKxMhrRLKBYAHDJGwrg2cwjo/edit?usp=sharing), the following document provides some extra guidelines that are less subjective about what should be looked for.

If a student does not receive a passing grade because they are missing something critical, put your notes into a google doc and link to it in the spreadsheet. Then if we decide we would like to give the students a chance to fix the report and graduate the Academy, this will hold the corrections that they will be expected to make.

## Grading Scale

Since the most important thing that we need to know is whether they have done a passing job on the capstone, we will use a **0-2** scale for each section of each of the reports with the following meanings:

0. Did not address the issue.
1. Satisfactorily addressed the issue.
2. Deserves a freakin' award for the poetry.

In order to pass, a student cannot have any 0s on any of the sections. If the student has any 0s for any sections, they will need to amend the report, add it back in, re-submit and have it re-graded at a later date if they are to receive a passing grade.

## Report 1

### Section 1 - Abstract

- Mentioned the type of dataset
- Mentioned the key stakeholders
- Mentioned each of the important steps (EDA, Deployment, what the rest of the document is about)

### Section 2 - Context

- Did they identify and understand what a deductible is?
  - From [healthcare.gov](https://www.healthcare.gov/glossary/deductible/): The amount you pay for covered health care services before your insurance plan starts to pay. With a $2,000 deductible, for example, you pay the first $2,000 of covered services yourself.
- Did they understand what the consequences of adjusting a deductible might be?

### Section 3 - Data

- Mentioned 8 features
    - All categorical except for age
- Mentioned the other_factor* features have high null counts
- Mentioned the number of observations
- Identified the very limited range in ages
- Identified how imbalanced the dataset was

### Section 4 - Modelling

- Did they get a baseline model that achieves ~0.59 ROC_AUC with a reasonable-sized test set of 70/30 or 80/20?
- Did they keep it simple? There is not much signal in the dataset so it is preferable that they keep with a simple pipeline and some tried and true very simple model.

### Section 5 - Deployment

- Nothing magical here. They should just mention the important parts and then reference the learning material or documentation in the necessary places.

### Section 6 - Results and key risks

- The data was quite incomplete in a few dimensions (age in particular) and the live data could well end up outside of this?
- Did they mention that the dataset has low signal and thus the deployed model is going to have a very difficult time making accurate predictions for a use case that can have a huge impact on peoples lives?

### Section 7 - Conclusions and Discussion

This is quite subjective. Anything that shows they thought critically about the project

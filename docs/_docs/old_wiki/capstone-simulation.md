## PSA

The return format from the simulator is:

```py
{"ContrabandIndicator": True}
```

## PSA2 - Report feedback

Since the capstone is pass-fail (you must pass all sections of both reports in order to pass the course)
we are going to allow for one round of fixes after our feedback ONLY in the case where we feel you put in
an honest effort and missed / forgot something. 

The feedback and requests for changes will be submitted via comments in your google doc so it is your responsibility to keep an eye on those! You will receive feedback during the next few weeks on both of your reports as we will be continuously grading them throughout. 

When you get feedback, fix it on the document, and reply on the comment to confirm you've changed it. Do not answer in the comment, nor resolve it. You may of course ask clarifying questions if you don't understand the feedback. 

The deadline for fixing anything requested by the instructors will be February 15th. After February 15th, we 
will spend a week going through all of the comments that we made and seeing if the changes are good enough 
to consider the previously failed section a pass.


# Report Due Dates and submissions

You should check the code and report into your `batch3-workspace` repo that
also contains the rest of the work you've done at the academy. This can
be done by simply copying the files over to the new repo. You should
then add the github users `PedroGFonseca` and `hershaw` to your repo and 
we'll take care of distributing it for grading.

We will check the commit times of the files to ensure that the reports were 
submitted before the deadline.

## For Honors Consideration

- Report #1: Due on Wednesday January 15th by midnight
- Report #2: Due on Sunday January 26th by midnight

Notice that report 1 due date is on January 15th. If you have
a working deployed model and submit the report by this
date, you will be considered for honors despite the original
date being this past weekend.

## For Regular Graduation

- Report #1: Due on Sunday January 19th by midnight
- Report #2: Due on Sunday February 2nd by midnight

# Capstone Simulation: What to expect

By now have or are close to having a working model online and the question
becomes, what's next?
Please read this section carefully as there are a couple of steps you will
have to take.

First of all you'll need to register your app in the portal.
In the top navigation bar there is now a "Capstones" section, head over and 
select the item descriptively called "Capstone".
You will be taken to a web page to input your application url (e.g. 
`https://my-awsome-heroku-model.herokuapp.com`).

On Sunday, January 12th, (if you are able to) you should have your application 
registered and online. 
During the afternoon starting at 14:00 we will do at least one dry run.
This will give us all a chance to fix any last minute bugs both in your 
applications and the simulator responsible for sending the data.

Even if you're not able to be there while we're sending data it's a good idea 
to give your application logs a look and check there's nothing unexpected.

After the dry run and before starting the simulation we will reset 
the simulator and you will reset you database (see [tips](#tips)).
Everything will then be set to start receiving the data, which will start
at 22:00.

During the simulation you start by receiving new observations followed a day 
later by updates for the observations you have received.
You will receive updates for the first half of the total observation data
and you can choose to retrain/redeploy you model at any time.

*Milestones*
* By 2020-01-11 deploy and register application
* 2020-01-12 14:00 dry run starts
* After the dry run and before 2020-01-12 22:00 reset application database
* From 2020-01-12 22:00 to 2020-01-17 22:00 receive observations
* From 2020-01-13 22:00 to 2020-01-16 22:00 receive updates

## Capstone: Extension
For those that want to make use of the extension the workflow is very similar
with two exceptions:
* Register the application in the capstone named: *Capstone Extension*
* All dates are shifted one week

*Milestones*
* By 2020-01-19 deploy and register application
* 2020-01-19 14:00 dry run starts
* After the dry run and before 2020-01-19 22:00 reset application database
* From 2020-01-19 22:00 to 2020-01-24 22:00 receive observations
* From 2020-01-20 22:00 to 2020-01-23 22:00 receive updates

## Tips
* Resetting your database: Open the _Heroku Postgres_ addon and under 
_Settings_ there is the option to reset the database. You will need to 
restart the app after resetting the database with `heroku restart`.
* Downloading database: Heroku provides a simple way of retrieving any data 
you might need [here](https://devcenter.heroku.com/articles/dataclips).



# Project Info

Project title: EGA Data Submission database (mEGAdata)

Project short title (30 characters): mEGAdata

URL of project idea page: 

--------------
Table of content:

[TOC]

--------------

# Biographical Information

I am a 4th Year Integrated Dual Degree Student at IIT (BHU). 


## My Research work.

I  have worked on predicting software clone evolution, we decided to take forward my previous work, part of my minor project. We analyzed methods and metrics for clone evolution on both same and different version of the software. We were able to improve by 50% over ARIMA/linear/Exponential-Smoothing methods by using a hybrid model for number series prediction. This work lead to a successfully accepted paper in “ICEECS 2015”. Further, this inspired me to look into field of data analysis, which i was eventually able to carry out during my Internship at Goldman Sachs with data science team.

## Contact Information

Student name: Sainyam Kapoor

Melange Link_id:  

Student postal address: House number 453, Sector - 7, Urban Estate, Gurgaon-122001, Haryana, India

Telephone(s): (+91)-860-120-1034

Email(s): [Sainyam Kapoor](<sainyam1994@gmail.com>), [Alterate Email](<sainyam.kapoor.cse12@itbhu.ac.in>)

Other communications channels: Skype/Google+, etc. : Skype:saikpr, GitHub:saikpr, BitBucket:sainyamkapoor


## Student Affiliation

Institution: Indian Institute of Technology, Benaras Hindu University, Varanasi (IIT-BHU)

Program: Integrated Dual Degree in Computer Science and Engineering (Bachelors and Masters)

Stage of completion: Almost completed with my Bachelors Courses, partial Master credits also completed. Expected to complete by May 2017.

Contact to verify: Dr. K.K. Shukla, Head, Computer Science and Engineering. ([Dr. K.K. Shukla](<kkshukle.cse@iitbhu.ac.in>))


# Schedule Conflicts

Please list any schedule conflict that will interfere with you treating your proposed C3G GCoC project as a full time job in the summer.  If you are applying to other internships, or have other commitments, list them.

Presently i have no commitments for any full time job in summer.
I have already applied to CERN Openlab intership, but its a very far fetched dream.

I might go for a vacation for a period of no more than 7 days, in middle of summer (as it gets very hot in Varanasi).

My college will start from last week of July (after 24th, i will be bit busy so will be cleaning up the code and final documentation )

# Mentors

Mentor names: David Bujold 

Mentor emails: [David Bujold](<david.bujold@computationalgenomics.ca>) (david.bujold@computationalgenomics.ca)

Mentor link_ids: 

Have you been in touch with the mentors? When and how? 

I exchanged emails with David Bujold discusing about the project and the selection tests. 
He has given me a good picture about what is to expected of me (both the small and big picture).
I hope to learn a lot from him during this summer.



# Synopsis (max 150 words)
 
Would you like me to reduce your mundane tasks(managerial, upload etc) such as those of uploading the data to EGA Repository.
If yes, this is the proposal for you.

Let me introduce to you, mEGAdata an application (written by my mentor David) it reduces the task of making the XML, uploading of metadata etc to EGA Repository.

But there is always a problem of initial setup and maintainence, this is where my work will come. I will make it easier for you to get started. Hope it gives you an idea, continue reading for more information.


# Benefits to Community (max 250 words)

In Today's world, a lot of time is spend in non productive work such as arranging the data, metadata etc in directories and databases. But what is missed is that most of this work doesnot require any special skillset, still they are done by highly trained professionals who can be doing something productive with their time and return back to society. But still given the privacy concerns these tasks are done by these professionals. What if we create a application and make it easily distributable and maintainable for the user to do some of these tasks. Time saved from this can be better utilised in doing some good research work.

Just by me spending my summer to work on this problem, some good researchers time will be saved.(which would be more valuable to the time i spend in creating the application)

I will be making it easier for the user to obtain a copy of the application which will be simple (one or two liner) to get started.
and not much setup will also be required.

By Open-Sourcing the work, society will be motivated to reduce the time wasted by people doing same things again and again. Today mEGAdata is being used by McGill EMC, but by making easier for others to access it, can be used by numerous other centers doing similar work. and this will also help McGill EMC, by other members adding some feature they missed or ignored. That's the beauty of open source.


# Coding Plan & Methods

### Describe in detail your plan for completing the work.  What functions will be written, how and when will you do design, how will you verify the results of your coding?  Each project is different, please make your application appropriate to the work you propose.  

First i will start by switching to an SQLite database, removing all MySQL dependencies. Making sure that the Database Schema is atleast in BCNF.
Once the base is defined and correct, i start to port the code to Python 3.5, because python2.7 is already in maintaince. I can try to support both or completely ignore this task if the requirement is not as such.

They i will explore VM vs Linux Containers vs docker for our task, which will be an overkill and which will be the minimal requirement.
Reason i want to explore Vagrant is for ability to use it over windows and linux both.

I will try to answer following questions:
*Which will help get the work done and be easier to support in Future
*If i go with linux container, would i need a supervisory daemon or a multiple dockers running and coordinating. If supervisory daemon, would supervisord work or some other manager.

once the Study is completed, i will start to port the repository to the appropriate container(vm or docker).

In mean time, i will also be writing a module to be added to mEGAdata which will create a BASH script with ascp, to make it easier for User to upload md5 and data to EGA.



### Describe perceived obstacles and challenges, and how you plan to overcome them.

Flask-Stormpath, which is requirement for the project is still on python2.7 (they are waiting for facebook-python-sdk to be upgraded to python3, but they will be cutting a new release in a week or so, which will build without facebook integration [Issue #26](https://github.com/stormpath/stormpath-flask/issues/26).


# Timeline


### Provide a detailed timeline of how you plan to spend your summer, organized by deliverables.  Don't leave testing and documentation for last, as that's almost a guarantee of a failed project. 

From April'16 to 22 May'16, survey of how this problem is solved and various pitfalls. Finalizing the Entity-Relationship Diagram.

From 22 May'16 to 5 June'16, SQlite migration should be completed.

From 6 June'16 to 19 June'16, Major python3.5 porting should be completed.

By 28 June'16, Final study should be completed and we should have a final decision on which to implement and how.

From 29 June'16 to 19th July'16, Prototyping of the solution is expected to be completed. First week to get to know of how to do the things that are required to be implemented. and next week to create a prototype.

From 19 July'16 to 9 August'16, Final Solution to be implemented and bash script generator Completed.

From 10 to 23 August'16, final documentation, blogs, video(no promises), clean up and final push.


### Final Deliverable:

A docker or Vagrant or any other such file, which once run will pack the application and make it easier for us to access.

For users: a simple script to download and create the application locally for easier uploads to EGA.

### What is your contingency plan for things not going to schedule? 

First, I will need to provide a detailed timeline which will be updated with achievements and/or failures. Second, possibly a weekly sync up between mentors and students, in order to provide efficient support. If required, deliverables to be redecided to avoid roadblocks and ensure that it can be completed within the time-frame.

# Management of Coding Project

### How do you propose to ensure code is submitted / tested?

I will publish a blog with demo of the minimal number of steps to get the application running. (Will try to publish a video also, but no promises)

### How often do you plan to commit?  What changes in commit behavior would indicate a problem?

I plan to push to my branch once every 3-4 days.  
If i haven't pushed in a week and my mentor is not aware of any emergency or personal commitments, then that would indicate a problem. This should never happen.

# Final Test

Describe the qualification test that you have submitted to you project mentors.  If feasible, include code, details, output, and example of similar coding problems that you have solved.

Test will be quite simple. A simple script to be downloaded and run on a Linux system which will result in installing of a complete web portal for easier upload to EGA.

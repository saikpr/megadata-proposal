# Project Info

Project title: EGA Data Submission database (mEGAdata)

Project short title (30 characters): mEGAdata

URL of project idea page: 

--------------
Table of content:

[TOC]

--------------

# Biographical Information

I am a 4th Year Integrated Dual Degree Student at IIT (BHU). I am a technical enthusiast and my belief is to use coding or any activity(as such) for greater good of society or at the very least myself.


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

Presently I have no commitments for any full time job in summers.
I have already applied to CERN Openlab intership, but its a pretty very far fetched dream.

I might go for a vacation for a period of no more than 7 days, in middle of summer (as it gets scorching hot in Varanasi).

My college will start from last week of July (after 24th, i will be bit busy so will be cleaning up the code and finalising the documentation )

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

Let me introduce to you, mEGAdata which is a database-driven lightweight web application for archiving genomics projects metadata on samples and experiments, with the goal of easing submission to the [European Genome-phenome Archive (EGA)](https://www.ebi.ac.uk/ega/home).

But there is always a problem of initial setup and maintainence(end users favor packages that are functional and easy to install!), this is where my work will come. I will make it easier to get started. Hope it gives you an idea, continue reading for more information.


# Benefits to Community (max 250 words)

In Today's world, a lot of time is spend in non productive work such as arranging the data, metadata etc in directories and databases. But what is missed is that most of this work doesnot require any special skillset, still they are done by highly trained professionals who can be doing something productive with their time and return back to society. But still given the privacy concerns these tasks are done by these professionals. What if we create a application and make it easily distributable and maintainable for the user to do some of these tasks. Time saved from this can be better utilised in doing some research.

Just by me spending my summer to work on this problem, some researcher's time will be saved. Further it will reduce the risk factor involved in failure.

I will be making it easier for the user to obtain a copy of the application which will be simple (one or two liner command) to get started and without much setup.

By Open-Sourcing the work, society will be motivated to reduce the time wasted in such mundane tasks. Today mEGAdata is being used by McGill EMC, but by making it easier for others to access it, can be used by numerous other centers doing similar work. and this will also help McGill EMC, as other members will add some feature which EMC must have missed or ignored. That's the beauty of open source.


# Coding Plan & Methods

### Describe in detail your plan for completing the work.  What functions will be written, how and when will you do design, how will you verify the results of your coding?  Each project is different, please make your application appropriate to the work you propose.  

*Must Have :
    * Switching to SQLite, removing all MySQL dependencies.
    * Ensuring that Database Schema is in BCNF, or atleast 3NF normalised form
    * Studing VM(Vagrant or similar) vs Linux Containers(LxC) vs Docker for portability. (Vagrant because of the ability to build on windows) (dependent on various factors such as future support, supervisory daemon or seperate dockers)
    * Porting the Code to Python3.x(Most probably Python3.5)
    * Web Page for Assays Metadata Management, supporting create/update/delete and validating the consistency of Database at the updation.
    * Web Page for Sequencing runs metadata management, supporting multiple sequencing raw files, with pertaining metadata. Metadata to be stored in the database.
    * Incorporate sample properties editor in the web application
    * Studying various OAuth based authentication systems.
    * Based on above study, use the best integratable and secure to application
    * Deciding one of LxC, docker, Vagrant or any other alternative and starting the porting process.
    * Search facility through donors, samples, datasets, and their metadata

*Nice to Have:
    * Module to generate BASH script with ascp, to make it easier for user to upload the raw data and its md5 to EGA.
    * Support for both python2.7 and python3.x
    * In Web Page for Sequencing runs metadata management, Raw data server location and md5 checkums integration service.
    * BioPortal ontologies integration
        * This involves using the bioportal.bioontology.org to map metadata properties to a given ontology, by creating a custom Handsontable editor.
        * Example: A sample has a property called "Cell Type", that should map to the UBERON ontology. The custom editor will enable searching the UBERON ontology, identify the right term, and store in the database the connected ontology URI.
        * Bioportal has several tools that can be used for these kind of features. Example for UBERON: Try searching for "B Cell"in [https://bioportal.bioontology.org/ontologies/UBERON/?p=widgets](https://bioportal.bioontology.org/ontologies/UBERON/?p=widgets).
    * Bioinformatics downstream analysis metadata
        * Sequencing runs need processing by various analysis software. Software with versions, parameters used, etc. need to be stored from the interface.

### Describe perceived obstacles and challenges, and how you plan to overcome them.

Flask-Stormpath, which is requirement for the project is still on python2.7 (they are waiting for facebook-python-sdk to be upgraded to python3, but they will be cutting a new release in a week or so, which will build without facebook integration [Issue #26](https://github.com/stormpath/stormpath-flask/issues/26). Possibly shift to some other OAuth based authentication system.



# Timeline


### Provide a detailed timeline of how you plan to spend your summer, organized by deliverables.  Don't leave testing and documentation for last, as that's almost a guarantee of a failed project. 

From April'16 to 22 May'16, survey of OAuth-based authentication systems, possible sample properties editor, VM(Vagrant or similar) vs Linux Containers(LxC) vs Docker for portability study, and designing the Entity-Relationship Diagram for the final application.

From 22 May'16 to 5 June'16, SQlite migration should be completed.

From 6 June'16 to 12 June'16, Major python3.5 porting should be completed.

From 12 June'16 to 28th June'16, Web Page for Assays Metadata Management

By 28 June'16, I should have completed 50% of the activities. Documentation and unit testing of all modules which have be done should be ready

From 29 June'16 to 5th July'16, Web Page for Sequencing runs metadata management.

From 5 July'16 to 24 July'16, OAuth based authentication systems, BASH script with ascp, global searching

From 24 July to 10 August'16, Incorporate sample properties editor, finally containerizing the application

From 10 Aug to 24 Aug'16 ,final documentation, functional testing, blog-entry, video(no promises), clean up and final push.


### Final Deliverable:

An easier way for users to deploy their own version of mEGAdata for upload to EGA Repository. The web application will be packed in form of a container( full vm or docker app) making it easier to deploy and maintain.


For users: a simple script to download and create the application locally for easier uploads to EGA.

Note: More definite deliverables already defined in Coding Plans & Methods

### What is your contingency plan for things not going to schedule? 

First, I will need to provide a detailed timeline which will be updated with achievements and/or failures. Second, possibly a weekly sync up with mentor, in order to provide efficient support. If required, deliverables to be redecided to avoid roadblocks and ensure that major work is completed within the time-frame.

# Management of Coding Project

### How do you propose to ensure code is submitted / tested?

Weekly Code Reviews, and approval of Mentor before finally pushing the major branch.

I will publish a blog with demo of the minimal number of steps to get the application running. (Will try to publish a video also, but no promises)

### How often do you plan to commit?  What changes in commit behavior would indicate a problem?

I plan to push to my branch once every 3-4 days.  
If i haven't pushed in a week and my mentor is not aware of any emergency or personal commitments, then that would indicate a problem. This actually should never happen.

# Final Test

Describe the qualification test that you have submitted to you project mentors.  If feasible, include code, details, output, and example of similar coding problems that you have solved.

Test will be quite simple. A simple script to be downloaded and run on a Linux system which will result in installing of a complete web portal for easier upload to EGA, and will satisfy all the stated features as above.


-----------------------------

## Additional Comments


I would like to heartily thank David Bujold, for patiently answering several queries about the project and reviewing my selection test. He was able to point me in right direction and helped by providing ideas and action plan. Thanks for bearing with my childish queries at times.
-----------------------------

### Selection test:

Basic Implementation:
    
*BitBucket Repo : [https://bitbucket.org/sainyamkapoor/simple_api_swag](https://bitbucket.org/sainyamkapoor/simple_api_swag)
*Angular JS Application : [http://api.simpleapi.ml:8080/static/index.html](http://api.simpleapi.ml:8080/static/index.html)
*Api End point : [http://api.simpleapi.ml:8080/api/v1.0/phone](http://api.simpleapi.ml:8080/api/v1.0/phone)

Alternative Implementation with swagger(Recommended):
    
*BitBucket Repo : [https://bitbucket.org/sainyamkapoor/simple_api_swag](https://bitbucket.org/sainyamkapoor/simple_api_swag)
*Angular JS Application : [http://api.simpleapi.ml/static/index.html](http://api.simpleapi.ml/static/index.html)
*Api End point : [http://api.simpleapi.ml/api/v1.0/phone](http://api.simpleapi.ml/api/v1.0/phone)
*Swagger UI: [http://api.simpleapi.ml/api/spec.html](http://api.simpleapi.ml/api/spec.html)
    
    
    PUT,POST,GET requests are documented in the bitbucket repo.

-----------------------------
-----------------------------
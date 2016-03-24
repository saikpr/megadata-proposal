# Project Info

Project Title: EGA Data Submission database (mEGAdata)

Project short title (30 characters): mEGAdata

URL of project idea page: 

--------------
Table of content:

[TOC]

--------------

# Biographical Information

I am a 4th Year Integrated Dual Degree Student at IIT (BHU). I am a technology enthusiast, and my belief is to use coding or any activity(as such) for the greater good of society or at the very least myself.


## My Research work.

I  have worked on predicting software clone evolution; we decided to take forward my previous work, part of my minor project. We analyzed methods and metrics for clone evolution on both same and different version of the software. We were able to improve by 50% over ARIMA/linear/Exponential-Smoothing methods by using a hybrid model for number series prediction. This work lead to a successfully accepted paper in “ICEECS 2015.” Further, this inspired me to look into the field of data analysis, which I was eventually able to carry out during my Internship at Goldman Sachs with data science team.

## Contact Information

Student name: Sainyam Kapoor

Melange Link_id:  Melange User:saikpr, Link ID has been discontinued from GSoC's Site.

Student postal address: House number 453, Sector - 7, Urban Estate, Gurgaon-122001, Haryana, India

Telephone(s): (+91)-860-120-1034

Email(s): [Sainyam Kapoor](<sainyam1994@gmail.com>), [Alterate Email](<sainyam.kapoor.cse12@itbhu.ac.in>)

Other communications channels: Skype/Google+, etc. : Skype:saikpr, GitHub:saikpr, BitBucket:sainyamkapoor


## Student Affiliation

Institution: Indian Institute of Technology, Benaras Hindu University, Varanasi (IIT-BHU)

Program: Integrated Dual Degree in Computer Science and Engineering (Bachelors and Masters)

Stage of completion: Almost completed my Bachelor Courses, partial Master credits also gained. Expected to complete by May 2017.

Contact to verify: Dr. K.K. Shukla, Head, Computer Science, and Engineering. ([Dr. K.K. Shukla](<kkshukle.cse@iitbhu.ac.in>))


# Schedule Conflicts

### Please list any schedule conflict that will interfere with you treating your proposed C3G GCoC project as a full-time job in the summer.  If you are applying for other internships or have other commitments, list them.

Presently I have no commitments for any full-time job in summers.
I have already applied to CERN Openlab intership, but it's a pretty very far fetched dream.

I might go for a vacation for no more than seven days, in the middle of summer (as it gets scorching hot in Varanasi).

My college will start from last week of July (after 24th, I will be bit busy so will be cleaning up the code and finalizing the documentation )

# Mentors

Mentor names: David Bujold 

Mentor emails: [David Bujold](<david.bujold@computationalgenomics.ca>) (david.bujold@computationalgenomics.ca)

Mentor link_ids: 

### Have you been in touch with the mentors? When and how? 

I exchanged emails with David Bujold discusing about the project and the selection tests. 
He has given me a good picture of what is to expected of me (both the small and big picture).
I hope to learn a lot from him during this summer.


# Synopsis (max 150 words)
 
Would you like me to reduce your mundane tasks(managerial, upload, etc.) such as those of uploading the data to EGA Repository?

If yes, this is the proposal for you.


Let me introduce to you, mEGAdata which is a database-driven lightweight web application for archiving genomics projects metadata on samples and experiments, with the goal of easing submission to the [European Genome-phenome Archive (EGA)](https://www.ebi.ac.uk/ega/home).

But there is always a problem of initial setup and maintainence(end users favor packages that are functional and easy to install!), this is where my work will come. I will make it simpler to get started. 
Hope this gives you an idea, continue reading for more information.


# Benefits to Community (max 250 words)

In Today's world, a lot of time is spent in nonproductive work such as organising the data, metadata, etc. in directories and databases. But what is missed is that most of this job does not require any unique skill set, still they are done by highly trained professionals, who instead can be doing something productive with their time and return back to society. But still given the privacy concerns, these professionals have to do these tasks. 

What if we create an application and make it easily distributable and maintainable for the user to do some of these tasks. Time saved from these tasks can be better utilized in doing research.

With me spending my summer to work on this problem, some researcher's time will be saved. Further, it will reduce the risk factor involved in the failure.

I will be making it easier for the user to obtain a copy of the application which will be simple (one or two liner command) to get started and without much setup.

By Open-Sourcing the work, society will be motivated to reduce the time wasted on such mundane tasks. Today mEGAdata is being used by McGill EMC, but by making it easier for others to access it, can be utilized by numerous other centers doing similar work. And this will also help McGill EMC as I will also be incorporating some new features in mEGAdata such as Assays Metadata Management, Sequencing runs metadata management etc. That's the beauty of open source.


# Coding Plan & Methods

### Describe in detail your plan for completing the work.  What functions will be written, how and when will you do design, how will you verify the results of your coding?  Each project is different; please make your application appropriate to the work you propose.  

####Must Have:
    
* Normalisation of Database Schema.
    * Logic: Normalisation is the process of decomposing tables such that data redundancy is reduced.
    * Technical Details:  Redundancy of data is a known source of inconsistency. We will be mapping all the dependencies and then apply transformation to convert to BCNF or atleast 3NF form. Normalised form might be traded off for performance on discussion with mentor.
    * Expectations: After this task is completed, we should have reduced chances of data inconsistency.
* Switching to SQLite, removing all MySQL dependencies. 
    * Logic: Size of Metadata will be limited, so we don't necessarily need a full fledged Database, since SQLite is embedded into Client program, we will be reducing the complexity of the system. 
    * Technical Details: SQLite has bindings to many programming languages(Python also). In this step, i will remove all MySQL binding and flask_peewee from requirement. and replace it with SQLite bindings.
    * Expectations: After this task is complete, we should have reduced one requirement in installing the portal.
* Studying Various Containerising Techniques 
    * Logic: End users favor packages that are functional and easy to install!
    * Technical Details: We will study Vagrant, LxC and Docker for portability. We decided to include Vagrant also, because of ease to build on windows also. This Study will be decide various factors such as future support, supervisory daemon or seperate dockers.
    * Expectations: By the End of this task, we should have finalised the technique we will go ahead.
* Porting the Code to Python3.x(Most probably Python3.5)
    * Logic: Python2.7 has already entered maintenance stage and support will be discontinued after 2020.
    * Technical Details: Will use 2to3 application to port the code to Python3.5.
    * Expectations: By the End of this task, we should have equally functional application as before, with added benefit of future support.
* Web Page for Assays Metadata Management 
    * Logic: User should be able to do create/update/delete of Assays Metadata.
    * Technical Details: Will use MVC based Architecture for this, application will be responsible for validating the consistency of Database at each updation(such as preventing user to delete a metadata set if it is used by at least one dataset). This will be done by adding a REST Endpoint to the API, and using Angular JS to update the webpage in action.
    * Expectations: By the end of this task, we should have fully functional Web Page for Assays Metadata Management, supporting create, update & delete for Assays Metadata.
* Web Page for Sequencing runs metadata management
    * Logic: User should be able to do manage Sequencing runs metadata, supporting multiple sequencing raw files, with pertaining metadata.
    * Technical Details: Will use MVC based Architecture for this, application will be responsible for validating the consistency of Database at each updation(such as preventing user to delete a metadata set if it is used by at least one dataset). This will be done by adding a REST Endpoint to the API, and using Angular JS to update the webpage in action. Metadata to be stored in the database.
    * Expectations: By the end of this task, we should have fully functional Web Page for Sequencing runs metadata management, supporting options to manage Sequencing runs metadata over multiple squencing raw files.
* Incorporate sample properties editor in the web application
   * Logic: User should be able to Edit the properties of metadata on the application, instead of downloading, removing old entry and uploading new one.
   * Technical Details: Will add a Webpage to get the Metadata from Database, and add REST Endpoint to update the Metadata in the Database.
   * Expectations: By end of this task, we should be able to edit the metadata from the application itself.
* Studying various OAuth based authentication systems.
    * Logic: IPA(Identity, Policy, and Audit) are some of the important characteristics an application should support. But in this we  will study various ways to support Identity and Policy, Auditing will be a Nice to Have feature(will try to support in case time remains).
    * Technical Details: Read about OAuth vs  OpenID Connect, Google OAuth vs Mozilla Persona or Github Authenticator or any other service. Presently i am favouring Google OAuth but will try to find concrete proof to go ahead with that.
    * Expectations: By end of this task, we should have a clear idea of which protocol to implement.
* Integration of Authentication Mechanism:
    * Logic: users need to be authenticated to use the facility.
    * Technical Details: Will use Flask-OpenID or any such as determined from previous activity.
    * Expectations: By end, user should be able to authenticate themselves before using the facility.
* Containerisation of the Application
    * Logic: End users favor packages that are functional and easy to install!
    * Technical Details: Based on Previous study, will use one of the Containerising technique.
    * Expectations: If the decision is docker, a dockerfile can be expected to be output. If it LxC, a script to generate the container can be expected.
* Search facility through donors, samples, datasets, and their metadata
    * Logic: Its easier for user to search instead of going through list of datasets.
    * Technical Details: Will add tagging to each of the entry(assays, sequencing runs etc), along with indexing of metadata into a SQLite Table for easier searching. This will include creation of REST Api End Point, and Angular JS page to consume the data form this End Point.
    * Expectations: By end, user should be able to put his/her query in a searchbox, which should take it to another page where all the data items will be listed, with link to the particular data item.
    * Challenge: It will be a challenge to maintain heirarchy of access. i.e. either limiting the users to their groups information or to their experiments only. Initially i will limit to user's experiment only.
####Nice to Have:
* Module to generate BASH script with ascp, to make it easier for the user to upload the raw data and its md5 to EGA.
    * Logic: It should be easier for user to make a single call to a script and upload the raw data and its md5, and retry in case of failure.
    * Technical Details: BASH script will be created which will take the input as metadata and file name, will generate the md5 to confirm its integritity and try to upload using "ascp" to EGA.
    * Expectations: A single script to upload a file to repository
* Support for both python2.7 and python3.x (low priority)
    * Logic: Support for both would enable developer to import the module in majority of python script he wants. 
    * Technical Details: will try to use __future__ and other such module to maintain the backward compatibility
    * Expectations: Module will be importable in both the major versions of python.
* BioPortal ontologies integration
    * This involves using the bioportal.bioontology.org to map metadata properties to a given ontology, by creating a custom Handsontable editor.
    * Example: A sample has a property called "Cell Type," that should map to the UBERON ontology. The custom editor will enable searching the UBERON ontology, identify the right term, and store in the database the connected ontology URI.
    * Bioportal has several tools that can be used for this kind of features. Example for UBERON: Try searching for "B Cell" in [https://bioportal.bioontology.org/ontologies/UBERON/?p=widgets](https://bioportal.bioontology.org/ontologies/UBERON/?p=widgets).
* Bioinformatics downstream analysis metadata
    * Sequencing runs need processing by various analysis software. Software with versions, parameters used, etc. need to be stored from the interface.
* In Web Page for Sequencing runs metadata management, Raw data server location, and md5 checkums integration service.
    * Logic: Maintaining raw data server can be helpful for user to locate the data.
    * Technical Details: Maybe use SSH(authetication using SSH keys) to list the files in the directory, and using md5 to match to the data. Maybe add a rest call to the bash script, which will let the main system know where the data is located.
    * Expectations: Easier localability of data. 
* Script to migrate old MySQL data to new SQLite database, based on new schema.
    * Logic: It would be easier for guys at McGill to easily move their old database to new application.
    * Technical Details: A python script which will be parse through the database and import the data to sqlite database
    * Expectations: A single script to export the data from old database to new one.
### Describe perceived obstacles and challenges, and how you plan to overcome them.

Flask-Stormpath, which is a requirement for the project, is still on python2.7 (they are waiting for facebook-python-sdk to be upgraded to python3, but they will be cutting a new release in a week or so, which will build without facebook integration [Issue #26](https://github.com/stormpath/stormpath-flask/issues/26). Possibly shift to some other OAuth based authentication system.

In searching, It will be a challenge to maintain heirarchy of access. i.e. either limiting the users to their groups information or to their experiments only. Initially i will limit to user's data only.

In authentication. it will be a challenge to create groups, given that Google or anyother API will only return UUID, maybe add an administrator to coordinate users into group. But THis will be Good to have feature.

# Timeline


### Provide a detailed timeline of how you plan to spend your summer, organized by deliverables.  Don't leave testing and documentation for last, as that's almost a guarantee of a failed project. 

From April'16 to 22 May'16, survey of OAuth-based authentication systems, possible sample properties editor, VM(Vagrant or similar) vs. Linux Containers(LxC) vs. Docker for portability study, and designing the Entity-Relationship Diagram for the final application.

From 22 May'16 to 5 June'16, SQlite migration should be completed.

From 6 June'16 to 12 June'16, Major python3.5 porting should be completed.

From 12 June'16 to 28th June'16, Web Page for Assays Metadata Management

By 28 June'16, I should have completed 50% of the activities. Documentation and unit testing of all modules which have been done should be ready

From 29 June'16 to 5th July'16, Web Page for Sequencing runs metadata management.

From 5 July'16 to 24 July'16, OAuth-based authentication systems, BASH script with ascp, global searching

From 24 July to 10 August'16, Incorporate sample properties editor, finally containerisation of the application

From 10 Aug to 24 Aug'16, final documentation, functional testing, blog entry, video(no promises), clean up and final push.


### Final Deliverable:

An easier way for users to deploy their version of mEGAdata for upload to EGA Repository. The web application will be packed in the form of a container( full VM or Docker app) making it easier to deploy and maintain.

All the Expectations in Must have features will be meet.

A seperate API and a web Application will be result of this activity, which will allow user to create new applications to meet their future needs. 

For users: a simple script to download and create the application locally for easier uploads to EGA.

Note: More defined deliverables have already been listed in Coding Plans & Methods.

### What is your contingency plan for things not going to schedule? 

First, I will try to meet each deadline and a seperate Doc will be maintained with the achievements and failures. Second, possibly a weekly sync up with the mentor, to provide efficient support. If required, deliverables to be redecided to avoid roadblocks and ensure that major work is completed within the time-frame.

# Management of Coding Project

### How do you propose to ensure code is submitted/tested?

Weekly Code Reviews.
Since the project is defined with concrete modules, with expectations listed from the activity. Mentor will confirm that the expectations from each activity is meet. and that will maintained in a Google Sheet along with commit id.

After approval of Mentor, code will be finally pushed to the main branch.

I will publish a blog with the demo of the minimal number of steps to get the application running. (Will try to publish a video also, but no promises)

### How often do you plan to commit?  What changes in commit behavior would indicate a problem?

I plan to push to my branch once every 3-4 days.  
If I haven't pushed in a week, and my mentor is not aware of any emergency or personal commitments, then that would indicate a problem. This should never happen.

# Final Test

### Describe the qualification test that you have submitted to you project mentors.  If feasible, include code, details, output, and example of similar coding problems that you have solved.

Basic Implementation:
    
* BitBucket Repo : [https://bitbucket.org/sainyamkapoor/simple_api](https://bitbucket.org/sainyamkapoor/simple_api)
* Angular JS Application : [http://api.simpleapi.ml:8080/static/index.html](http://api.simpleapi.ml:8080/static/index.html)
* Api End point : [http://api.simpleapi.ml:8080/api/v1.0/phone](http://api.simpleapi.ml:8080/api/v1.0/phone)

Alternative Implementation with swagger(Recommended):
    
* BitBucket Repo : [https://bitbucket.org/sainyamkapoor/simple_api_swag](https://bitbucket.org/sainyamkapoor/simple_api_swag)
* Angular JS Application : [http://api.simpleapi.ml/static/index.html](http://api.simpleapi.ml/static/index.html)
* Api End point : [http://api.simpleapi.ml/api/v1.0/phone](http://api.simpleapi.ml/api/v1.0/phone)
* Swagger UI: [http://api.simpleapi.ml/api/spec.html](http://api.simpleapi.ml/api/spec.html)
    
    
PUT, POST, GET requests are documented in the bitbucket repo.


## Credits:

I would like to thank David Bujold, for patiently answering queries about the project and reviewing my selection test. He was able to point me in the right direction and helped me by providing ideas and action plan. Thanks for bearing with my childish queries at times.


-----------------------------
-----------------------------
# Project Info

- Project Title: EGA Data Submission database (mEGAdata)
- Project short title (30 characters): mEGAdata
- URL of project idea page: [Mugqic/gsoc2016](https://bitbucket.org/mugqic/gsoc2016/overview#markdown-header-ega-data-submission-database-megadata)


# Biographical Information

My Name is Sainyam Kapoor, and I am a 4th Year Integrated Dual Degree Student at Indian Institute of Technology (BHU), Varanasi (IIT BHU). I am a technology enthusiast, and my belief is to use coding or any activity (as such) for the greater good of society or at the very least myself. I have a strong background in Python, C & C++. I have previously done an internship with Data Science Team at Goldman Sachs, where I build a model for anomaly detection in GS's Internal Cloud, and I made a REST API as part of the final project.


## My Research work.

I have worked on predicting software clone evolution; we decided to take forward my previous work, part of my minor project. We analyzed methods and metrics for clone evolution on both same and different version of the software. We were able to improve by 50% over ARIMA/linear/Exponential-Smoothing methods by using a hybrid model for number series prediction. This work lead to a successfully accepted paper in “ICEECS 2015.” Further, this inspired me to look into the field of data analysis, which I was eventually able to carry out during my Internship at Goldman Sachs with data science team.

## Contact Information

- Student name: Sainyam Kapoor
- Mélange Link_id:  Mélange User:saikpr, Link ID has been discontinued from GSoC's Site.
- Student postal address: House number 453, Sector - 7, Urban Estate, Gurgaon-122001, Haryana, India
- Telephone(s): (+91)-860-120-1034
- Email(s): [Sainyam Kapoor](<sainyam1994@gmail.com>), [Alternate Email](<sainyam.kapoor.cse12@itbhu.ac.in>)
- Other communications channels: Skype/Google+, etc.: Skype:saikpr, GitHub:saikpr, BitBucket:sainyamkapoor

## Student Affiliation

- Institution: Indian Institute of Technology, Banaras Hindu University, Varanasi (IIT-BHU)
- Program: Integrated Dual Degree in Computer Science and Engineering (Bachelors and Masters)
- Stage of completion: Currently in 4th Year. I have almost completed my Bachelor Courses, partial Master credits also gained. Expected to complete by May 2017.
- Contact to verify: Dr. K.K. Shukla, Head, Computer Science and Engineering. ([Dr. K.K. Shukla](<kkshukle.cse@iitbhu.ac.in>))

# Schedule Conflicts

### Please list any schedule conflict that will interfere with you treating your proposed C3G GSoC project as a full-time job in the summer.  If you are applying for other internships or have other commitments, list them.

Presently I have no commitments for any full-time job in summers.
I have already applied for CERN Openlab internship, but it's a pretty very farfetched dream.

I might go for a vacation for no more than seven days, in the middle of summer (as it gets scorching hot in Varanasi).

# Mentors

- Mentor names: David Bujold 
- Mentor emails: [David Bujold](<david.bujold@computationalgenomics.ca>) (david.bujold@computationalgenomics.ca)
- Mentor link_ids: Link ID has been discontinued from GSoC's Site.

### Have you been in touch with the mentors? When and how? 

I exchanged emails with David Bujold discussing the project and the selection tests. 
He has given me a good picture of what is to be expected of me (both the small and big picture).
I hope to learn a lot from him during this summer.

# Synopsis (max 150 words)
 
Would you like me to reduce your mundane tasks (managerial, upload, etc.) such as those of uploading the data to EGA Repository?

If yes, this is the proposal for you.

Let me introduce to you, mEGAdata which is a database-driven lightweight web application for archiving genomics projects metadata on samples and experiments, with the goal of easing submission to the [European Genome-phoneme Archive (EGA)](https://www.ebi.ac.uk/ega/home).

But there is always a problem of initial setup and maintenance(end users favor packages that are functional and easy to install!), this is where my work will come. I will make it simpler to get started. There are several  CI/CD tools online, I have previously worked with Jenkins, will explore more for development.

Hope this gives you an idea, continue reading for more information.

# Technical Synopsis (max 150 words)

mEGAdata is a database-driven lightweight web application for archiving genomics projects metadata on samples and experiments, with the goal of easing submission to the [European Genome-phoneme Archive (EGA)](https://www.ebi.ac.uk/ega/home).

Submission of large datasets to EGA requires upload of metadata via XML to EGA_webin. And original dataset is transferred via SFTP(slow) or Aspera (ascp, fast). mEGAdata was build to submit one sample by one. I plan to automate and speed up this process of submission.

The issue with any Web Application or any application forsakes is related to successful and secure deployment. Usually, it is tough to deploy in production with getting everything(from version to libraries, etc.) as the developer is intended, with the fast pace moving of software community, something which is working today might be deprecated in next version and eventually removed. Though the Developer has good intentions in deprecating some parts of the library, the end user has to suffer till the application developer decides to change the code, or someone else does it. To counter this dependency hell, Docker was introduced. Though I am convinced this will be a right way to go, I want to explore other options such as Vagrant (to ensure that application is deployable on Windows also), for this, I will be doing the survey in Community Bonding time, along with the conventional community bonding.

I will ensure that the code base meets the privacy requirement and ensure proper auditing of actions is possible, by using very basic Write-ahead logging.

__Note__: More Technical Information in subsequent sections.

# Benefits to Community (max 250 words)

In Today's world, a lot of time is spent on nonproductive work such as organizing the data, metadata, etc. in directories and databases. But what is missed is that most of this job do not require any unique skill set, still they are done by highly trained professionals, who instead can be doing something productive with their time and return to society. But still given the privacy concerns, these professionals have to do these tasks. 

What if we create an application and make it easily distributable and maintainable for the user to do some of these tasks. Time saved from these tasks can be better utilized in doing research.

With me spending my summer to work on this problem, some researcher's time will be saved. Further, it will reduce the risk factor involved in the failure of privacy.

I will be making it easier for the user to obtain a copy of the application which will be simple (one or two liner command) to get started and without much setup. (something on lines of: "wget -qO- https://get.megadata.<some-top-level-domain>/ | sh"). This deployment will be automated, using GitHub hooks to CI/CD and then uploading the script to a server.

By Open-Sourcing the work, society will be motivated to reduce the time wasted on such mundane tasks. McGill EMC is using mEGAdata today, but by making it easier for others to access it, can be utilized by numerous other centers doing similar work. And this will also help McGill EMC as I will also be incorporating some new features in mEGAdata such as Assays Metadata Management, Sequencing runs metadata management, etc. 

That's the beauty of open source.



# Coding Plan & Methods

### Describe in detail your plan for completing the work.  What functions will be written, how and when will you do design, how will you verify the results of your coding?  Each project is different; please make your application appropriate to the work you propose.  

#### Must Have:
    
* Normalization of Database Schema.
    * __Logic__: Normalization is the process of decomposing tables such that data redundancy is reduced.
    * __Technical Details__:  
        - Redundancy of data is a known source of inconsistency. We will be mapping all the functional dependencies and then apply transformation to convert to __BCNF__ or, at least, __3NF__ form. 
        - The normalized form might be traded off for performance on final discussion with the mentor.
    * __Expectations__: After this task is completed, we should have reduced chances of data redundancy, which leads to data inconsistency.
    
* Switching to SQLite, removing all MySQL dependencies. 
    * __Logic__: Size of Metadata will be limited, so we don't necessarily need a full-fledged Database since SQLite is embedded into Client program, we will be reducing the complexity of the system. 
    * __Technical Details__: SQLite has bindings to many programming languages (Python also). In this step, I will remove all MySQL binding from the requirement and replace it with SQLite bindings.
    * __Expectations__: After this task is complete, we should have reduced one requirement in installing the portal while still meeting the required functionality.
    
* Studying Various Containerizing Techniques 
    * __Logic__: End users favor packages that are functional and easy to install!
    * __Technical Details__: 
        - We will study Vagrant, LxC and Docker for portability. This Study will be decided by various factors such as future support, supervisory daemon or separate dockers. 
        - I have already done a preliminary survey; docker appears to be a very nice option as it supports versioning (but that is limited to 1023, due to AUFS). 
        - Docker still has pretty much-limited support to run on Windows, while vagrant is capable of running on Windows. 
        - VM might be larger in size, with high startup time, but are still a preferred way to transport application in Corporate (experience with Goldman Sachs)
    * __Expectations__: By the End of this task, we should have finalized the technique we will go ahead.
    
* Porting the Code to Python3.x (Most probably Python3.5)
    * __Logic__: Python2.7 has already entered maintenance stage and support will be discontinued after 2020.
    * __Technical Details__: Will use the 2to3 application to port the code to Python3.5.
    * __Expectations__: By the End of this task, we should have equally functional application as before, with added benefit of future support.
    
* Web Page for Assays Metadata Management 
    * __Logic__: User should be able to do create/update/delete of Assays Metadata.
    * __Technical Details__: 
        - This is expected to be done by building a REST Endpoint (HTTP verbs to be supported: GET/POST/DELETE/PUT). AngularJS Page or similar technology will be used which will act as our view.
        - Controller will be responsible for validating the consistency of Database at each updating (such as preventing user to delete a metadata set if it is used by at least one dataset).
    * __Expectations__: By the end of this task, we should have fully functional Web Page for Assays Metadata Management, supporting create, update & delete for Assays Metadata.
    
* Web Page for Sequencing runs metadata management
    * __Logic__: User should be able to do manage Sequencing runs metadata, supporting multiple sequencing raw files, with pertaining metadata.
    * __Technical Details__: 
        - This is expected to be done by building a REST Endpoint (HTTP verbs to be supported: GET/POST/DELETE/PUT). AngularJS Page or similar technology will be used which will act as our view.
        - Controller will be responsible for validating the consistency of Database at each updating (such as preventing user to delete a metadata set if at least one dataset uses it).
        - Raw data is expected to be in FASTQ format. Since FastQ format makes no assumptions about the structure of the experiments (thus may or may not contain any metadata). I will be taking the metadata from the user and use md5 to map to the file (along with its name), along with host details.
    * __Expectations__: By the end of this task, we should have fully functional Web Page for Sequencing runs metadata management, supporting options to manage Sequencing runs metadata over multiple sequencing raw files.

* Incorporate sample properties editor in the web application
    * __Logic__: User should be able to edit the properties of metadata on the application, instead of downloading, removing old entry and uploading new one.
    * __Technical Details__: 
        - This is expected to be done by building a REST Endpoint (HTTP verbs to be supported: GET/POST/DELETE/PUT). AngularJS Page or similar technology will be used which will act as our view.
        - Controller will be responsible for validating the consistency of update.
    * __Expectations__: By the end of this task, we should be able to edit the metadata from the application itself.

* Studying various OAuth based authentication systems.
    * __Logic__: IPA(Identity, Policy, and Audit) are some of the important characteristics an application should support. But in this we will study various ways to support Identity and Policy; Auditing will be a Nice to Have feature (will try to support in case time remains).
    * __Technical Details__: Read about OAuth vs.  OpenID Connect, Google OAuth vs. Mozilla Persona or Github Authenticator or any other service. I am familiarized with Google OAuth2, but will try to find concrete proof to go ahead with that. Moreover, it depends on the usage of the users.
    * __Expectations__: By the end of this task, we should have a clear idea of which protocol to implement.

* Integration of Authentication Mechanism:
    * __Logic__: users need to be authenticated to use the facility.
    * __Technical Details__:
        - Will use Flask-OpenID or Flask-OAuth or any such as determined from the previous activity.
        - Will be supported using decorators such '@google.authorized_handler' or any such.
    * __Expectations__: By the end, the user should be able to authenticate them before using the facility.
    
* Containerization of the Application
    * __Logic__: End users favor packages that are functional and easy to install!
    * __Technical Details__: Based on the Previous study, will use one of the Containerizing techniques.
    * __Expectations__: If the decision is Docker, a docker file can be expected to be output. If it LxC, a script to generate the container can be expected.

* Translate XML generation for EGA submission from Perl to Python
    * __Logic__: It would be easier for developer to call a python script from the application instead of Perl
    * __Technical Details__: 
        - To call a Perl script, the user will be required to open a subprocess, which would open up a whole lot of security vulnerabilities. So instead, we will call the python function directly.
        - I have previously used lxml to parse, so it might be a good idea to use etree from lxml to generate the xml.
    * __Expectations__: By end, we should have a python script which would be functionally similar to the Perl script

* Search facility through donors, samples, datasets, and their metadata
    * __Logic__: It’s easier for the user to search instead of going through the list of datasets.
    * __Technical Details__: 
        - Will add tagging to each of the entry(assays, sequencing runs, etc.), along with indexing of metadata into an SQLite Table for easier searching. 
        - This will include the creation of REST API End Point, and Angular JS page to consume the data from this End Point.
    * __Expectations__: By the end, the user should be able to put his/her query in a search box, which should take it to another page where all the data items will be listed, with the link to the particular data item.
    * __Challenge__: It will be a challenge to maintain the hierarchy of access. i.e. either limiting the users to their group's experiment or their experiments only. Initially, I will limit to user's experiment only.

* Script to migrate old MySQL data to new SQLite database, based on the new schema.
    * __Logic__: It would be easier for guys at McGill to move their old database easily to the new application.
    * __Technical Details__: A python script which will be parse through the database and import the data to sqlite database
    * __Expectations__:  A single script to export the data to SQLite.


#### Nice to Have:
* Module to generate BASH script with ascp, to make it easier for the user to upload the raw data and its md5 to EGA.
    * __Logic__: It should be easier for the user to make a single call to a script and upload the raw data and its md5, and retry in case of failure.
    * __Technical Details__: BASH script will be created which will take the input as metadata and file name, will generate the md5 to confirm its integrity and try to upload using "ascp" to EGA.
    * __Expectations__: A single script to upload a file to repository
* Support for both python2.7 and python3.x (low priority)
    * __Logic__: Support for both would enable the developer to import the module in the majority of python script he wants. 
    * __Technical Details__: will try to use __future__ and other such modules to maintain the backward compatibility
    * __Expectations__: Module will be importable in both the major versions of Python.

* BioPortal ontology integration
    * This will involve creating a Handsontable editor, based on given ontology. I haven’t used it, but should not pose many challenges, will integrate it if time is left.
     
* Bioinformatics downstream analysis metadata
     * __Logic__: User should be able to store analysis parameters in the application itself.
    * __Technical Details__: 
    - This is expected to be done by building a REST Endpoint (HTTP verbs to be supported: GET/DELETE/PUT). AngularJS Page or similar technology will be used which will act as our view.
    * __Expectations__: By the end of this task, we should have fully functional Web Page for storing Metadata/parameters in the application.

* In Web Page for Sequencing run metadata management, raw data server location, and md5 checksums integration service.
    * __Logic__: Maintaining raw data server can be helpful for the user to locate the data.
    * __Technical Details__: Maybe use SSH (authentication using SSH keys) to list the files in the directory, and using md5 to match to the data. Maybe add a rest call to the bash script, which will let the primary system know where the data is located.
    * __Expectations__: Easier to point out the raw data. 



### Describe perceived obstacles and challenges, and how you plan to overcome them.

Flask-Stormpath, which is a requirement for the project, is still on python2.7 (they are waiting for Facebook-Python-sdk to be upgraded to python3, but they will be cutting a new release in a week or so, which will build without Facebook integration [Issue #26](https://github.com/stormpath/stormpath-flask/issues/26). Possibly shift to some other OAuth based authentication system.

In searching, it will be a challenge to maintain the hierarchy of access. I.e. either limiting the users to their group’s information or their experiments only. Initially, I will limit to user's data only.

In authentication. It will be a challenge to create and maintain groups, given that Google or any-other API will only return UUID, maybe add an administrator to coordinate users with the group. But this will be Nice to have feature.

# Timeline


### Provide a detailed timeline of how you plan to spend your summer, organized by deliverables.  Don't leave testing and documentation for last, as that's almost a guarantee of a failed project. 

From __April'16 to 22 May'16__, the survey of OAuth-based authentication systems, possible sample properties editor, VM (Vagrant or similar) vs. Linux Containers (LxC) vs. Docker for portability study, and designing the Entity-Relationship Diagram for the final application.

__Note__: April'16 to 22nd May is Community Bonding time since I have reviewed good part of the code, I decided to do the survey instead. Though am already familiarized with few technologies (have used them for multiple projects) such as Docker and OAuth compared to others, but wanted to evaluate all for their simplicity and features. And can easily move forward with them without many hiccups. 

I plan to start coding early as I will be free after 5th May. But following are the firm deadlines which I will be trying to meet. Function Documentation and doctests are expected to go side by side. 

From __22 May'16 to 5 June'16__, SQlite migration should be completed.

From __6 June'16 to 12 June'16__, Major python3.5 porting should be completed.

From __12 June'16 to 28th June'16__, Web Page for Assays Metadata Management

By __28 June'16__, I should have completed 50% of the activities. Documentation and unit testing of all modules, which have been completed, should be ready.

From __29 June'16 to 5th July'16__, Web Page for Sequencing runs metadata management.

From __5 July'16 to 24 July'16__, OAuth-based authentication systems, BASH script with ascp, global searching

From __24 July to 10 August'16__, Incorporate sample properties editor, finally containerization of the application

From __10 August to 24 August'16__, final documentation, functional testing, blog entry, video (no promises), clean up and final push.

__Note__: 16th is the suggested pens down date.

### Final Deliverable:

In one line, an easier way for users to deploy their version of mEGAdata for upload to EGA Repository. The web application will be packed in the form of a container (full VM or Docker app) making it easier to deploy and maintain.

All the __Expectations__ in Must-Have features will be met. A separate API and a web application will be the result of this activity, which will allow the user to create new applications to meet their future needs. 

For end-users: a simple script to download and create the application locally for easier uploads to EGA.

Note: More defined deliverables have already been listed in Coding Plans & Methods.

### What is your contingency plan for things not going to schedule? 

First, I will try to meet each deadline, and a separate Doc will be maintained with the achievements and failures. Second, possibly a weekly sync up with the mentor, to provide efficient support. If required, deliverables to be redefined to avoid roadblocks and ensure that major work is completed within the time-frame. Last 15 days are kept for contingency and if everything is on time, which will be used to support Nice to have features.

# Management of Coding Project

### How do you propose to ensure code is submitted/tested?

Weekly Code Reviews.
Since the project is defined with concrete tasks, with __expectations__ listed from each tasks. The mentor will confirm that the expectations from each activity are met. And that will be maintained in a Google Sheet along with commit id.

After approval of Mentor, the code will be finally pushed to the main branch, as features are implemented.

I will also publish a blog with the demo of the minimal number of steps to get the application running. (Will try to release a video also, but no promises for that)
#### Testing Methodology
"Something that is untested is broken."

I will incorporate Unit tests for all Python function using doctest (logic being, the developer should be able to see the test in the doc section of a function).

For the API endpoint, I plan on using Flask-Testing.

Angular JS recommends Karma and Jasmine for unit testing, and I plan on using that.


### How often do you plan to commit?  What changes in commit behavior would indicate a problem?

At the bare minimum, I plan to push to my branch once every 3-4 days.  
If I haven't pushed in a week, and my mentor is not aware of any emergency or personal commitments, then that would indicate a problem. This should never happen.


### Describe the qualification test that you have submitted to you project mentors.  If feasible, include code, details, output, and example of similar coding problems that you have solved.

Basic Implementation:
    
* BitBucket Repo: [https://bitbucket.org/sainyamkapoor/simple_api](https://bitbucket.org/sainyamkapoor/simple_api)
* Angular JS Application: [http://api.simpleapi.ml:8080/static/index.html](http://api.simpleapi.ml:8080/static/index.html)
* Api End point: [http://api.simpleapi.ml:8080/api/v1.0/phone](http://api.simpleapi.ml:8080/api/v1.0/phone)

Alternative Implementation with swagger (Recommended):
    
* BitBucket Repo: [https://bitbucket.org/sainyamkapoor/simple_api_swag](https://bitbucket.org/sainyamkapoor/simple_api_swag)
* Angular JS Application: [http://api.simpleapi.ml/static/index.html](http://api.simpleapi.ml/static/index.html)
* Api End point: [http://api.simpleapi.ml/api/v1.0/phone](http://api.simpleapi.ml/api/v1.0/phone)
* Swagger UI: [http://api.simpleapi.ml/api/spec.html](http://api.simpleapi.ml/api/spec.html)
    
    
        PUT, POST, GET requests are documented in the bitbucket repo.


# Credits:

I would like to thank David Bujold, for patiently answering my queries about the project and reviewing my selection test. He was able to point me in the right direction and helped me by providing ideas and action plan. Thanks for bearing with my childish queries at times.


-----------------------------
-----------------------------
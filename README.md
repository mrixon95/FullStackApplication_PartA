# YourHealth: Better you, everyday!



### Purpose:

This project is designed to track the physical, mental and financial health of an individual. The analytics relating to the user's physical, mental and financial health should all be tracked and this information is to be displayed back to the user in an understandable way. Therefore, the purpose of YourHealth, is to assist the user in monitoring their overall health conditions and get a complete picture of all the significant factors that affect their health and wellbeing. Amongst other health and wellbeing metrics, it will be able to track the user's weight, diet, exercise routine, blood pressure, financial security and mental wellbeing. The intent of building YourHealth is to give the user a very clear picture of every factor that influences their health and wellbeing. Additionally, the app should clearly display how each factor has changed overtime so that user's can see which aspects of their health and wellbeing have been improving and deteriorating. 

For example, a user may well have changed diet, increased their amount of exercise and have lost 10 kg over the past 3 months. They report that feel a lot more energetic and have boosted their self-esteem. They report all of these good changes in their life into the YourHealth app. However, other factors in their life could have deteriorated. The cost of a gym membership and a dietician has caused significant financial distress on them and their performance at work is not as good because they have cut down work hours in order to go to the gym. 

The YourHealth app should account for all factors involved and deliver a clear picture to the user about their overall health and wellbeing profile. 

### Functionality:

**Allow users to enter in their health related data** - The YourHealth app features will allow users to enter in their general profile information along with health and wellbeing data. The general profile information will be obtained from the user when they sign up. They will enter in their name, age, email, date of birth and other profile information. Likewise, the health and wellbeing data will be obtained from the user on a frequent basis. This information includes their weight, diet, financial income and expenses, medication, exercise routine and other relevant data.

**Display graphs and information** - The YourHealth app will have a feature which displays all the relevant information that the user entered in a very understandable format. This feature will have line charts, bar charts, histograms, spider charts and many other powerful visuals that illustrate trends in the user's health and wellbeing over a period of time. Also correlations between metrics can be evaluated to show whether one metric has an affect on another eg. perhaps one user has a strong negative correlation between financial stress and time asleep. When the user is under financial stress, they tend to sleep less. Insights such as this would be of interest to the user and should be displayed to them.

**Highlight areas of significant improvement and deterioration** - There will be an insights page where the areas of significant improvement and deterioration are displayed. This page should be easy to read and the user should be able to immediately recognise which aspects of their health and wellbeing are getting better and which aspects are getting worse.



### Target Audience:

The YourHealth app is designed for those people who find it difficult to track their health and wellbeing, or would like to see some insights into their health and wellbeing statistics. By inputting in all of their relevant health and wellbeing data, those users get clear insights into which aspects of their life are improving and alternatively, which aspects are deteriorating. Also correlations between factors can be viewed by the user so that they can see what may be causing the change in their health and wellbeing.



### Tech Stack:

I plan to build this application using a Python Flask App. This flask app will be made up of controllers which contains endpoints. These endpoints will be assessible through making HTTP requests to the flask server. The app will use **HTML**, **CSS** and **jinja2** on the **front-end**. This tech will be user-facing and display the graphical user interface to the end user. The jinja2 will enable the data retrieved from the PostgreSQL database, to be displayed to the user. On the **back-end**, a **PostgreSQL** **database** will be used to store all the user data in relational database tables. 

AWS will be used to spin up two **EC2 instances**. One EC2 instance will host the Flask application and accept traffic from any IP address on the internet. The other EC2 instance will host the PostgreSQL database where the user data is stored. For security reasons, only traffic from the EC2 instance with the Flask app will be accepted. This is to say that the database will not be able to receive queries from the wider internet. It will only be manipulated by the Flask app.

An **application load balancer** will be configured so that incoming traffic from users will be distributed across multiple EC2 instances. This ensures that there is never an overwhelming amount of requests made to a single EC2 instance. Instead, new EC2 instances can be spun up whenever the workload increases so that the response time of each request does not significantly deteriorate.

Finally, a **docker image and container** will be used to store all the instructions in setting up the Flask app and PostgreSQL database on separate EC2 instances. It should be very quick to start up the docker container and run the application.



### Data Flow Diagram:



I plan to build this application using a Python Flask App. This flask app will be made up of controllers which contains endpoints. These endpoints wil



YourHealth app will have a feature which displays all the relevant information that the user entered in a very understandable format. This feature will have line charts, bar charts, histograms, spider charts and many other powerful visuals that illustrate trends in the user's health and wellbeing over a period of time. Also correlations between metrics can be evaluated to show whether one metric has an affect on another eg. perhaps one user has a strong negative correlation between financial stress and time asleep. When the user is under financial stress, they tend to sleep less. Insights such as this would be of interest to the user and should be displayed to them.







**R2:** [Report 1: Privacy and Security Analysis](docs/Report_1_Privacy_and_Security_Report.md)

**R3:** [Report 2 Professional Ethical Legal](docs/Report_2_Professional_Ethical_Legal.md)

My app is designed to be similar to LinkedIn but for IT professionals.
On ConnectIT, IT professionals will be able to:

* register as a user and add photos
* like and comment on user posts
* add work history, study history, certifications and links to their resume/projects
* write down meetings they have
* send messages to other users and like their messages

Docs for my app:
* [Trello board](https://trello.com/b/tTpbSo3U/project-management-tracking-application) for **project management**
* [End points](https://petstore.swagger.io/?url=https://raw.githubusercontent.com/mrixon95/Term3_Assignment_Flask_App/main/docs/connectITAPI_endpoints.yaml) for **interacting with the flask app**
* [Wireframes](docs/Wireframes.md) for **designing the front end** 



**R4, R9:** My data model uses a **PostgreSQL database** and has one-to-one, one-to-many and many-to-many relationships between the tables. The application is able to communicate with the postgresql database in the cloud by using SQLAlchemy. This module uses Object Relational Mapping which abstracts table records into Python classes. The application also makes use of Marshmallow schemas to validate data sent to the database and to deserialise into json format before being sent back to the user in the HTTP response. 



**R7:** An example of an API endpoint aggregating data is below. This endpoint gets the number of likes for a post. This can be done by counting the number of distinct users who like a post.

![get_num_likes_example](docs/get_num_likes_example.PNG)





## R6: User-interface using Jinja

### URL: http://127.0.0.1:5000/web/login

### Login Page

![jinja_log_in_page](docs/jinja_log_in_page.PNG)

### List of work experiences



![jinja_work_experiences](docs/jinja_work_experiences.PNG)

### R11: Join table example





![join_table_example](docs/join_table_example.PNG)









## Proposed Entity Relationship Diagram

* Each User can have multiple images, certifications, work histories, connections, meetings, messages, study histories, resume/projects, posts, comments and like multiple posts
* Each Like belongs to one post and one user
* Each comment belongs to one post and one user
* Each connection has one user who requests the connection and one user who can decide to confirm it



![Entity_Relationship_Diagram](docs/ERD_diagram.png)


## Installation
In order to install this application:

1. Install python 3.8, python3.8-venv and python3-pip on your system.
   On Ubuntu run ```sudo apt install python3.8 python3.8-venv```
   Verify that it install successfully by running ```python3.8 --version```

2. Install pip3 the python3 package manager.
   On Ubuntu run ```sudo apt-get install python3-pip```
   or ```python3 -m pip install pip```

3. Clone the application onto your system by running ```git clone https://github.com/mrixon95/Docs_On_Term3_CCC_course.git```
   and cd into the directory

4. Download a virtual environment and activate it.
   On Ubuntu run ```python3 -m venv venv``` to download the module
   and ```source venv/bin/activate``` to activate the virtual environment.
5. install application dependencies within the activated Python3.8 virtual environment by running ```pip3 install -r requirements.txt```.


## Setup
Create a ```.env``` file using the ```.env.example``` template within the ```src``` folder and populate the required fields within the ```.env``` file.

## Custom Commands
These following flask commands below are for automating tasks related to database tables and for testing during the development phase.
1. ```flask db create```: creates database tables defined in registered models.
2. ```flask db seed```: populates database tables with dummy data using faker module.
3. ```flask db drop```: drops all database tables defined in registered models.



# CI/CD Pipeline



A CI/CD pipeline can be created as part of the continuous integration workflow when pushing modified code to GitHub.

1. The test_suite job will run on one of GitHub's VMs using the latest Ubuntu operating system. The new code pushed to GitHub is checked out into this VM.
2. The VM installs python3.8 and installs the dependencies. These dependencies and their version number are written on separate lines in the requirements.txt file.
3. The automated tests in the tests directory are ran 
4. The .py files are checked against the PEP8 style guide by running flake8



## Migrations

If you make any adjustments to the database tables eg. adding a new column to a table, then migrations are needed for recording those changes. The sqlachemy package```flask-migrate``` is in the requirements.txt file so no need to pip install it again.

To set it up:

1. Run `flask db init` and then drop everything in the database using ``` flask db-custom drop```
2. Create the migration using ```flask db migrate -m "Initial migration"``` and then run the migration using ```flask db upgrade```

You are now ready to make changes to the model that will automatically recorded every single time you migrate.
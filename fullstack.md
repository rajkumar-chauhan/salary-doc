# Fullstack Documentation
![Overall Component Architecture Flow](https://www.revenueriver.co/hubfs/fullstack.jpeg#keepProtocol)
---

| Author | Created/Updated | Version  | Last updated by | Comments |
|--------|------------|----------|-----------------|----------------|
| Siddharth   | 06-06-24   | 0.1| Siddharth          | Intial Doc       |
| Siddharth   |  08-06-24  | 0.2| Siddharth          | Change in Diagrams and flow      |
## Table of Contents
1. [Introduction](#introduction)
2. [Overall Component Architecture Flow](#overall-component-architecture-flow)
   * [Frontend Flow](#frontend-flow)
    * [Database Management](#database-management)
      *  [Employee API](#employee-api)
      * [The Attendance API](#the-attendance-api)
      * [The Salary API](#the-salary-api)


3. [User Flow](#user-flow)
5. [Conclusion](#conclusion)

---


## Introduction

Full Stack Development is the process of creating a complete web application that includes front-end, back-end, and database management. 
The front end deals with the user interface and user experience (UI/UX) of the web application. I
It is responsible for the visual representation of the application and how it interacts with users. 
Back-end development is responsible for server-side programming, which includes business logic, data access, and security. Finally, database management is responsible for storing, accessing, and managing data for the application.

## Overall Component Architecture Flow

### Frontend Flow

Front-end development deals with the user interface and user experience (UI/UX) of the web application. 
It is responsible for creating a visual representation of the application and how it interacts with users.
Front-end developers use programming languages like HTML, CSS, and JavaScript to create the web application's user interface.
Pre-Requisites
The frontend application have dependencies on other REST API of OT-Microservices.

![Atl text](https://github.com/OT-MICROSERVICES/frontend/raw/main/static/frontend.png)
To run the application successfully, we need these things configured
For Refrence Links Below
* [Documentation](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Frontend/Detailed-Documentation) 
* [POC](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Frontend/POC) 
* [Employee API](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Employee-API)
* [Attendance API](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Attendance)
* [Salary API](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Salary-API)

### Backend Management 



#### 1 .Employee-API

The application doesn't have any specific pre-requisites except the database connectivity. Additionally, we can add Redis as cache management system  the setup.
![Alt text](https://github.com/OT-MICROSERVICES/employee-api/raw/main/static/employee.png)
Create this same as above.
Pre-Requisites
For running the application, we need following things configured:
For Refrence Links Below
* [Documentation](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Employee-API/Detailed-Documentation) 
* [POC](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Employee-API/POC) 
* [ScyllaDB](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Employee-API/POC)
* [Redis](https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/linux/)


| **Supported Features**                                   | **Description**                                                           |
|----------------------------------------------------------|---------------------------------------------------------------------------|
| ScyllaDB                                                 | As primary database for storing information                               |
| Redis                                                    | As a cache management system for quick response                           |
| Migrate                                                   | Upgrading to the latest version of the database                           |


#### 2 .The Attendance api
The attendance api application have some database and package manager dependencies. Some of them are mandatory and some can be option, for example - Redis.
To run the application successfully,
we need these things configured

Supported features of the application are:-

PostgresSQL as a primary database for storing all the attendance records
Redis as cache management middleware for storing all API response
![Atl text](https://github.com/OT-MICROSERVICES/attendance-api/raw/main/static/attendance.png)
Below Have Refrence Links for in detail
* [Documentation](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Attendance/Documentation) 
* [POC](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Attendance/POC) 
* [PostgresSQL](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Postgresql/Detailed%20Document) 
* [Redis](https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/linux/)
* [Poetry](https://www.digitalocean.com/community/tutorials/how-to-install-poetry-to-manage-python-dependencies-on-ubuntu-22-04)
* [Liquibase](https://docs.liquibase.com/start/install/liquibase-linux-debian-ubuntu.html)

#### 3. The Salary API
We need an Api microservice which is responsible for storing all the salary related transactions and records of Employee in OT-Microservices stack. This Application is must be independent and can be run on multiple operating system. JAVA RUNTIME would be required to run this application.
![Atl text](https://github.com/OT-MICROSERVICES/salary-api/blob/main/static/salary.png?raw=true)

We only need maven as build tool, but for running the application following things are required
For Refrence Link are below 
* [Documentation](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Salary-API/Detailed-Documentation)
* [POC](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Salary-API/Salary_POC)
* [ScyllaDB](https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/install-on-linux.html)
* [Redis](https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/linux/)
* [Java](https://maven.apache.org/)

### Database Management

Database management is responsible for storing, accessing, and managing data for the application. It deals with the creation, maintenance, and optimization of databases. Database management is done using tools like .
For Refrence Links Below
* [ScyllaDB](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Employee-API/POC)
  
* [PostgresSQL](https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices/Postgresql/Detailed%20Document)
  
* [Redis](https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/linux/)

### User Flow
![Alt text](https://prepbytes-misc-images.s3.ap-south-1.amazonaws.com/assets/1673592711181-What%20is%20Full%20Stack%20Development1.png)
---

| **User Registration Flow* |                                                                                         |  
|---------------|-----------------------------------------------------------------------------------------|
| User submits the registration form. |                                                      |
| Frontend validates the input. |                                                          |
| The request is sent to the backend. |                                                      |
| The backend processes the registration and stores the data in the database. |                            |
| A response is sent back to the frontend. |                                                      |
---

| **User Login Flow** |      |                                                   
|---------------------|----------|                                          
| User submits the login form. |  |                                           
| Frontend validates the input. | |                                           
| The request is sent to the backend. |   |                                   
| The backend authenticates the user. |   |                                   
| A response is sent back to the frontend with a token. |    |          
---

| **Data Processing Flow** |                                                                                        |
|---------------------------|----------------------------------------------------------------------------------------|
| Data is submitted from the frontend. |                                                               |
| The backend processes the data. |                                                                         |
| Data is validated and transformed. |                                                                |
| Processed data is stored in the database. |                                                           |
| Confirmation is sent back to the frontend. |                                                       |
---
### Conclusion
![Alt text](https://github.com/mygurkulam-p9/documentation/assets/160397748/bf2a9eaf-05c9-47e9-bb35-f533e42d02bc)
In this document We can assume that above flow diagrams are explaining more with the help of there purticular Terms .
This document provided a detailed overview of the fullstack application architecture, including component diagrams and user flow diagrams.
Here we interconnect all three API's with frontend 

## Contact Information

| Name          | Email Address                          | 
| ------------- |:--------------------------------------:|
| Siddharth      | siddharth.pawar.snaatak@mygurukulam.co |

## Refrences 

| Links          | Description                          | 
| ------------- |:--------------------------------------:|
|    https://github.com/OT-MICROSERVICES  | For Information pupose|
|   https://github.com/mygurkulam-p9/documentation/tree/main/OT-Microservices  | For Flows |

# SALARY API  

|CREATED/UPDATED |VERSION|AUTHOR|COMMENT|
|--------|-----------|-------|---------|
|05-06-2024|0.1|Rajkumar|Documentation on Salary API| 


## Table of Content 
- [Purpose](#Purpose)
- [Pre-reqisites](#Pre-requisites)
- [System Requirement](#System-Requirement)
- [Build-Time Dependency](#Build-Time-Dependency)
- [Run-Time Dependency](#Run-Time-Dependency)
- [Architecture ](#Architecture)
- [ Dataflow ](#Dataflow )
- [ Setting Up the Environment](#Setting-Up-the-Environment)
- [Building and Running the Salary API](#Bilding-and-Running-the-SalaryAPI)
- [Conclusion](#Conclusion)
- [ Endpoints ](#Endpoints )
- [ References ](#References ) 
- [Contact Information ](#Contact-Information )
     
## Purpose 
We need an Api microservice which is responsible for storing all the salary related transactions and records of Employee in [OT-Microservices](https://github.com/OT-MICROSERVICES) stack. This Application is must be independent and can be run on multiple operating system. JAVA RUNTIME would be required to run this application.

## Pre-requisites
The Salary API application have some database, cache manager and package dependencies. Ensure you have the following on your system :
* [ScyllaDB](https://www.scylladb.com/)
* [Redis](https://redis.io/)
* [Maven](https://maven.apache.org/)
  
## System Requirements 
|Hardware Specification |Minimum Recommendation|
|:-----------------------:|:----------------------:|
|Processor              | Dual-core            |
|RAM                    | 4GB                  |
|Disk                   | 20GB                 |
|OS                     |Ubuntu(22.04)         |

## Build-Time Dependency
| Name | Version | Description |
|:-----:|:------:|:------------:|
|Maven|3.+|It helps manage project dependencies, build processes, and project documentation.|

## Run-Time Dependency
|Name  | Version | Description |
|:------:|:-------:|:----------:|
|JAVA|  17| It is necessary to run the compiled Java application.|


## Architecture 

![Salary API](https://github.com/OT-MICROSERVICES/salary-api/blob/main/static/salary.png)

## Dataflow 

* The process begins when a client  sends a request to the Salary API. These requests can be for various operations like creating a new salary record, retrieving salary data, updating existing records, or deleting them.

* The application initially checks Redis to determine if the requested data is cached.

  If the data is present in Redis, it is retrieved and returned immediately, eliminating the need for a database query.
  
  If the data is absent in Redis, the application then queries the ScyllaDB database to fetch the data.
 
* Then the  response  sends back to the client. This response could be the requested data, a confirmation of a successful operation, or an error message if something went wrong.

## Setting Up the Environment
**ScyllaDB**
Install ScyllaDB
To install ScyllaDB, execute the following commands:
```
curl -sSf get.scylladb.com/server | sudo bash
sudo scylla_io_setup
```
**Redis**
Install Redis
To install Redis, use the following commands:
```
 sudo apt install redis-server
 sudo systemctl start redis-server
 sudo systemctl status redis-server
 redis-cli
 ping
```
### Required Libraries
**Install JDK 17**
To install JDK 17, run:
```
sudo apt install openjdk-17-jdk
```
**Install Maven**
To install Maven, execute:
```
sudo apt install maven
```
**Install Migrate**
To install Migrate, use the following commands:
```
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz -o migrate.tar.gz
tar -xvzf migrate.tar.gz
sudo mv migrate /usr/local/bin/
sudo chmod +x /usr/local/bin/migrate
```
## Building and Running the Salary API
### Build the project:
To build the project and skip test cases, execute:
```
mvn clean package -Dmaven.test.skip=true
```
### Testing
**Checkstyle**
To run Checkstyle, use:
```
mvn checkstyle:checkstyle
```
**Run Tests**
To run the test cases, execute:
```
mvn test
```
### Running the Java Application
To run the Java application, navigate to the project directory and use the following command:
```
java -jar target/salary-api.jar
```
## High Availability
To make the salary-api service highly available, you can implement the following strategies:

**Load Balancing**: Deploy multiple instances of the microservice and use a load balancer to distribute incoming traffic evenly.

**Auto-Scaling**: Set up auto-scaling policies to automatically adjust the number of service instances based on traffic and load using tools like AWS Auto Scaling.


 By integrating these practices, you can enhance the availability and reliability of your salary-api service.

## Conclusion
Following these steps, you will set up the necessary environment for the Salary API, build the project, and run the application. Ensure that all commands are executed in the correct order and in a terminal with sufficient privileges.
Other Endpoint are below 

## Endpoints 
|Endpoint|Method|Description|
|--------|-------|----------|
|/api/v1/salary/create/record|POST |Data creation endpoint which accepts certain JSON body to add salary inf|
|/api/v1/salary/search|GET|Endpoint for searching data information using the params in the URL|    
|/api/v1/salary/search/all|GET|Endpoint for searching all information across the system|
|/actuator/prometheus|GET|Application healthcheck and performance metrics are available on this endpoint|
|/actuator/health|GET|Endpoint for providing shallow healthcheck information about application|


## References 
|links | Description |
|-------|------------|
|https://redis.io/docs/latest/operate/oss_and_stack/install/install-redis/install-redis-on-linux/|For Redis |
|https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/install-on-linux.html| For Scylladb|
|https://github.com/OT-MICROSERVICES/salary-api|For understanding the workflow of salary api|



## Contact Information 
|Name|Email Address|
|:---:|:---:|
|Rajkumar|rajkumar.chauhan.snaatak@mygurukulam.co|

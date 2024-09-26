# Java Unit Testing POC

**Created/Updated** | **Version** | **Author** | **Comment**
--- | --- | --- | ---
21-06-2024 | 1.0 | Rahul Sharma | Initial POC
24-06-2024 | 2.0 | Rahul Sharma | Updated POC

## Table of Contents

- [Purpose](#purpose)
- [Prerequisites](#prerequisites)
- [POC Steps](#poc-steps)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

## Purpose 

This document presents a Proof of Concept (POC) for Java Unit Testing. It aims to demonstrate the setup and execution of unit tests using popular Java testing frameworks. The goal is to ensure that the components of the Java application work as expected.

## Prerequisites

| **Requirement**                | **Description**                                |
|--------------------------------|------------------------------------------------|
| JDK 17                | Java                         |
| Build Tool                     | Maven                               |
| Java Project Repository        | [quality-gate](https://github.com/zoro2024/quality-gate) |

## POC Steps

### 1. Setting Up the Project

1.Step-1:-**Install Java**
```
apt-get update
apt-get upgrade
apt install openjdk-17-jdk
apt install maven
```

![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/4454647b-5633-470c-a3ba-225e74d385b1)

![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/9187ff84-d200-4f84-aa92-c467b2c469eb)

![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/5ba29cb0-37da-4061-a149-3d155406ce88)

![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/3070105f-c80a-4597-a883-9e416458b7d3)


2.  **Clone the Repository**
    - Clone the repository from GitHub: `git clone https://github.com/zoro2024/quality-gate.git`
    - Navigate to the project directory: `cd quality-gate`

![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/81823e59-9584-45d2-af68-d0c6fd73483f)

2.  **Using Maven**
    - Execute `mvn test` from the command line.
![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/8684acbf-2c88-4230-8454-233e27c962ec)
![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/b283e021-e361-4d6b-af5e-fd67eff23362)

3.  **Generate the report**
  - Execute `mvn surefire-report:report` from the command line.
    ![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/374404c2-d86e-427e-aa69-1f51691cada7)
    ![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/64ce749e-bfd9-4cb3-827b-9790f5d986e2)

    
4.  **Views the report in a browser**
 - Execute `xdg-open target/site/surefire-report.html` from the command line.
   ![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/933d03e9-7bf7-4f8c-b85f-2c03f84b9b1b)
   ![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/6edddb7b-f282-4261-8787-b9f718561a25)
   ![image](https://github.com/mygurkulam-p9/documentation/assets/142473694/2c105be9-d6a1-4888-b322-8c1dbf8eceab)

    
## Conclusion

This proof-of-concept showcases the fundamental setup and execution of unit tests in a Java project using Maven, JUnit. Effective unit testing plays a crucial role in enhancing code reliability and maintainability by validating individual components of the application.

## Contact Information
**Name** | **Email Address**
---|---
Rahul Sharma | rahul.kumar@opstree.com

## References


| Reference                                     | Link                                                  |
|-----------------------------------------------|-------------------------------------------------------|
| JUnit 5 User Guide                            | [JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/) |
| Mockito Documentation                         | [Mockito Documentation](https://site.mockito.org/)    |
| quality-gate Repository                       | [GitHub - quality-gate Repository](https://github.com/zoro2024/quality-gate) |

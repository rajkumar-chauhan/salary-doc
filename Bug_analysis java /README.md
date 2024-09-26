
# POC for Java Based Application

![image](https://github.com/mygurkulam-p9/documentation/blob/main/Application_CI_Design/Java%20CI%20checks/Bug%20Analysis/Screenshots/spotbugs.png?raw=true)

| Created/Updated | Version  |  Author        | Comment                |
|-----------------|----------|----------------|------------------------|
| 20-06-2024      |      0.1| Rajneesh Yadav | Initial commit          |


## Introduction 

The Proof of Concept (POC) focuses on demonstrating the bug analysis process for a Java-based application. The project under consideration is the "salary-api" from the [OT-MICROSERVICES repository](https://github.com/OT-MICROSERVICES/salary-api.git).

 
## Prerequisites

**Java Version 17** (mentioned in pom.xml)  

**Maven** - A build automation tool used primarily for Java projects. It helps manage project dependencies, the build lifecycle, and project documentation.

**Spotbug** - A static analysis tool that finds bugs in Java programs by analyzing bytecode.

## Steps

### Install Java 17 and Maven

As the salary code is Java-based, it is designed to be compatible with Java version 17. It is advisable to install Maven, a crucial tool for managing and building Java projects.

```
	sudo apt update
	sudo apt install openjdk-17-jdk
        sudo apt install maven
```

### Cloning a Java App

![img](https://github.com/mygurkulam-p9/documentation/blob/main/Application_CI_Design/Java%20CI%20checks/Bug%20Analysis/Screenshots/Screenshot%202024-06-20%20at%2011.23.16%20PM.png?raw=true)


### Add the Spotbug dependency in pom.xml file.
To integrate SpotBugs into your Maven project via pom.xml, use this configuration to ensure the SpotBugs Maven plugin (spotbugs-maven-plugin) version 4.8.2.0 is set up along with SpotBugs 4.8.3 for static analysis and bug detection during your build process.


        <plugin>
          <groupId>com.github.spotbugs</groupId>
          <artifactId>spotbugs-maven-plugin</artifactId>
          <version>4.8.2.0</version>
          <dependencies>
            <dependency>
              <groupId>com.github.spotbugs</groupId>
              <artifactId>spotbugs</artifactId>
              <version>4.8.3</version>
            </dependency>
          </dependencies>
        </plugin>


### Integrate Find Security Bugs into spotbugs-maven-plugin
This configuration enables SpotBugs to use Find Security Bugs for additional security analysis based on your specified include and exclude filter files (spotbugs-security-include.xml and spotbugs-security-exclude.xml).


To integrate Find Security Bugs into SpotBugs plugin, you can configure your pom.xml like below:


              <plugin>
                  <groupId>com.github.spotbugs</groupId>
                  <artifactId>spotbugs-maven-plugin</artifactId>
                  <version>4.8.2.0</version>
                  <configuration>
                      <includeFilterFile>spotbugs-security-include.xml</includeFilterFile>
                      <excludeFilterFile>spotbugs-security-exclude.xml</excludeFilterFile>
                      <plugins>
                          <plugin>
                              <groupId>com.h3xstream.findsecbugs</groupId>
                              <artifactId>findsecbugs-plugin</artifactId>
                              <version>1.12.0</version>
                          </plugin>
                      </plugins>
                  </configuration>
              </plugin>


### 	Analyze Code with SpotBugs:

```
 mvn spotbugs:check
```
![img](Screenshots/02.png)


### Generate SpotBugs Reports: 
This command will generate an html report. After running this command, generate various types of reports, such as HTML and XML: (target/spotbugs.html)(target/spotbugsXml.xml).

```
	mvn spotbugs:spotbugs
```
![img](Screenshots/03.png)
![img](Screenshots/04.png)
![img](Screenshots/05.png)
![img](Screenshots/06.png)
![img](Screenshots/07.png)

# Conclusion

In conclusion, the Proof of Concept showcased effective bug analysis practices for the Java-based "salary-api" application. By leveraging Java 17, Maven, and SpotBugs with Find Security Bugs integration, the POC demonstrated a systematic approach to identify and address potential issues in the codebase. Adopting these practices empowers development teams to proactively address potential issues, ensuring the delivery of high-quality and secure software.

## Contact Information

|    Name                                   | Email Address                    |
|-------------------------------------------|----------------------------------|
| **[Rajneesh Yadav](https://github.com/RajneeshOps)** | rajneesh.yadav.snaatak@mygurukulam.co |

***

# Resources and References

| Description                                      | References  
| ------------------------------------------------- | ------------------------------------------------------------------- |
| SpotBugs Maven Plugin – Usage                           | [Link](https://spotbugs.github.io/spotbugs-maven-plugin/usage.html#:~:text=To%20generate%20the%20SpotBugs%20report,xml%20.&text=Then%2C%20execute%20the%20site%20plugin%20to%20generate%20the%20report.) |
| Usage Guide                           | [Link](https://github.com/find-sec-bugs/find-sec-bugs/wiki/Maven-configuration) |

Prerequisites:

Jenkins server installed and running.
Maven installed on the Jenkins server.
SonarQube server configured and accessible.
Docker installed on the Jenkins server for ECS deployment.
Jenkins plugins installed: SonarQube Scanner, Docker Pipeline, Amazon ECS Plugin, AWS Credentials Plugin, Pipeline Maven Integration.
Setup:

Clone this repository to your Jenkins server or the machine running Jenkins.
Make sure all prerequisites are met.
Jenkins Configuration:

Configure Jenkins Global Tools:

Set up JDK and Maven installations under "Manage Jenkins" > "Global Tool Configuration."
Configure SonarQube Scanner under the same section and specify the SonarQube server details.
Create AWS Credentials:

Go to "Manage Jenkins" > "Manage Credentials" > "Global credentials (unrestricted)."
Add your AWS credentials (Access Key ID and Secret Access Key) for ECS deployment.
Jenkins Pipeline:
The Jenkins pipeline is defined in the Jenkinsfile at the root of this repository. It consists of the following stages:

Build: Maven is used to clean and package the application code.

SonarQube Analysis: The code is analyzed using SonarQube to check for code quality issues, bugs, and vulnerabilities.

Build and Push Docker Image: Docker builds a container image and pushes it to your specified Docker registry.

Deploy to ECS: The Docker image is deployed to Amazon ECS using the specified ECS task definition.


# VERSIONS
##
- JDK 1.8 or later
- Maven 3 or later
- MySQL 5.6 or later

# Technologies 
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- MySQL
# Database
Here,we used Mysql DB 
MSQL DB Installation Steps for Linux ubuntu 14.04:
- $ sudo apt-get update
- $ sudo apt-get install mysql-server

Then look for the file :
- /src/main/resources/accountsdb
- accountsdb.sql file is a mysql dump file.we have to import this dump to mysql db server
- > mysql -u <user_name> -p accounts < accountsdb.sql



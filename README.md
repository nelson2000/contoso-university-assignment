# Contoso University Website Modification

## Initial setup

Backend - [.NET Core API]
Front-end - [ASP.NET MVC and Razor]
Database - [Entity Framework] Local/generic 
Testing - Moq and xUnit
Messaging Service - Twillio
Email Service - SendGrid
API access - Json Web Token JWT

## Modification

Front-end - React Framework as UI
Backend - .NET Core API
Database - MS SQL Server (external)

set up API connections between React and ASP.NET as expected

run the database container and setup database, username and password and create a schema.

set up database context connection string, dependency injection for the database in the app-setting.json or process.cs file.




### Database
- Set up a stand-alone storage optimized instance as a DB server in cloud or on-prem. However for the purpose of testing and development, we can use the official MS SQL Server docker image on github

### Create dockerfiles

- we then create dockerfiles for REACT Framework from a node base 		image, set an appropriate publishing port.

- create a multi-stage dockerfile for the ASP.NET Core API.

- for testing purpose, we can create a docker-compose file to spin up the  react dockerfile (build and run), .net api (build and run) and the sql server (run).

### Docker-compose set up
![image](https://user-images.githubusercontent.com/20236706/206538634-e1edccc3-697b-4959-b22f-468d7f074aae.png)
### CI/CD Workflow for the website
Now that we have tested using docker-compose and we are comfortable with the result.

We can use Jenkins for our CI/CD pipeline, Jenkins will build all the dockerfiles into images  and incorprate the Moq, xUnit testing with pluggins in Jenkins, it will send build images to Kubernetes Cluster for deployment  as pods artifacts to Sonarqube  or another server for code quality check and to Nexus for artifact storage.

CI/CD Pipeline flow

![image](https://user-images.githubusercontent.com/20236706/206540511-d3d35b28-00e5-4b7f-b717-c690b00e291c.png)

There is much more to do, but considering the limited time, this is all i can come up with.

Thank you

Prepared and designed by


Nelson Nwajie
Devops engineer
8th December 2022

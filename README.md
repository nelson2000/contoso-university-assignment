# Contoso University Website Modification

## Initial setup

- Backend - .NET Core API
- Front-end - ASP.NET MVC and Razor
- Database - Entity Framework - Local/generic 
- Testing - Moq and xUnit
- Messaging Service - Twillio
- Email Service - SendGrid
- API access - Json Web Token JWT

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


Now that we have tested using docker-compose and we are comfortable with the result, we can build the images and deploy the containers in kubernetes clusters using Azure DevOps.

### CI/CD using Azure DevOps
We can easily adapt this CI/CD pipeline to Azure DevOps, by pulling dockerfiles for all the stack from github and building and releasing in a AKS, Azure managed kubernetes Cluster. 

![image](https://user-images.githubusercontent.com/20236706/206547389-77a364df-6784-4321-8ac6-e08449e3450e.png)


### CI/CD Pipeline flow using Jenkins

We can also use Jenkins for our CI/CD pipeline, Jenkins will build all the dockerfiles into images  and incorprate the Moq, xUnit testing with pluggins in Jenkins, it will send build images to Kubernetes Cluster for deployment  as pods artifacts to Sonarqube  or another server for code quality check and to Nexus for artifact storage.

![image](https://user-images.githubusercontent.com/20236706/206540511-d3d35b28-00e5-4b7f-b717-c690b00e291c.png)

### Tools

- Docker
- Azure DevOps or Jenkins
- Nexus
- Azure repo
- Sonaqube
- Azure Kubernetes Services (AKS)


Prepared and designed by


- Nelson Nwajie
- Devops engineer
- 8th December 2022

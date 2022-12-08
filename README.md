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

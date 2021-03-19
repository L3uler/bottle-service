# bottle-service


### Overview

A lightweight .NET 5 microservice that I wrote for a Whisky and Wine cellar management app. 
It allows clients to perform CRUD operations on Bottle resources, the central domain entity for the application.

I've uploaded it to my GitHub as a sample of my back-end development, to showcase a backend service that I architected and built using a range of modern technologies.

### Technology

The service is written in C# using .NET 5.
It exposes an ASP.NET Core REST API and uses MongoDB for storage. 
It also uses some popular .NET libraries like FluentValidation and Automapper to do validation, mapping, and a bunch of other stuff.  
The service has been containerised with Docker for ease of development and deployment. 

### Architecture

The service follows the ports and adapters pattern. There is a Core domain project containing the domain models and services. It also contains the contracts that any ports must meet in their interaction with the Core of the microservice. Dependencies point inwards to this Core project. The ports take the form of the REST API and the Mongo ORM, for which there are separate projects. Adapters take the form of mappers (created with Automapper) which adapt between the domain Bottle model and the models used for sending data in and out of the ports.

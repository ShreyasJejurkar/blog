---
id: 629
title: 'Clean Architecture with C# .NET'
date: '2021-04-22T13:41:28+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.com/?p=629'
permalink: /2021/04/22/clean-architecture-with-csharp-net/
timeline_notification:
    - '1619079091'
image: /wp-content/uploads/2021/04/pexels-photo-4974914.jpeg
categories:
    - Programming
tags:
    - .NET
    - architecture
    - csharp
---

Today, in this post I will walk you through the basics and important concepts related to Clean architecture with .NET.

**What is Clean Architecture**

Clean architecture is the next iteration of the very well know architecture patterns that we used to see in the past like Hexagonal, Onion, and Screaming architecture. This architecture is by no means a silver bullet or first-class solution to all architecture problems or complexities that we face today. This architecture just tries to lower the complexity, coupling between layers, and tries to increases cohesion.

The important factor of this architecture is the domain-centric nature. In past, we used to see the database-centric architecture or mostly consider as 3-layer architecture. In those at the very bottom we have the database (SQL or MySQL) then we have database access layer (ORM) then business logic layer (Service layer) and then at the top we have the presentation layer (UI, MVC). This architecture is OK for simple apps and is used widely today as well. But for complex domains and continuously changing requirements in today’s world, this architecture falls apart because of its tight coupling between layers. As in that architecture, each layer knows what its dependent layer is doing. So, if there any change requirement, the cost of change spans across this all layer, and hence it is hard to maintain and keep track of.

So clean architecture tries to solve this problem by keeping the domain in the center. So, although if there any change we can make a change to the domain without affecting another layer much or lowering the cost of change. And also, the important point to note is that all dependencies point inwards in the layer and there will no outward dependencies. And if the inner layer wants to access services from the outer layer, it will depend upon abstractions defined by the inner layer and not on the concrete implementation.

Now we will go to each layer one by one and we will talk about a simple example of a School Management System so that you can understand what will go in each layer and how they contribute to the overall system.

 [![](https://mccshreyas.files.wordpress.com/2021/07/cleanarchitecture-1.png?w=971&resize=700%2C487)](https://mccshreyas.files.wordpress.com/2021/07/cleanarchitecture-1.png)</figure>**Domain Layer**

This is the center of this architecture. This will contain all domain entities, custom exceptions, constant values, and anything related to the core domain. This layer contains enterprise-wide logic, so this might be shared across multiple applications as a Nuget package, so make sure to include the things which are core in the domain. For example, in our School Management System, the `Student`, `Teacher`, `Class` will be the domain entities because without these entities the School Management System won’t even work and won’t even make sense. Similarly, `StudentNotFoundException`, `ClassroomFullException` will be the custom exception that we can have in this layer. Along with this, we can have DomainEvents as well like `StudentRegisteredEvent`, `ClassroomFullEvent`, so that other parts of the application can subscribe to this event and can perform their task based on business logic.

```csharp
    public class Student
    {
         public int Id { get; set; }
         public string Name { get; set; }
         // other domain fields
    }
```

**Application Layer**

This is an important layer in this architecture because this is where you will write your business logic based on various use cases and requirements. As this layer depends on the domain layer, you will have a project reference of the domain project on this project so that this layer will be able to access domain-related things. In contrast to Service-Repository architecture, this is your Service layer. This layer will get input data from the presentation layer and will do processing on it based on business logic and at the end ultimately it will query or save data to the database by using repository abstractions.

Important to note that this layer won’t be having an idea of the type of database which application is using. This layer will just depend upon the abstractions of the repository and not on the concrete implementation. The abstraction and corresponding concrete implementation will be configured together using a dependency injection container. And the concrete implementation will reside in the Persistence project which will talk in detail in a later section. This layer will also have corresponding handlers or subscribers for various domain events, and which will perform the operation as per the requirement.

```csharp
    public class StudentService : IStudentService
    {
         private IStudentRepository _studentRepository;
         public StudentService(IStudentRepository studentRepository)
         {
             _studentRepository = studentRepository;
         }
         public void SaveStudent(SaveStudentRequest request)
         {
               // validate request data based on business logic
               // and create domain student object
               var newStudent = StudentValidator.validate(request);
               _studentRepository.Save(newStudent);
         }
    }
```

**Infrastructure Layer**

This layer contains anything external. This layer will have things that are not directly related to your application domain but are needed as part of specific functionality. Consider in our School Management System, we want to notify each student about the timetable of the exam via their emails. So, to do so we need to use NuGet packages which makes email sending tasks easier, for example, the SendGrid NuGet package. So, the concrete implementation will reside in this project. And if you decide to put interface abstractions, then you can put that in the application layer. So that you can able to call those infrastructure services from business logic using abstractions.

```csharp
    public class SendGridMailService : IMailService
    {
         public void SendMail(MailRequest request)
         {
              // mail sending logic.
         }
    }
```

**Persistence Layer**

This layer is our database access layer. This layer will have a concrete implementation of the repository abstractions which are defined by the application layer. In clean architecture, only this layer has knowledge about the actual underlying database provider. So, in the future, if there any need to change the database provider from let’s say SQL Server to MySQL, only changes will be made in this layer without affecting another layer. Or in other example, you want to use Dapper instead of Entity Framework, then you can swap or change implementation of abstractions without affecting other part of the system. From .NET perspective Entity Framework DbContext, Dapper related things and migrations will reside in this project.

```csharp
    public class StudentRepository : IStudentRepository
    {
         private ApplicationDbContext _context;
         public StudentRepository(ApplicationDbContext context) 
         {
             _context = context;
         }

         public void SaveStudent(Student student)
         {
             _context.Students.Add(student);
             _context.SaveChanges();
         }
    }
```

**Presentation Layer**

Last but not least, the presentation layer is the outermost layer in Clean Architecture. From this layer, user will be able to interact with the whole system. So, we can consider this layer as the user input layer. This might be your API, MVC, or even blazor app. Point to note in the real world, there might be multiple presentation layers in the system which in turn contact the application layer for input and output. The presentation layer won’t be having any business or application logic, this layer will just accept an incoming request (mostly HTTP API request) and forwards it to the application layer for processing and waits for the reply from the application layer, once done it will return the data to the user if any.

```csharp
    [ApiController]
    [Route("/api/[controller]")]
    public class StudentController : ControllerBase
    {
         private IStudentService _service;
         public StudentRepository(IStudentService service) 
         {
             _service = service;
         }

         public IActionResult SaveStudent(NewStudentRequest request)
         {
             _service.SaveStudent(request);
             return Ok();
         }
    }
```

As you can see clean architecture is quite easy to understand. I will suggest you take a look at the following .NET template which is developed by Jason Tylor for Clean architecture implementation, so that you will have a head start in your project.

<https://github.com/jasontaylordev/CleanArchitecture>

Thanks for reading, if you any questions or doubts please let me know in the comment section below.
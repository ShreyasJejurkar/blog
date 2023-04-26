---
id: 560
title: 'Log Entity Framework Core generated SQL in ASP.NET Core'
date: '2020-11-15T14:03:20+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=560'
permalink: /2020/11/15/log-entity-framework-core-generated-sql-in-asp-net-core/
timeline_notification:
    - '1605449003'
publicize_twitter_user:
    - MCCshreyas
amp_status:
    - ''
spay_email:
    - ''
image: /wp-content/uploads/2020/11/images.png
categories:
    - Uncategorized
tags:
    - .NET
    - dotnet
    - 'entity framework'
    - SQL
---

If you’re a .NET developer, then you are most probably familiar with Entity Framework data access technology that Microsoft provides for developers.  
But still, if you are not familiar then let me explain to you.  
Entity Framework is an Object (Relational) Mapper for database objects, meaning it lets you query database records using LINQ (Language-integrated query) and under the hood, it generates the resulting query based on your LINQ expression and executes it on the database, and if there are resulting records from SQL query then those records EF maps to your C# class objects, so that you don’t have to do that heavy lifting for mapping database values to C# objects and vice versa.

So the main point here is to understand that EF generates SQL query based on LINQ expression that the user has written. So while developing an ASP.NET Core Web application (Or any .NET application) or debugging a bug, you might need to see a generated query for your LINQ operation, and most probably you might want to log in to console so that based on it you can decide do you want to write a raw SQL query for given complex operation or wanna use EF generated query.  
So by default when you add the EF Core package to the application, it does not log the query to the console, we have to tell EF core explicitly to log the generated query to the console (or might be somewhere else).  
So in today’s post how we will see how we can do that. There are generally two ways to do so. But let’s proceed with a simple one.

**1<sup>st</sup> way**:  
This is the simplest way to start logging your generated query.  
In your `DbContext` class, you need to override the `OnConfiguring` method and need to add the following line to `optionsBuilder`. As we can see the `LogTo` (added in .NET 5) method takes `Action<string>` as a parameter. For simplicity, I am logging queries to Console but you can log it anywhere and second parameter we have to pass the `LogLevel`. By adding this, the EF core will start logging generated SQL to Console.

```csharp
  protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
        {
            optionsBuilder
                .EnableSensitiveDataLogging()
                .LogTo(Console.WriteLine, LogLevel.Information);

            base.OnConfiguring(optionsBuilder);
        }
```

**2<sup>nd</sup> way**:  
This way is quite simple and configurable as well. In the previous method as we see we need to modify the actual C# code to tell EF to start logging generated SQL but in this way, we just need to add an entry in the Logging section under appsettings.json file.

```json
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information",
      "Microsoft.EntityFrameworkCore.Database.Command": "Information"
    }
  },
```

After adding the above entry, the Logger abstraction will read this configuration at startup and will start logging EF generated SQL.  
One of the advantages of this is like, in production scenarios if we don’t want to log the generated SQL to console, so in that, we just need to remove or comment out this entry in JSON file, by doing so the EF will no longer log the generated SQL and this does not require the application restart, as the configuration will automatically get reloaded.

By following any of the steps mentioned above, you will see generated SQL to logs. If you face any problem while doing so, please let me ping in comment section below.

Thanks for reading!
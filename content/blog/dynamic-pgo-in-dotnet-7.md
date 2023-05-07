---
title: "Dynamic PGO in .NET 7"
date: 2023-05-07T06:33:32Z
slug: dynamic-pgo-in-dotnet7
author: ShreyasJejurkar
layout: post
categories:
    - Programming
tags:
    - dotnet
---

With .NET 7 release, the .NET team has released dynamic PGO functionality for JIT in CoreCLR. Static PGO was already there with .NET 6 release, but with 7, we have both Static and dynamic PGO. Static PGO is by default on in .NET 6 and 7, the dynamic PGO we have to opt into with the flag. But before we enable it, let’s understand quickly what PGO means itself and what’s the difference between its static and dynamic variants.

## What is PGO!?

PGO stands for Profile guided optimization. In this compiler optimizes the generated code based on its execution behavior and the flow. Generally, the compiler assumes that all the possible behavior of the code will always occur and happen at runtime as well. To simplify the understanding of this, one of the good code examples is the try/catch block, 90% of the time, the catch block won’t execute, because whatever is expected to happen in the try block will always happen, and in some exceptional scenario, the catch block will execute. So, in this one, the compiler can, even more, optimize the code path in the try block and can bring closer to the calling method for faster execution because that is the 90 % of occurring cases in the given scenario. So, in short with PGO, the compiler has some additional data to further optimize the code based on its execution behavior.

## Difference between Static PGO and Dynamic PGO.

Static PGO relies on statically available data for the execution. Most of the cases static PGO is getting used to improve the startup time, because it’s statically known that from a given method the execution will start, so in that we can pre-JIT that method to enable faster startup execution.
Whereas Dynamic PGO relies on real-time (dynamic) data for optimization. It monitors the hot path, frequently executing methods and a bunch of other things while running the actual application, and based on that data, it optimizes the codegen for those particular scenarios and hence the throughput of that application improves over the period.

## How to enable PGO in .NET 7?

For enabling static PGO we don’t have to do anything, it’s enabled by default in .NET 7. To enable dynamic PGO we have to opt into with the following property.

```xml
<PropertyGroup>
    <TieredPGO>true</TieredPGO>
</PropertyGroup>
```

We have to add the above property to the csproj file of the actual execution project like the ASP.NET Core WebAPI project or the Console project. 
If you have many projects in your solution and if you don’t want to go to each project and add this, you can create a Directory.Build.props file (parallel to the solution file) and put it like below.

```xml
<Project>
    <PropertyGroup>
        <TieredPGO>true</TieredPGO>
    </PropertyGroup>
</Project>
```

This file gets automatically read by dotnet build or msbuild at runtime and will apply those values at the time of actual build and publishing of the project.
So with the above steps, the dynamic PGO gets enabled for the JIT for your project. If you want to learn more about Dynamic PGO, please refer to the below set of links.

[Design document for dynamic PGO](https://github.com/dotnet/runtime/blob/main/docs/design/features/DynamicPgo.md)

[Conversations about PGO](https://devblogs.microsoft.com/dotnet/conversation-about-pgo/)

[EgorBO (JIT Engineer at Microsoft) write-up about PGO](https://gist.github.com/EgorBo/dc181796683da3d905a5295bfd3dd95b)


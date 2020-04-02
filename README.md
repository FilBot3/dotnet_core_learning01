# dotNet Core Learning

## Overview

This repository is mostly for me to learn how to work with .NET Core from
Microsoft. Its surprising fast on both Linux and Windows, but I think its a lot
faster on Linux. Surprisingly easy to get started with the `dotnet` command.

## Requirements

* dotnet Core SDK 3.1 or newer

## Setup

Add a NuGet Package source to dotnet

```bash
dotnet nuget add source --name nuget.org https://api.nuget.org/v3/index.json
```

This may require having `nuget` in your `PATH`.

Create a Project

```bash
dotnet new console --output src/HelloWorld
```

Create a new Test

```bash
dotnet new xunit --output test/HelloWorldTest
```

Add the Source as a Reference to the Test

```bash
dotnet add ./test/HelloWorldTest/HelloWorldTest.csproj reference ./src/HelloWorld/HelloWorld.csproj
```

Add both of these to a solution file for ease of management

```bash
dotnet new sln
dotnet sln add ./src/HelloWorld/HelloWorld.csproj
dotnet sln add ./test/HelloWorldTest/HelloWorldTest.csproj
```

## Usage

Build the project

```bash
dotnet build
```

Release the Project

```bash
dotnet publish --runtime linux-x64 --configuration Release
```

## Development and Testing

To perform linting, this can be done by using a tool called `StyleCop.Analyzers`.
Install StyleCop.Analyzers to each project you wish to have it run against.

```bash
dotnet add ${CSHARP_PROJECT}.csproj package StyleCop.Analyzers
```

Then perform a build to get all the style warnings. While the build might succeed,
it doesn't mean that you're code is stylistically appropriate. This is helpful for
performing CI/CD functionality.

Another tool that can be used in a CI/CD environment is the `dotnet tool` called
`dotnet-format`. Install the tools like this:

```bash
dotnet tool install --global dotnet-format
```

Then call the program like:

```bash
dotnet format --workspace example.sln --verbosity diag
```

### Branching Strategies

Follow GitFlow when performing development on this repository. That way changes can be tracked.

## References

* [Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/)
* [Microsoft .NET Core Guide](https://docs.microsoft.com/en-us/dotnet/core/)
* [Microsoft .NET Core API](https://docs.microsoft.com/en-us/dotnet/api/?view=netcore-3.1)


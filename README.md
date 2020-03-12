# dotNet Core Learning

## Overview

This repository is mostly for me to learn how to work with .NET Core from
Microsoft. Its surprising fast on both Linux and Windows, but I think its a lot
faster on Linux. Surprisingly easy to get started with the `dotnet` command.

## Requirements

* dotnet Core SDK 3.1 or newer

## Setup

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

TODO

## References

* [Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/)
* [Microsoft .NET Core Guide](https://docs.microsoft.com/en-us/dotnet/core/)
* [Microsoft .NET Core API](https://docs.microsoft.com/en-us/dotnet/api/?view=netcore-3.1)


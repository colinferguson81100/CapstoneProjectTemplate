# Summary of the Technical Aspects of this Project:
- This project is split into two parts – frontend and backend – and each have their own technologies.

# Explain what kind of technologies are needed to replicate and how.
Dependencies
- Dotnet Core >= [5.0](https://dotnet.microsoft.com/download)
- Vue [latest stable](https://vuejs.org/v2/guide/installation.html)

# Required IDEs, frameworks, etc.
No required ide, but it is recommended to have [VScode](https://code.visualstudio.com/) and install the extensions for csharp and vue

# Explain the folder structure of your code repositories and what they mean.

## Backend
```
├── bsu.ips-generator.backend.sln
├── Ips.PdfConverter
│   ├── bin
│   ├── Converter.cs
│   ├── Goal.cs
│   ├── Helpers.cs
│   ├── IpsDocument.cs
│   ├── Ips.PdfConverter.csproj
│   ├── obj
│   └── PdfModel.cs
├── Ips.Server
│   ├── appsettings.Development.json
│   ├── appsettings.json
│   ├── bin
│   ├── Files
│   ├── Ips.Server.csproj
│   ├── obj
│   ├── Program.cs
│   ├── Properties
│   └── Startup.cs
├── Ips.Test
│   ├── bin
│   ├── DocTest.cs
│   ├── Ips.Test.csproj
│   ├── obj
│   └── SetupTest.cs
└── README.md
```

The main logic for pdf generation is in the `Ips.PdfConverter` directory.
`Converter.cs` is the main class the `Server` communicates with.

The `IpsDocument` File specifies how the actually pdf "looks" along with
how the data is supplied to the document.

The Server part of the project is in the aptly named `Ips.Server` project.
The api endpoints are located in the `Startup.cs` file, this also functions as a reasonable server entry point.

Of course `Ips.Test` is where all the testing files go 


# This document will have a special section on how to test and how to interpret the result.
  - Running might be as simple as running a command or clicking some menu items.
  - Interpreting might be as simple as showing a sample testing report and explaining different parts of it.

navigate to the project root directory and enter
```bash
dotnet test
```
to run the tests.

## Frontend
```
─── bsu.ips-generator.frontend
    ├── node_modules
    ├── src
    │   ├── assets
    |   |   └── question.png
    │   ├── router
    |   |   └── index.js
    │   ├── views
    │   |   ├── FinalPage.vue
    │   |   ├── Goals.vue
    │   |   ├── Landing.vue
    │   |   ├── RiskTolerance.vue
    │   |   └── TimeHorizon.vue
    │   ├── App.vue
    │   └── main.js
    ├── tests
    |   └── add tests here
    ├── .gitignore
    ├── babel.config.js
    ├── Dockerfile
    ├── jest.config.js
    ├── package.json
    └── README.md
```
node_modules can be ignored

the router directory and index.js controlls the change to each page in the generator

each view in the views directory is a different section in the generator

App.vue and main.js controls and sets up the entire generator

tests directory contains tests for the frontend

.gitignore contains files than can be ignored by git

babel.config.js exports babel into the project which helps with javascript code

Dockerfile contains the docker setup and instructions on how to use it

jest.config.js exports jest into the project which helps with testing

package.json contains general information about what dependencies and configurations of the project

README.md contains instructions on how to run the frontend

#  Steps to run Docker for Frontend

Install Docker Desktop.
```
https://www.docker.com/products/docker-desktop
```

Build the image.
```bash
    docker build -t ips/bsu.ips-generator.frontend .
```

Create and start docker container.
```bash
    docker run -it -p 8080:8080 -d --name bsu.ips-generator.frontend ips/bsu.ips-generator.frontend
```

Use Docker Desktop to access the project.

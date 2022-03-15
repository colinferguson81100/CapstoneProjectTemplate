# Summary of the Technical Aspects of this Project:
- This project is split into two parts – frontend and backend – and each have their own technologies.

# Required Technologies to Replicate Our Project:
Dependencies
- Dotnet Core >= [5.0](https://dotnet.microsoft.com/download)
- Vue [latest stable](https://vuejs.org/v2/guide/installation.html)

# Required IDEs, frameworks, etc.
No required ide, but it is recommended to have [VScode](https://code.visualstudio.com/) and install the extensions for csharp and vue

# Explaining the Folder Structure of our Code Repositories:

### Backend:
```
.
├── bsu.ips-generator.backend.sln
├── bsu.ips-generator.backend.sln.DotSettings.user
├── docker-compose.debug.yml
├── docker-compose.yml
├── Ips.PdfConverter
│   ├── background.png
│   ├── bin
│   ├── Converter.cs
│   ├── Helpers.cs
│   ├── IpsDocument.cs
│   ├── Ips.PdfConverter.csproj
│   ├── obj
│   └── PdfModel.cs
├── Ips.Server
│   ├── appsettings.Development.json
│   ├── appsettings.json
│   ├── background.png
│   ├── bin
│   ├── Binders
│   ├── Controllers
│   ├── Dockerfile
│   ├── Ips.Server.csproj
│   ├── obj
│   ├── Program.cs
│   ├── Properties
│   └── Startup.cs
├── Ips.Test
│   ├── bin
│   ├── Dockerfile
│   ├── DocumentGenerationUnitTests.cs
│   ├── IntegrationTests.cs
│   ├── Ips.Test.csproj
│   ├── missingRiskTolerance.json
│   ├── obj
│   ├── validPdfJson.json
│   └── validpdf.pdf
└── README.md
```

The main logic for pdf generation is in the `Ips.PdfConverter` directory.
`Converter.cs` is the main class the `Server` communicates with.

The `IpsDocument` File specifies how the actually pdf "looks" along with
how the data is supplied to the document.

The Server part of the project is in the aptly named `Ips.Server` project.
It's api endpoints are located Controllers/ApiController class.

Of course `Ips.Test` is where all the testing files go


# This document will have a special section on how to test and how to interpret the result.
  - Running might be as simple as running a command or clicking some menu items.
  - Interpreting might be as simple as showing a sample testing report and explaining different parts of it.

navigate to the project root directory and enter
```bash
dotnet test
```
to run the tests.

### Frontend:
```
─── bsu.ips-generator.frontend
    ├── cypress
    │   └── ... (contains testing files)
    ├── node_modules
    ├── src
    │   ├── assets
    |   |   └── question.png
    │   ├── components
    │   |   ├── CurrencyInput.vue
    │   │   └── Sidebar.vue
    │   ├── router
    |   |   └── index.js
    │   ├── views
    │   |   ├── AssetAllocation.vue        
    │   |   ├── FinalPage.vue
    │   |   ├── Goals.vue
    │   |   ├── Landing.vue
    │   |   ├── RiskTolerance.vue
    │   |   └── TimeHorizon.vue
    │   ├── App.vue
    │   └── main.js
    ├── .dockerignore
    ├── .gitignore
    ├── cypress.json
    ├── Dockerfile
    ├── package-lock.json
    ├── package.json
    └── README.md
```
cypress is the frontend testing framework. All the tests for the frontend are stored here

node_modules can be ignored

the components directory holds components that are used in different views on the frontend

the router directory and index.js controlls the change to each page in the generator

each view in the views directory is a different section in the generator

App.vue and main.js controls and sets up the entire generator

tests directory contains tests for the frontend

.dockerignore contains files that can be ignored by docker

.gitignore contains files that can be ignored by git

cypress.json is used for storing configuration values for tests

Dockerfile contains the docker setup and instructions on how to use it

package.json and package-lock.json contains general information about what dependencies and configurations of the project

README.md contains instructions on how to run the frontend

# How to Test and How to Interpret the Result:
  - use the command npx cypress open to start up the cypress testing browser (make sure cypress is installed using npm install cypress)
  - go to the testing browser and click on the test files you want to run
  - once clicked cypress should run through all the tests and check if they pass or fail

#  Replicating the Project with Docker

### Replication Steps:

Install Docker Desktop and **ensure it is currently running on your machine.**
```
https://www.docker.com/products/docker-desktop
```

Clone the InvestAway repository onto your machine. It does not matter where it is cloned to as long as you remember where it is.
```bash
git clone https://423rd@bitbucket.org/accutechdev/bsu.ips-generator.frontend.git
```

*Note: Some IDEs will suggest that some dependencies are missing upon loading the project for the first time.
This can be ignored, as docker will install the required dependencies.*

Navigate to the project directory if you are not already there.
```
cd bsu.ips-generator.frontend\backend\Ips.PdfConverter
```

Open a terminal in this location (if you are not already using one) and start the server:
```
docker-compose up --build
```

Open one of the following url links in your internet browser to begin the quiz!
- Windows & Mac: http://127.0.0.1:8080
- Linux: http://172.18.0.3:8080

### Resolving Errors:

General troubleshooting tip:
- Check for updates within your IDE, Git Bash, and Docker Desktop and update as necessary.

If you receive this error:
```
Error response from daemon: open \\.\pipe\docker_engine_linux: The system cannot find the file specified.
```
Try running the following commands:
```
docker-compose down
dotnet restore
cd bsu.ips-generator.frontend\backend\Ips.PdfConverter
docker-compose up --build
```

If you recieve this error:
```
error during connect: This error may indicate that the docker daemon is not running.
```
ensure that Docker Desktop is properly installed and **is currently running**.

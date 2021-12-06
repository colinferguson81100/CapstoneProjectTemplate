# How to Set Up the Project
- This project comes in two parts: a frontend and a backend.
    - The frontend involves the parts of the code that a user will interact with, such as our questionnaire and user interface.
    - The backend contains code that the user does not directly see or interact with, such as creating a PDF document.

- There are two ways to build our project: manually and through Docker Desktop. Both approaches are detailed below.

# Without Docker (Manual Setup):
### Backend:

Clone the backend repository onto your machine. It does not matter where it is cloned to as long as you remember where it is.
```bash
    git clone https://sanaugler@bitbucket.org/accutechdev/bsu.ips-generator.backend.git
```

Navigate to the project directory.
```bash
    cd bsu.ips.generator
```

Install the required dependencies.
```bash
    dotnet restore
```

### Frontend:

Clone the frontend repository onto your machine. It does not matter where it is cloned to as long as you remember where it is.
```bash
https://bitbucket.org/accutechdev/bsu.ips-generator.frontend.git
```

Install the required npm packages.
```bash
    npm install
```

Run the project.
```bash
    npm run serve
```

Go to localhost 8080


# With Docker Desktop (Semi-Automated Setup):
### Backend:

Coming Soon!

### Frontend:
Clone the frontend repository onto your machine. It does not matter where it is cloned to as long as you remember where it is.
```bash
https://bitbucket.org/accutechdev/bsu.ips-generator.frontend.git
```

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

# Utilizing Our Project: 
1. Complete the questionnaire through the frontend.
1. Once complete, your investment policy statement (IPS) will be created as a PDF document with the information from your questionnaire answers.
1. The PDF file may be downloaded through your browser!

# Troubleshooting
- All errors will be output to the console
Small bug with generating pdf. May have to press the "Generate PDF button twice"


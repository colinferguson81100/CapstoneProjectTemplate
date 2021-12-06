# Setup

## Setup the frontend and backend. (clone locations don't matter).

### Backend Setup 
```bash
    git clone https://sanaugler@bitbucket.org/accutechdev/bsu.ips-generator.backend.git
```

Go to the project directory

```bash
    cd bsu.ips.generator
```

Install dependencies

```bash
    dotnet restore
```

### Frontend setup

1. Clone the frontend repository onto your computer

Without Docker:

2. Install npm packages
```bash
    npm install
```

3. Run project
```bash
    npm run serve
```

4. Go to localhost 8080

With Docker:

2. Install Docker Desktop

3. Build image
```bash
    docker build -t ips/bsu.ips-generator.frontend .
```

4. Create and start docker container
```bash
    docker run -it -p 8080:8080 -d --name bsu.ips-generator.frontend ips/bsu.ips-generator.frontend
```

5. Use Docker desktop to access project

## Runthrough 
1. go through the frontend and make a pdf
1. pdf file should be downloaded through your browser

# Troubleshooting

Small bug with generating pdf. May have to press the "Generate PDF button twice"


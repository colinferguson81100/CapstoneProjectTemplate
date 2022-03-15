# How to Set Up the Project
- This project comes in two parts: a frontend and a backend.
    - The frontend involves the parts of the code that a user will interact with, such as our questionnaire and user interface.
    - The backend contains code that the user does not directly see or interact with, such as creating a PDF document.

Clone the repository onto your machine. It does not matter where it is cloned to as long as you remember where it is.
```bash
git clone https://sanaugler@bitbucket.org/accutechdev/bsu.ips-generator.frontend.git
```

Navigate to the project directory if you are not already there.
```
cd bsu.ips-generator.frontend
```

Start the server.
```
docker-compose up --build
```

Tear down the server if needed (hold control and hit c to stop the asp.net service).
```
docker-compose down
```

Url to send data too for pdf creation:
```
http://0.0.0.0:5000/api/Post
```

Use Docker Desktop to access the project.

# Utilizing Our Project: 
1. Complete the questionnaire through the frontend.
1. Once complete, your investment policy statement (IPS) will be created as a PDF document with the information from your questionnaire answers.
1. The PDF file may be downloaded through your browser!

# Troubleshooting
- All errors will be outputted to the console.


# ResumeAI

## Overview

The project is a MEAN project and uses node version 18.

# Deploying Backend
############# DEPLOYING BACKEND ######################

1. Cloned the repository into local directory

```bash
git clone https://github.com/CharismaticOwl/ResumeAI.git

cd ResumeAI/ResumeBuilderBackend
```

2. Created a .env file for environment variables

```
JWT_SECRET_KEY="MYREALLYSECRETKEY"
MONGO_URL="mongodb+srv://**************/resume_builder"
OPENAI_KEY="OPENAI_API_KEY"
GMAIL_USER="THIS EMAIL IS USED TO SEND RESUMES"
GMAIL_PASS="PASSWORD USED BY NODEMAILER"
FRONT_END="URL FOR FRONTEND"
```

3. Created a dockerfile

```
Base image used is node:alpine

created a WORKDIR - /app

copied all the local files to the workdir

now run npm install --force

Also install typescript and ng gloabally

Compile the typescript code with tsc command

expose port 4292, as the app will be listening here

command - nohup npm start

nohup - no hang up when the termial is exited
```

4. Test the localhost:4292 for an output

```
Cannot GET /
```

5. Push the image to docker repo or ECR


#############Congrats Backend is deployed##############
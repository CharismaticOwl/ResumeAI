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

# Deploying Frontend
############# DEPLOYING FRONTEND ######################

1. Naviage to resumeAI folder, where both backend and frontend code is present.

```
cd ResumeBuilderAngular
```

2. Change the package.conf.json file

```json
{
    "/api": {
      "target": "http://backend:4292",
      "secure": false
    }
  }
```

3. Created a Docker file

```
Used base image node:alpine

Created a working directory /app

copied all the file from local to /app

run npm install --force

also run the other dependencies

npm i -g ng @angular/cli

build the app

run npm run build

exposed port 4200

comand nohup npm start

nohup - means no hang up, the process with not terminate when the terminal is exited
```

4. Test the application at localhost:4200, you can try login

5. Push the image to docker repo or ECR


#############Congrats Frontend is deployed##############

# Docker Compose
############# DEPLOYING THE ENTIRE APP USING DOCKER-COMPOSE######################

1. Create a docker compose file, it should with .yaml file extension

2. first service for backend, build the image and also context is specified
 ports 4292 is exposed

3. frontend will be built, order is defined using depends_on option and expose port 4200

4. using docker-compose up command to build the images and deploy.

# Create ECR  public repos to push the images to ECR and docker hub

```
public.ecr.aws/w4c5t7g4/resumeai-backend
public.ecr.aws/w4c5t7g4/resumeai-frontend
public.ecr.aws/w4c5t7g4/resumeai-nginx
```

```
docker.io/narsss1234/resumeai-frontend
docker.io/narsss1234/resumeai-backend
docker.io/narsss1234/resumeai-nginx
```

# 
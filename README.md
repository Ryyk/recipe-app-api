# recipe-app-api


##Dockerfile:

- **"FROM python:3.7-alpine"** - Base image for the docker 
- **"ENV PYTHONUNBUFFERED 1"** - Prevents python from buffering the outputs inside the docker image, intead prints them directly.
- **"COPY ./requirements.txt /requirements.txt"** - Copy the requirements file to the docker image.
- **"RUN mkdir /app"** - Folder where the app source code will be 
- **"RUN adduser -D user"** - Creates a user to run application to prevent someone from gaining acces to the whole docker image.

##Docker-compose:



##Tools used:

###Django:
- Python web framework
- Build web apps rapidly
- Provides object relational mapper (ORM)
    - convert objects to database rows automaticly
- Django admin to manage database

###Django Rest framework:
- Extension to Django to build REST API's
- Built in authentication for the API endpoints
- Viewsets to build the structure of the API and provide the endpoints to manage the objects
- Serializers to validate the requests to the API and help convert JSON objects to database models


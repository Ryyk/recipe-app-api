# recipe-app-api


## Dockerfile:

- **"FROM python:3.7-alpine"** - Base image for the docker 
- **"ENV PYTHONUNBUFFERED 1"** - Prevents python from buffering the outputs inside the docker image, intead prints them directly.
- **"COPY ./requirements.txt /requirements.txt"** - Copy the requirements file to the docker image.
- **"RUN mkdir /app"** - Folder where the app source code will be 
- **"RUN adduser -D user"** - Creates a user to run application to prevent someone from gaining acces to the whole docker image.

## Docker-compose:

- A tool that allows to run a docker image easly from the project location.
- Allow to easily manage the different services that make the project, for instance the python application and the database.
- version: "3" - Version of the docker compose
- "context: ." - Current directory to run docker compose
- "ports:" - Match the port 8000 on the host to port 8000 on the image.
- "volume" - Maps the volume of the local machine into the docker container. Making it possible to get the updates that we make to our project into our docker image in real time. Whenever we change a file will be updated in the container without building an docker image again.

## Travis (similar to Jenkins):
- Continuous integration tool to automate tests and checks on projects every time we push changes.

## Django:
- Python web framework
- Build web apps rapidly
- Provides object relational mapper (ORM)
    - convert objects to database rows automaticly
- Django admin to manage database

## Django Rest framework:
- Extension to Django to build REST API's
- Built in authentication for the API endpoints
- Viewsets to build the structure of the API and provide the endpoints to manage the objects
- Serializers to validate the requests to the API and help convert JSON objects to database models


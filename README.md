# REST API with Python, Django REST Framework and Docker using Test Driven Development (TDD)


## Docker:

![alt text](https://image.slidesharecdn.com/icwe2016dockertutorial-160607091958/95/using-docker-containers-to-improve-reproducibility-in-software-and-web-engineering-37-638.jpg?cb=1474409524)

- A docker image can be run by multiple containers.

**Important commands:**
- "docker build ." - create image with dockerfile
- "docker images" - list all images
- "docker run <image> sh -c "ls" - run image with shell and pass a specific command 
- "docker run -it <image> sh" - run image and open shell

### Dockerfile 
- **"FROM python:3.7-alpine"** - Base image for the docker 
- **"ENV PYTHONUNBUFFERED 1"** - Prevents python from buffering the outputs inside the docker image, intead prints them directly.
- **"COPY ./requirements.txt /requirements.txt"** - Copy the requirements file to the docker image.
- **"RUN mkdir /app"** - Folder where the app source code will be 
- **"RUN adduser -D user"** - Creates a user to run application to prevent someone from gaining acces to the whole docker image.

### Docker-compose:

- A tool that allows to run a docker image easly from the project location and helps managing different containers. 
- Docker Compose, “a tool for defining and running complex applications with Docker. With Compose, you define a multi-container application in a single file, then spin your application up in a single command which does everything that needs to be done to get it running.” 
All of that can be done by Docker Compose in the scope of a single host. In that sense, its concept is very similar to Kubernetes pods. For multi-host deployment, you should use more advanced solutions, like Apache Mesos or a complete Google Kubernetes architecture. 
- Allow to easily manage the different services that make the project, for instance the python application and the database.
- version: "3" - Version of the docker compose
- "context: ." - Current directory to run docker compose. Where the dockerfile is.
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
- https://docs.djangoproject.com/en/2.2/intro/tutorial01/ 

**Important commands:**
- docker-compose run app sh -c "django-admin.py startproject app ." - create django project using docker compose
- docker-compose run app sh -c "python manage.py startapp core" - create core app
- docker-compose run app sh -c "python manage.py makemigrations core" - Creates a new migrations/ file that allows Django to create the model in the database that we use. Everytime changes are done to the model the command needs to be run

## Django Rest framework:
- Extension to Django to build REST API's
- Built in authentication for the API endpoints
- Viewsets to build the structure of the API and provide the endpoints to manage the objects
- Serializers to validate the requests to the API and help convert JSON objects to database models


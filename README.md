# docker_flask_homework
This assignment aims to provide hands-on experience in Dockerizing Flask applications, first individually and then using Docker Compose for managing multiple applications.

# Dockerized Flask Applications

This repository is dedicated to a hands-on exploration of Dockerizing Flask applications, covering both individual setups and the orchestration of multiple applications using Docker Compose.

## Part 1 - Dockerizing a Single Flask Application

### Setting Up and Dockerizing a Flask App:

- Create a folder and name it Part1.
- Develop a Flask application within the Part1 folder.
- Additionally, craft a Dockerfile and name it Dockerfile.

- Create a text file named requirements.txt. Add "flask" to the file.
- In your Cloud Shell terminal, execute `docker build -t <name_of_image> .` to build the image.
- Employ `docker images` to inspect the list of images.
- Utilize `docker run -d -p <port1>:5000 <name_of_image>` to run the image in a container.
- Preview the image by changing the port to 1 in Cloud Shell.
- Observe the list of containers with `docker ps`.
- Stop the container using `docker stop <container_ID>`.
- Remove the container with `docker rm <container_ID>`.
- Clean and remove everything with `docker system prune -a -f`.

## Part 2 - Dockerizing Multiple Flask Applications

### Preparing Multiple Flask Applications:

- Create a folder and name it Part2.
- Form a Docker Compose file and name it docker-compose.yml, usinngg code:

```yaml
version: '3'
services:
  flask1:
    build: ./flask1
    ports:
      - "5001:5000"
  flask2:
    build: ./flask2
    ports:
      - "5002:5000"
```
Create two folders: flask1 and flask2.
In each folder, generate a Flask application (app.py), a Dockerfile, and a requirements.txt file.
Use the provided Dockerfile code in both Flask folders.
Add "flask" to the requirements.txt file in both folders.
Dockerizing with Docker Compose:
In your Cloud Shell terminal, execute docker-compose build to build your images.
Use docker-compose up to run your images in containers.
Preview your images by adjusting ports according to the Docker Compose file.
Inspect a list of containers with docker-compose ps.
Halt your containers with docker-compose down.
Clean and remove everything with docker system prune -a -f.
Explanation of Docker Compose
Version: Version of the Docker Compose file.
Services: Services for the application.
Build: Specific path.
Ports: Maps a port from the host machine to a port from an image container.
Volumes: Mounts a directory from the host machine to the image container.

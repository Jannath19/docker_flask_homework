# docker_flask_homework
This assignment aims to provide hands-on experience in Dockerizing Flask applications, first individually and then using Docker Compose for managing multiple applications.

Dockerizing Flask Applications
Part 1: Dockerizing a Single Flask Application
Setting Up and Dockerizing a Flask App:
Create a folder and name it Part1.
Create a Flask application within the Part1 folder.
Additionally, create a Dockerfile and name it Dockerfile. 

Create a text file and name it requirements.txt. Add "flask" to the file.
In your Cloud Shell terminal, type docker build -t <name_of_image> . to build the image.
Type docker images to view the list of images.
Type docker run -d -p <port1>:5000 <name_of_image> to run the image in a container.
Preview the image by changing the port to port 1 in Cloud Shell.
Type docker ps to view a list of containers.
Type docker stop <container_ID> to stop the container.
Type docker rm <container_ID> to remove the container.
Type docker system prune -a -f to clean and remove everything.

Part 2: Dockerizing Multiple Flask Applications 
Preparing Multiple Flask Applications:

Create a folder and name it Part2.
Create a Docker Compose file and name it docker-compose.yml. Use the following code:
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
Create two folders: flask1 and flask2.

In each folder, create a Flask application (app.py), a Dockerfile, and a requirements.txt file.

Use the provided Dockerfile code in both Flask folders.

Add "flask" to the requirements.txt file in both folders.

Dockerizing with Docker Compose:

In your Cloud Shell terminal, type docker-compose build to build your images.
Type docker-compose up to run your images in containers.
Preview your images by changing ports according to the Docker Compose file.
Type docker-compose ps to view a list of containers.
Type docker-compose down to stop your containers.
Type docker system prune -a -f to clean and remove everything.
Explanation of Docker Compose
Version: Version of the Docker Compose file.
Services: Services for the application.
Build: Specific path.
Ports: Maps a port from the host machine to a port from an image container.
Volumes: Mounts a directory from the host machine to the image container.






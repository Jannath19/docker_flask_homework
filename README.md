# docker_flask_homework
This assignment aims to provide hands-on experience in Dockerizing Flask applications, first individually and then using Docker Compose for managing multiple applications.

Dockerizing Flask Applications
Part 1: Dockerizing a Single Flask Application
Setting Up and Dockerizing a Flask App:
Create a folder and name it Part1.
Create a Flask application within the Part1 folder.
Additionally, create a Dockerfile and name it Dockerfile. Use the following code:
# Use an official Python runtime as a parent image
FROM python:3.8-slim

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app/
COPY . /app/

# Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]
Create a text file and name it requirements.txt. Add "flask" to the file.
In your Cloud Shell terminal, type docker build -t <name_of_image> . to build the image.
Type docker images to view the list of images.
Type docker run -d -p <port1>:5000 <name_of_image> to run the image in a container.
Preview the image by changing the port to port 1 in Cloud Shell.
Type docker ps to view a list of containers.
Type docker stop <container_ID> to stop the container.
Type docker rm <container_ID> to remove the container.
Type docker system prune -a -f to clean and remove everything.
Part 2: Dockerizing Multiple Flask Applications (Using Compose)
Preparing Multiple Flask Applications:

Create a folder and name it Part2.
Create a Docker Compose file and name it docker-compose.yml. Use the following code:
yaml
Copy code
version: '3'
services:
  flask1:
    build: ./flask1

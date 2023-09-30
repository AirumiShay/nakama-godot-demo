# Use the official Ubuntu 22.04 image

FROM ubuntu:latest

# Install the required packages

RUN apt-get update &&  install -y apt-transport-https ca-certificates curl software-properties-common 
RUN apt-get install -y docker.io docker-compose
RUN apt-get install python3.11 python3-pip -y
# Set the environment variable

ENV DOCKER_HOST=unix:///var/run/docker.sock

# Copy the project files into the container

COPY . /app

# Set the working directory

WORKDIR /app

# Expose the ports

EXPOSE 8080 7350 26257 7349 7351 9100 9090
RUN dockerd &
RUN usermod -aG docker root
RUN sleep 25
RUN ps aux | grep dockerd

RUN docker ps

RUN sleep 25
RUN ps aux | grep dockerd
# Specify the command to run when the container starts
RUN docker-compose -f docker-compose.yml up --verbose

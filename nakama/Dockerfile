# Use the official Ubuntu 20.04 image

FROM ubuntu:latest

# Install the required packages

RUN apt-get update && apt-get install -y curl docker.io docker-compose

# Set the environment variable

ENV DOCKER_HOST=unix:///var/run/docker.sock

# Copy the project files into the container

COPY . /app

# Set the working directory

WORKDIR /app

# Expose the ports

EXPOSE 8080 7350 26257 7349 7351 9100 9090
RUN dockerd &
RUN sleep 5
RUN ps aux | grep dockerd
RUN sleep 5
# Specify the command to run when the container starts
RUN docker-compose -f docker-compose.yml up

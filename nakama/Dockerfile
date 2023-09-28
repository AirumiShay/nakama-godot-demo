# Use the official Ubuntu 20.04 image

FROM ubuntu:20.04

# Install the required packages

RUN apt-get update && apt-get install -y curl docker.io docker-compose

# Set the environment variable

ENV DOCKER_HOST=unix:///var/run/docker.sock

# Copy the project files into the container

COPY . /app

# Set the working directory

WORKDIR /app

# Expose the port

EXPOSE 7350/tcp

# Run the server

CMD ["docker-compose", "-f", "docker-compose.yml", "up"]

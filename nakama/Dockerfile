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

# Expose the ports

EXPOSE 8080/tcp 7350/tcp 26257/tcp 7349/tcp 7351/tcp 9100/tcp 9090/tcp

# Specify the command to run when the container starts

CMD ["docker-compose", "-f", "docker-compose.yml", "up"]

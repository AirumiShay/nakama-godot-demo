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

EXPOSE 8080/tcp
EXPOSE 7350/tcp
EXPOSE 26257/tcp
EXPOSE 7349/tcp
EXPOSE 7351/tcp
EXPOSE 9100/tcp
EXPOSE 9090/tcp
# Run the server

CMD ["dockerd &", "sleep 5", "docker-compose", "-f", "docker-compose.yml", "up"]

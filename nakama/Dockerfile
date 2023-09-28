FROM ubuntu:20.04

RUN apt-get update && apt-get install -y curl docker.io docker-compose

COPY . /app

WORKDIR /app

EXPOSE <port>

CMD docker-compose -f docker-compose.yml up
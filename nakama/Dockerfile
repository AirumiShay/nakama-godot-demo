# Используем образ Ubuntu 20.04
FROM ubuntu:20.04

# Устанавливаем необходимые пакеты
RUN apt-get update && apt-get install -y curl docker.io docker-compose
# Запускаем демона Docker

RUN dockerd &
# Устанавливаем переменную DOCKER_HOST
ENV DOCKER_HOST=unix:///var/run/docker.sock

# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app
EXPOSE 7350
# Запускаем сервер Nakama
CMD docker-compose -v && ls  && docker-compose -f docker-compose.yml up

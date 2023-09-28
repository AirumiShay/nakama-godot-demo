# Используем образ Ubuntu 20.04
FROM ubuntu:20.04

# Устанавливаем необходимые пакеты
RUN apt-get update && apt-get install -y curl docker.io docker-compose

# Устанавливаем переменную DOCKER_HOST
ENV DOCKER_HOST=unix:///var/run/docker.sock
# Запускаем демона Docker
RUN nohup dockerd &

# Ждем, пока демон Docker запустится
RUN sleep 5
# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app

# Открываем порт

EXPOSE 7350/tcp
# Запускаем сервер Nakama
RUN  docker && docker ps && docker-compose -f docker-compose.yml up

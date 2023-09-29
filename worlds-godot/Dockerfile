# Используем образ Ubuntu 20.04
FROM ubuntu:20.04

# Устанавливаем необходимые пакеты
RUN apt-get update 
RUN pwd && ls -l && tar -xf server.tar.xz
# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app
EXPOSE 5225/tcp

# Распаковываем сервер
CMD ls
# Запускаем сервер Godot
CMD ./server --main-pack server.pck

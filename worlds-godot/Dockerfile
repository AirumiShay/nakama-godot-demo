# Используем образ Ubuntu 20.04
FROM ubuntu:20.04

# Устанавливаем необходимые пакеты
RUN apt-get update
# Распаковываем сервер
RUN pwd && ls -l && tar -xf server.tar.xz
# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app
EXPOSE 5225/tcp



# Запускаем сервер Godot
CMD pwd && ls && ./server --main-pack server.pck

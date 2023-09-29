# Используем образ Ubuntu 20.04
FROM ubuntu:latest

# Устанавливаем необходимые пакеты
RUN apt-get update -y

# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app
# Распаковываем сервер
RUN pwd && ls -l && tar -xf /app/server.tar.gz -C /app

EXPOSE 5225

# Запускаем сервер Godot
CMD /app/server --main-pack /app/server.pck


# Используем образ Ubuntu 20.04
FROM ubuntu:latest

# Устанавливаем необходимые пакеты
RUN apt-get update -y

# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app
# Распаковываем сервер
RUN mkdir godot
RUN pwd && ls -l && tar -xfv /app/server.tar.gz -C /
RUN cd /app/server && python /app/server/server.py
EXPOSE 5225

# Запускаем сервер Godot
CMD /server --main-pack /app/server.pck


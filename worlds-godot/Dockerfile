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
RUN pwd && ls -l && tar -xf /app/server.tar.gz -C /app/godot
RUN cd /app/server && python3 /app/server/server.py
EXPOSE 5225

# Запускаем сервер Godot
CMD /app/godot/server --main-pack /app/server.pck


# Используем образ Ubuntu 20.04
FROM ubuntu:latest
FROM python:3.11
# Устанавливаем необходимые пакеты
RUN apt-get update -y && apt-get install python3.11  -y

# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app
# Распаковываем сервер
#RUN pip install tornado
RUN pwd && ls -l && tar -xf /app/server.tar.gz -C /
RUN cd /app/server && python3 /app/server/server.py
EXPOSE 5225

# Запускаем сервер Godot
CMD /server --main-pack /app/server.pck


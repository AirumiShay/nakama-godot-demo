# Используем образ Ubuntu 22.04
FROM ubuntu:latest
FROM python:3.11
# Устанавливаем необходимые пакеты
RUN apt-get update -y && apt-get install python3.11 python3-pip -y

# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app
# Распаковываем сервер
#RUN pip3 install --upgrade pip
RUN pip3 install tornado

EXPOSE  9998 

RUN wget -qO- ident.me

RUN sleep 5

# Запускаем python3-сервер Worlds port 9998  - run OK ,but Godot-client don't can connect to server.
CMD wget -qO- ident.me && cd /app/server && python3 /app/server.py 

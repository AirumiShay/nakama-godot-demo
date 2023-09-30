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
RUN pip3 install --upgrade pip
RUN pip3 install tornado
#RUN pwd && ls /app && 
RUN tar -xf /app/server.tar.gz -C /
#RUN ls /
EXPOSE  9998 6317 5225
RUN sleep 5
RUN wget -qO- ident.me
# Запускаем python3-сервер MUD CataclysmLD port 6317
#RUN cd /app/mud && python3 /app/mud/server.py &
RUN sleep 5
# Запускаем сервер Godot  в фоне на порту 5225 - not working now
RUN /server --main-pack /app/server.pck &
# Запускаем python3-сервер MUD CataclysmLD port 6317
CMD cd /app/mud && python3 /app/mud/server.py
# Запускаем python3-сервер Worlds port 9998  - run OK ,but Godot-client don't can connect to server.Запускаем python3-сервер MUD CataclysmLD port 6317
#CMD wget -qO- ident.me && cd /app/server && python3 /app/server/server.py & && cd /app/mud && python3 /app/mud/server.py

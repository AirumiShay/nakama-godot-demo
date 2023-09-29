# Используем образ Ubuntu 20.04
FROM ubuntu:20.04

# Устанавливаем необходимые пакеты
#RUN apt-get update

# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app
# Распаковываем сервер
RUN pwd && ls -l && tar -xf /app/server.tar.gz -C /app

EXPOSE 5225/tcp



# Запускаем сервер Godot
CMD /app/server --main-pack /app/server.pck

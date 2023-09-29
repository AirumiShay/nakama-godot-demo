# Используем образ Ubuntu 20.04
FROM ubuntu:20.04

# Устанавливаем необходимые пакеты
RUN apt-get update 

# Копируем файлы проекта в контейнер
COPY . /app

# Задаем рабочую директорию
WORKDIR /app
EXPOSE 5225/tcp
RUN tar -xf server.tar.xz
# Запускаем сервер Nakama
CMD ["./server", "--main-pack". "server.pck"]

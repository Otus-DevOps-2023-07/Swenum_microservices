# Swenum_microservices
Swenum microservices repository

## Выполнено ДЗ № 15

### В процессе сделано

- Изучена работа контейнера с сетевыми драйверами none, host, bridge
- Проведен эксперимент многократного запуска контейнера nginx с сетью host
- Исследовано поведение net-namespaces при запуске контейнеров с драйверами none и host
- Изучен функционал сетевых алиасов при запуске проекта reddit с использованием bridge-сети
- Изучена работа контейнеров одновременно в нескольких сетях
- Исследовано поведение сетевого стека Linux при запуске контейнеров с bridge сетями
- Исследовано изменение цепочек iptables при запуске контейнеров с bridge сетями
- Проект reddit описан в файле docker-compose.yml  и параметризирован в файле .env

- Базовое имя проекта изменено при помощи переменной `COMPOSE_PROJECT_NAME=reddit`;
- Создан файл `docker-compose.override.yml` с целью переопределения инструкции `command` контейнеров `comment` и `ui`, а также пробрасывания папки с кодом с хоста внутрь контейнеров:
```
version: '3.3'
services:
  ui:
    volumes:
      - ./ui/:/app/
    command: ["puma", "--debug", "-w", "2"]
  comment:
    volumes:
      - ./comment/:/app/
    command: ["puma", "--debug", "-w", "2"]
  post:
    volumes:
      - ./post-py/:/app/
```


## Выполнено ДЗ № 14

### В процессе сделано

- Скачан и распакован архив
- Созданы Dockerfile
- Собраны образы из Dockerfile
- Проверена работаа docker network
- Запущены контейнеры из образов

### Комманды запуска

```
docker run -d --network=reddit  --network-alias=post_db --network-alias=comment_db mongo:3.6
docker run -d --network=reddit  --network-alias=post tigerbybyby/post:1.0
docker run -d --network=reddit  --network-alias=comment tigerbybyby/comment:1.0
docker run -d --network=reddit  -p 9292:9292 tigerbybyby/ui:1.0
```


## Выполнено ДЗ №13

### В процессе сделано

- Установлен Docker
- Изучены и протестированы комманды: ps, images, run, create, exec, commit, kill, system
- Установлен docker-machine
- Создан Dockerfile, build an image and runned container
- Создан dockerhub account
- Загружены образы dockerhub


### Комманды запуска
```
docker run --name reddit -d -p 9292:9292 swenum/otus-reddit:1.0
```


## Выполнено ДЗ №12

Заглушка для закрытия ДЗ на сайте otus

# Swenum_microservices
Swenum microservices repository


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
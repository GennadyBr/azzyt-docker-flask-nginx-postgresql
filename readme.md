# Пример Веб Приложения

С использованием технологий:

- Docker 
- Compose 
- Flask 
- Gunicorn 
- PostgreSQL 
- pgamin
- nginx (reverse proxy) 

Для видео на канале Azzrael Code https://www.youtube.com/watch?v=w7Sx_QNCekE

## Для запуска

Поднять истанс в Яндекс Compute Cloud как написано здесь https://azzrael.ru/yandex-compute-cloud-docker-python-flask 
и в истансе склонировать репозиторий

```bash
git clone https://github.com/AzzraelCode/azzyt-docker-flask-nginx-postgresql.git app
```

Затем забилдить и поднять контейнер с помощью Docker Compose
в этом помогут команды ниже

```
# Билд
sudo docker-compose build
# Запуск
sudo docker-compose up
# Запуск в фоне
sudo docker-compose up -d --build
# Остановка
sudo docker-compose stop
```
Чтобы обращаться к домену описанному в nginx.conf нужно или проделегировать домен (но это отдельная тема),
либо прописать в hosts соотв. IP домену. Если запуск предполагается только локально, то можно просто удалить server_name azzrael_code.yt;
из nginx.conf. 

Пожробнее см. видео на канале https://www.youtube.com/watch?v=w7Sx_QNCekE

## Внешние тома

База и приложение пробрасываются на хост! На деве - это норм, на проде - нужно спрятать внутрь!

## Полезные ссылки

Мое видео во многом основано на мануале отсюда https://testdriven.io/blog/dockerizing-flask-with-postgres-gunicorn-and-nginx/ но сильно отличается. 
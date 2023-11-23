![kittygram](https://github.com/aleksey-vasilev/kittygram_final/actions/workflows/main.yml/badge.svg?event=push)

## Проект «Kittygram»

### Описание:

Проект Kittygram позволяет собирать информацию котах и кошках пользователей - их фото, клички и достижения.
Предусмотрена регистрация пользователей и и возможность общения с базой через API.

### Стек:

```
Python 3.9 as programming language
```

```
Django 3.2 as web framework

```

```
Django REST framework 3.12 as toolkit for building Web APIs
```

```
Postgres as database
```

```
GitHub as repo and workflows manager
```

### Установка:

1. Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/aleksey-vasilev/kittygram_final
cd kittygram
```

2. Создайть файл .env и заполнить его своими данными

```
POSTGRES_DB=...
POSTGRES_USER=...
POSTGRES_PASSWORD=...
DB_HOST=...
DB_PORT=..
```

3. Для установки docker compose на сервер, выполнить следующие действия:

```
sudo apt update
sudo apt install curl
curl -fSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh
sudo apt-get install docker-compose-plugin
```

4. Перейти в директорию kittygram/ и запустить docker compose в режиме демона:

```
sudo docker compose -f docker-compose.production.yml up -d
```

5. Выполнить миграции и собрать статические файлы бэкенда в /backend_static/static/

```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
```

### Автор:

Алексей Васильев (aleksey-vasilev)

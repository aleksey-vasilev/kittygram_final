[![kittygram](https://github.com/aleksey-vasilev/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/aleksey-vasilev/kittygram_final/actions/workflows/main.yml)

## Проект «Kittygram»

### Описание:

Учебный прокт Kittygram позволяет собирать информацию котах и кошках пользователей - их фото, клички и достижения.

Предусмотрена регистрация пользователей и и возможность общения с базой через API.

Настроено развертывание через докер и CI/CD через GitHub Actions.

### Используемые технологии

![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Postgres](https://img.shields.io/badge/mysql-%2300f.svg?&style=for-the-badge&logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/docker%20-%230db7ed.svg?&style=for-the-badge&logo=docker&logoColor=white)
![GitHub](https://img.shields.io/badge/github%20-%23121011.svg?&style=for-the-badge&logo=github&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/github%20actions%20-%232671E5.svg?&style=for-the-badge&logo=github%20actions&logoColor=white)

### Необходимые инструменты

* [Python](https://www.python.org/)
* [Pip](https://pypi.org/project/pip/)
* [Django](https://www.djangoproject.com/)

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

# Kittygram - социальная сеть на самых минималках для размещение фотографий котиков.
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) 
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white) 
![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray)
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![Djoser](https://img.shields.io/badge/Djoser-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) 
![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) 

Сайт «Kittygram». Онлайн-сервис и API где пользователь может опубликовать краткую информацию и фотографии своих любимых питомцев, посмотреть питомцев других пользователей, 

### Функционал проекта Kittygram:
- Регистрация пользователя
- Загрузка,редактирование и удаление фотографий и информации о котиках
- Возможность просмотра фотографий котиков других пользователей 

## Технологии
 - Python 3.10 либо выше
 - Django
 - Django Rest Framework
 - Djoser
 - Nginx
 - Gunicorn
 
## Установка проекта на локальный компьютер из репозитория 
 - Клонировать репозиторий `git clone <адрес вашего репозитория>`
 - перейти в директорию с клонированным репозиторием
 - установить виртуальное окружение `python3 -m venv venv`
 - установить зависимости `pip install -r requirements.txt`
 - в директории /backend/kittygram_backend/ создать файл .env
 - в файле .env прописать Значения переменных SECRET_KEY, DEBUG, ALLOWED_HOSTS в виде: `SECRET_KEY = '<ваш_ключ>', 'DEBUG = FALSE' , ALLOWED_HOSTS = 'localhost 127.0.0.1'
   
## Подключение сервера к аккаунту на GitHub
- на сервере должен быть установлен Git
- если Git не установлен - установить командой `sudo apt install git`
- находясь на сервере сгенерировать пару SSH-ключей командой `ssh-keygen`
- клонировать проект с GitHub на сервер: `git clone git@github.com:Ваш_аккаунт/<Имя проекта>.git`

## Запуск backend проекта на сервере
- Создать виртуальное окружение `sudo apt install python3-pip python3-venv -y`
- находясь в директории с проектом активировать его `python3 -m venv venv`  `source venv/bin/activate` 
- установить зависимости `pip install -r requirements.txt`
- выполнить миграции `python manage.py migrate`

## Запуск frontend проекта на сервере
- установить на сервер `Node.js`   командами
`curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - &&\`
`sudo apt-get install -y nodejs`
- установить зависимости frontend приложения. Из директории `<ваш проект>/frontend/` выполнить команды: `npm install`

## Установка и запуск Gunicorn
установить пакет gunicorn `pip install gunicorn==20.1.0`
- В директории _/etc/systemd/system/ создайте файл _gunicorn.service_  открыв его командой `sudo nano /etc/systemd/system/gunicorn.service` скопировав в него код из файла gunicorn_kittygram.service который можно найти в папке infra

## Установка и настройка Nginx

 - На сервере из любой директории выполнить команду: `sudo apt install nginx -y`
- Для установки ограничений на открытые порты выполнить по очереди команды: `sudo ufw allow 'Nginx Full'`  `sudo ufw allow OpenSSH`
- включить файервол `sudo ufw enable`

### собрать и настроить статику для backend-приложения.
Выполнить команду `python manage.py collectstatic`
- в директории_<имя_проекта>/backend/_ будет создана директория _static_backend/_ 
- Скопировать директорию _static_backend/_ в директорию _/var/www/<имя_проекта>/_
### собрать и разместить статику frontend-приложения.
- Из директории _<имя_проекта>/frontend/_  выполнить команду `npm run build`
- Скопировать директорию _/frontend/build/_ в директорию _/var/www/<имя_проекта>/_
- открыть файл конфигурации веб-сервера `sudo nano /etc/nginx/sites-enabled/default` скопировав в него код из файла default который также можно найти в папке infra.


## Автор
Влад Ермолаев - [GitHub](https://github.com/VladErm91)

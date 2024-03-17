# taski-docker
Отработка деплоя, на внешний сервер, проекта для постановки задач Taski методом CI/CD. При успешном деплое присылается уведомление через Телеграм на созданного бота.

## Использованные технологии:
* Docker
* Telebot
  
## Запуск проекта:
Клонировать репозиторий:
~~~
git clone git@github.com:ConstantineGolovin/taski-docker.git
~~~
Запуск проекта:
~~~
sudo docker compose -f docker-compose.production.yml up
~~~
Зайти в контейнер backend, запустить в нём миграции, собрать статику, создать суперпользователя:
~~~
sudo docker compose -f docker-compose.production.yml exec backend bash
./manage.py makemigrations
./manage.py migrate
./manage.py collectstatic
./manage.py createsuperuser
~~~

## Автор проекта
Головин К.А., 70 когорта

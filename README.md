## Трекер полезных привычек


В проекте реализована бэкенд-часть SPA веб-приложения для напоминания о выполнении привычек с помощью трекера в телеграмме. 
Телеграмм бот каждый раз будет присылать напоминание о выполнении привычки в определенное время, созданное пользователем.



Для запуска проекта необходимо склонировать содержимое репозетория и установить зависимости.
* Создать базу данных
* В файл .env внести данные настроек конфигурации в соответствии с .env_sample
* Для работы, требуется redis
* Создать TelegramBot

### Как установить
Для того чтобы запустить программу, вам нужно будет установить [PostgreSQL](https://www.postgresql.org/download/), во время установки указать пароль для подключения к БД.
А также установить redis и получить Telegram токен
Пароль от БД надо будет указать в файле `.env`, а также имя БД, адрес redis и Telegram токен. Файл можно создать самому или переименовать существующий `.env_sample` в `.env`

Рекомендуется использовать POETRY для изоляции проекта.

Python3.10 уже должен быть установлен,
затем используйте poetry для установки зависимостей

### Как запустить 
Для того чтобы запустить код, в консоли нужно прописать `cd` и название папки, в которой находится проект. После этого нужно прописать `python manage.py runserver`.

Пример запуска:
```
python manage.py runserver
```

Для создания учетной записи администратора (суперпользователя) выполнить следующую команду

    python manage.py csu


Для запуска периодической задачи открыть два терминала и ввести следующие команды.

    celery -A config worker -l INFO
    celery -A config beat -l INFO


С документацией проекта можно ознакомиться по адресу:

    http://127.0.0.1:8000/swagger/
    http://127.0.0.1:8000/redoc/

### Как запустить проект с помощью Docker-compose:

В терминале набираем команду

        docker-compose build

docker-compose build — позволяет обновить образы или создать их заново, если они были изменены;

Далее набираем команду

        docker-compose up

docker-compose up — запускает приложение со всеми контейнеры, информация о которых есть в docker-compose.yml. Если файл
не указан, по умолчанию используется файл в текущем каталоге

Остальные команды для DOCKER которыми вы можете воспользоваться в своем проекте.

        docker-compose restart

Docker-compose restart — перезапускает контейнеры;

        docker-compose logs

Docker-compose logs — выводит журналы состояния;

        docker-compose ps

Docker-compose ps — отображает текущее состояние контейнеров.

        docker-compose down

Docker-compose down — останавливает и удаляет все контейнеры, а также тома, связанные с ними.

        docker-compose start

Docker-compose start — запускает остановленные контейнеры.

        docker-compose stop

Docker-compose stop — останавливает работу запущенных контейнеров без их удаления.

        docker-compose restart

Docker-compose restart — перезапускает контейнеры.

        docker-compose pull

Docker-compose pull — загружает последние версии образов для сервисов, описанных в файле docker-compose.yaml

### Цель проекта
Код написан в образовательных целях.
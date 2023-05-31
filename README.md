склонируйте репорзиторий.

перейдите в папку cd infra.

создайте файл .env, согласно шаблону:

DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
команда docker-compose up разверните проект.

Сделайте миграции, суперпользователя и соберите статику:

docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
Зайдите на (http://localhost/admin/) и убедитесь, что все работает

сервер доступен по http://158.160.55.239/admin/
# Проект YaMDB
![Github actions](https://github.com/Xanssun/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
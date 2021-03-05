Service Yamdb
=================================

In a team with my colleagues we have written service – databases of reviewing films, books, music and
REST API for it. My role included registration and authentication system, access rights, work with a token, e-mail confirmation system, fields.


Tech stack: Python3, Django Rest Framework, HTML, HTTP, HTTPS, PostgreSQL, Gunicorn, Docker, Postman, Linux, Visual Studio Code.

Getting Started
===============

1. You can build it in steps:
    1. ``cd ...wherever...``
    2. ``git clone https://github.com/volhadounar/infra_sp2.git``
    3. ``cd infra_sp2``
    4. ``docker-compose up``
    5. Open another command window.
    6. ``docker-compose run web python manage.py migrate`` -- Reads all the migrations folders in the application folders and creates / evolves the tables in the database
    7. ``docker-compose exec web python manage.py createsuperuser``
    8. ``docker-compose exec web python manage.py loaddata fixtures.json`` -- Uploads fixtures file with web-service' data
2. The usage:
    1. There you can read the documentation: http://localhost:8000/redoc/
    2. http://localhost:8000/admin -- Visit admin page to create items as admin
    3. Try e-mail confirmation system:
        - In Postman make put request with body {"email":"some_email"} using:
        http://localhost:8000/api/v1/auth/email/
        - Find confirmation code in the folder 'sent_emails'. Use it in the next step.
        - Make the put request with body {"email":"some_mail", "confirmation_code": "some_confcode_from_email"}: http://localhost:8000/api/v1/auth/token/
        - Input token in the request headers: `Authorization: Bearer <token>`
        - http://localhost:8000/api/v1/users/me/ -- Fetch current profile data

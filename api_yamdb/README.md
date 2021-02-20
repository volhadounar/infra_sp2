Service Yamdb
=================================

A service – databases of reviewing films, books, music and REST API for it( is made in a team with my
colleagues)
Tools:  Django Rest Framework, ModelViewSet, routers, JSON Web Token, Authorization, Users Roles,
Postman.

Getting Started
===============

1.  You can build it in steps:
    1.  ``cd ...wherever...``
    2.  ``git clone https://github.com/volhadounar/api_yamdb.git``
    3.  ``cd api_yamdb``
    4.  ``pip install -r requirements.txt``  -- Should install everything you need
    5.  ``python3 manage.py migrate`` -- Reads all the migrations folders in the application folders and creates / evolves the tables in the database
    6.  ``python3 manage.py createsuperuser`` 
    7.  ``python3 manage.py runserver`` -- Running localy
    8.  And visit http://127.0.0.1:8000
    9.  http://127.0.0.1:8000/admin visit admin page to create items as admin

2. Build docker image:
    1. ``cd api_yamdb``
    2. ``docker-compose up``
    3. open another command window
    4. ``docker-compose run web python manage.py migrate``
    5. ``docker exec -it container_id python manage.py createsuperuser``
    6. http://127.0.0.1:8000/admin visit admin page to create items as admin
    7. ``docker exec -it container_id python manage.py dumpdata > fixtures.json`` -- upload fixtures file with creates data

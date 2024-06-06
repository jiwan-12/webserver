***Django project structure for Web Application***

***Django version: Django==5.0.6***

Please follow the following folder structure for the django project

    webserver/
    ├── deployments/                        # Isolate Dockerfiles and docker-compose files here.
    │   ├── Dockerfile
    │   ├── Dockerfile_dev
    │   ├── Dockerfile_prod
    │   └── docker-compose.yml
    ├── docs/
    │   ├── CHANGELOG.md
    │   ├── CONTRIBUTING.md
    │   ├── deployment.md
    │   ├── local-development.md
    │   └── schema.yml
    ├── local_db/ 
    ├── locale/ 
    ├── logs/ 
    ├── media/
    ├── webserver/
    │   ├── apps/
    │   │   ├── authentication/                 # A django rest app
    │   │   │   ├── auth_apis/
    │   │   │   │   ├── google_auth/            # Only the "presentation" layer exists here.
    │   │   │   │   │   ├── __init__.py
    │   │   │   │   │   ├── serializers.py
    │   │   │   │   │   ├── urls.py
    │   │   │   │   │   └── views.py
    │   │   │   │   ├── microsoft_auth/         # Only the "presentation" layer exists here.
    │   │   │   │   │   ├── __init__.py
    │   │   │   │   │   ├── serializers.py
    │   │   │   │   │   ├── urls.py
    │   │   │   │   │   └── views.py
    │   │   │   │   └── __init__.py
    │   │   │   ├── fixtures/                   # Constant "seeders" to populate your database
    │   │   │   ├── management/
    │   │   │   │   ├── commands/               # Try and write some database seeders here
    │   │   │   │   │   ├── __init__.py
    │   │   │   │   │   └── command.py
    │   │   │   │   └── __init__.py
    │   │   │   ├── migrations/
    │   │   │   │   └── __init__.py
    │   │   │   ├── templates/            # App-specific templates go here
    │   │   │   ├── tests/                # All your integration and unit tests for an app go here.
    │   │   │   │   ├── __init__.py
    │   │   │   │   └── test_app1_name.py
    │   │   │   ├── __init__.py
    │   │   │   ├── admin.py
    │   │   │   ├── apps.py
    │   │   │   ├── models.py
    │   │   │   ├── services.py          # Your business logic and data abstractions go here.
    │   │   │   ├── urls.py
    │   │   │   └── views.py
    │   │   ├── discovery/               # A django rest app same as google_auth structure
    |   |   ├── chat/                    # A django rest app same as google_auth structure
    │   │   └── core/                    # A django rest core same as app1 structure plus following files
    │   │       ├── constants.py
    │   │       ├── exceptopns.py
    │   │       └── helpers.py
    │   ├── common/                      # An optional folder containing common "stuff" for the entire project
    │   │   ├── __init__.py
    │   │   ├── common.py
    │   │   ├── constants.py
    │   │   ├── generics.py
    │   │   ├── helpers.py
    │   │   ├── mixins.py
    │   │   ├── models.py
    │   │   └── serializers.py
    │   └── config/
    │       ├── settings
    │       │   ├── __init__.py
    │       │   ├── development.py
    │       │   ├── production.py
    │       │   └── staging.py
    │       ├── __init__.py
    │       ├── asgi.py
    │       ├── urls.py
    │       └── wsgi.py
    ├── requirements/
    │   ├── common.txt              # Same for all environments
    │   ├── development.txt         # Only for a development server
    │   ├── local.txt               # Only for a local server (example: docs, performance testing, etc.)
    │   ├── production.txt          # Production only
    │   └── requirements-dev.txt 
    │   └── requirements.txt 
    ├── scripts/                    # Your script files
    │   └── entrypoint.sh           # Any bootstrapping necessary for your application
    ├── static/                     # Your static files
    │   ├── css/
    │   ├── images/
    │   └── js/
    ├── .dockerignore
    ├── .env
    ├── .env.example                # An example of your .env configurations. Add necessary comments.
    ├── .flake8
    ├── .gitignore                  # https://github.com/github/gitignore/blob/main/Python.gitignore
    ├── LICENSE
    ├── manage.py               
    ├── Pipfile
    ├── Pipfile.lock
    ├── pyproject.toml
    ├── pytest.ini
    ├── README.md
    ├── setup.cfg
    ├── setup.py
    └── tox.ini

1. **Project Folder**:
   - This is the root folder of your Django project.

2. **manage.py**:
   - This script is used to interact with your Django project via command line. It allows you to run administrative tasks, manage your project, and more.

3. **Project Config Folder**:
   - This folder contains the configuration settings for your Django project.

4. **settings.py**:
   - Configuration settings for your Django project such as database settings, static files configuration, middleware settings, etc.

5. **urls.py**:
   - This file contains URL patterns for your project. It maps URL paths to view functions or classes.

6. **wsgi.py** and **asgi.py**:
   - Entry points for WSGI (Web Server Gateway Interface) and ASGI (Asynchronous Server Gateway Interface) servers respectively. They provide the interface between your Django application and the web server.

7. **Apps**:
   - Django projects are composed of reusable apps. Each app can have its own models, views, templates, and URL patterns.

   - **auth_app**:
     - This is an example of a Django app within the project. It could be named according to its functionality, such as `users`, `products`, `blog`, etc.
     - **models.py**:
       - Contains the database models for this specific app.
     - **views.py**:
       - Contains the views (controller logic) for this app.
     - **urls.py**:
       - Contains URL patterns specific to this app.
     - **templates**:
       - Folder for HTML templates specific to this app.
     - **static**:
       - Folder for static files (CSS, JavaScript, images) specific to this app.
     - **forms.py**:
       - Contains forms specific to this app.
     - **admin.py**:
       - Register app models to the Django admin interface.

   - **discovery**:
     - Another example of a Django app within the project, similar to App1.
     - Follows the same structure with its own `models.py`, `views.py`, `urls.py`, `templates`, `static`, `forms.py`, `admin.py`, etc.

8. **Migrations**:
   - Django's migration system manages changes to your models and propagates those changes into your database schema. Migrations are Python files stored in the `migrations` directory of each app.

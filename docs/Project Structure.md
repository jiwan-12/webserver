*** Django project structure for webapp ***
    webserver/
    ├── manage.py
    ├── webserver/
    │   ├── __init__.py
    │   ├── asgi.py
    │   ├─ settings.py
    │   ├─ urls.py
    │   ├── wsgi.py
    ├── auth_app/
        ├── migrations/
        │   └── __init__.py
        ├── __init__.py
        ├── admin.py
        ├── apps.py
        ├── models.py
        ├── tests.py
        ├── urls.py
        └── views.py

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

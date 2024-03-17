# DJANGO

I hate this.

## DJANGO
- ### Getting Started
    ```django-admin startproject name_of_the_project```
    
    ```python manage.py runserver```    

    ```python manage.py startapp name_of_app```

- ### Template Inheritance
  Allows us to make a template which we can use in html files.
  ```
  #Template for simple html page present at tasks/layout.html
  <!doctype html>
  <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport"
              content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Tasks</title>
    </head>
    <body>
        {% block body %}
        {% endblock %}
    </body>
  </html>
  ```
    
  To use this template in other html pages.
  ```
  {% extends "tasks/layout.html" %}
  {% block body %}
    <h1>Test</h1>
  {% endblock %}
  ```
    
- ### Link
  Allows us to navigate to other pages using name given to urls in urls.py file.
  ```
  <a href="{% url 'name_of_url' %}">Test</a>
  ```
- ### Name Collision
  Happens when multiple apps have same name of urls.
  To solve this we can uniquely identify each apps urls by adding:
  ```
  app_name="app_name"
  url_patterns=[
    path("", views.index,name=index)
  ]
  ```
  In urls.py file, now all urls of this app can be accessed as:
  ```app_name:index```
- ### Forms
  
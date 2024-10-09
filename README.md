# Eventmanager


## Backend setup:

Initialize new venv
- python -m venv project-venv

Install requirements (only after generating virtual environment)
- pip install -r requirements.txt

Start venv<sup>windows</sup>
- project-venv\Scripts\activate

setup Django
- pip install django djangorestframework django-cors-headers requests

Create backend project
- django-admin startproject django_backend

Test if everything works<sup>windows</sup>
- python django_backend/manage.py runserver

Create backend app (No clue if we need this)
- python manage.py startapp testApp

> Projects vs. apps
> What’s the difference between a project and an app? An app is a web application that does something – e.g., a blog system, a database of public records or a small poll app. A project is a collection of configuration and apps > for a particular website. A project can contain multiple apps. An app can be in multiple projects.
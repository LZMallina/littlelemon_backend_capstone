# Meta Backend Certification Module 8: Capstone project

## Week 1: Setting up the environment

* Install VS code https://code.visualstudio.com/Download
* Install Python
https://www.python.org/downloads/
* Install Git

## Setup virtual environment with pipenv

$ pip3 install pipenv

$ pipenv //-> check if virtual environment installed

$ pipenv shell //-> activate virtual environment

## Install django

$ pipenv install django

$ django-admin startproject littlelemon .

* Go to Pipfile inside the main directory and update the package dependencie:

[packages]
django = "*"
djangorestframework = "*"
djangorestframework-xml = "*"
djoser = "*"

$ python manage.py startapp restaurant

$ python manage.py runserver //--> to ensure django and virtual environment setup

ctrl+C //--> exit server

## Connect to MySQL

$ pipenv install mysqlclient //--> adds mysqlclient as dependency

$ pipenv install //--> update all dependencies

* Log into MySQL command line

$ CREATE DATABASE reservations;

$ SHOW DATABASES;

## Configurate settings.py

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME':'reservations',
        'HOST':'127.0.0.1',
        'PORT':'3306',
        'USER':'admindjango',
        'PASSWORD':'employee@123!',
    }
}
INSTALLED_APPS =[
    'restaurant'
]

## Ensure MySQL is properly connected to the django app

$ python manage.py makemigrations

$ python manage.py migrate

* Log into MySQL command line

$ SHOW DATABASE;

$ USE reservations;

$ show tables;

$ describe restaurant_booking;

$ exit; //--> exit MySQL

# Meta Backend Certification Module 8: Capstone project

## Week 1: Setting up the environment

* Install VS code https://code.visualstudio.com/Download
* Install Python
https://www.python.org/downloads/
* Install Git

### Setup virtual environment with pipenv

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

## Week 2: Django database configuration and Models
### Connect to MySQL

$ pipenv install mysqlclient //--> adds mysqlclient as dependency

$ pipenv install //--> update all dependencies

### Configurate settings.py

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME':'littlelemon',
        'HOST':'127.0.0.1',
        'PORT':'3306',
        'USER':'root',
        'PASSWORD':'',
        'OPTIONS':{
            'init_command':"SET sql_mode ='STRICT_TRANS_TABLES'"
        }
}
INSTALLED_APPS =[
    'restaurant'
]

### Access MySQL through VS Code

* Install MySQL extension from VS Code extension marketplace: MySQL by Jun Han

$ python manage.py makemigrations
$ python manage.py migrate

* MySQL should be on the VS code explorer menu.  Click + to get access to database LittleLemon.
### Create Database and Connect to MySQL through MySQL command line

* Log into MySQL command line

$ CREATE DATABASE database_name;

$ SHOW DATABASES;

$ USE database_name;

$ show tables;

$ describe table; //--> see details of the table

* Create user for the database;

$ CREATE USER 'admindjango'@'localhost' IDENTIFIED BY 'employee@123!' ;

$ SELECT user FROM mysql.user //--> to ensure your user has been created

$ GRANT ALL ON *.* TO 'admindjango'@'localhost';

$ FLUSH PRIVILEGES; //--> update the user's access to all tables

$ exit; //--> exit MySQL

* Update settings.py with correct user and password;

## Setting up models: Booking and Menu

## Register Booking and Menu on admin.py, then access admin on browser

$ python manage.py createsuperuser
Username: admin
email address: admin@littlelemon.com
password: LittleLemon123!

$ python manage.py runserver

* go to server /admin, then login
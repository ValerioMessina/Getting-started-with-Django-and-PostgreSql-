# Getting started with Django and PostgreSql 
### using Docker and Docker Compose

A Simple development enviroment of Django and Postgresql using Docker and Docker Compose.

###  Stack 
| Service name | Service version |
| ------------ | ------------- |
| Django          | Latest      |
| PostgreSql    | Latest      |


##### How to run it 
```
# 1. Clone this repo.

# 2. Change to the root of your project directory.
# Initializing Django application.
sudo docker-compose run web django-admin startproject test .

# Go to ./test/settings.py and replace 

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

# With  

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'PASSWORD': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
}

# Creating images 
 docker-compose up

# To shutdown all services 
 docker-compose down
 or
 Ctrl + C 
 ```


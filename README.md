# The Simple Guide to Django

_Django explained simply._

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/siowyisheng/simple-django/blob/master/LICENSE) ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

## Table of Contents <!-- omit in toc -->

- [What is Django?](#what-is-django)
- [What is a Django project?](#what-is-a-django-project)
- [What is a Django app?](#what-is-a-django-app)
- [What are models?](#what-are-models)
- [What is the admin site?](#what-is-the-admin-site)
- [What are views?](#what-are-views)
- [What is a field?](#what-is-a-field)
- [What are migrations?](#what-are-migrations)
- [What are templates?](#what-are-templates)
- [What are generic views?](#what-are-generic-views)
- [What is Mezzanine?](#what-is-mezzanine)
- [How do I deploy?](#how-do-i-deploy)
- [How to reference URLs?](#how-to-reference-urls)
- [How are URLs directed to views?](#how-are-urls-directed-to-views)
- [TODO](#todo)

## What is Django?

## What is a Django project?

Start a project:

```bash
$ ./manage.py startproject myproject
```

## What is a Django app?

One part of a project, which provides one or more features.

Start an app:

```bash
$ ./manage.py startapp myapp
```

Add an app to a project:

```python
INSTALLED_APPS = [
    'myapp',
]
```

## What are models?

A definition of each type of your stored data, its fields and behaviors. Each model maps to a single database table.

Each field is an instance of some `Field`, and maps to a database column. The different type of `Field` determines what data to store in the database. Some common field are `CharField`, `BooleanField`, `DateTimeField`, `DecimalField`, `EmailField`, `FileField`, `ImageField`, `IntegerField`, `SlugField`, `TextField`.

`ForeignKey`, `ManyToManyField` are special fields which represent relations to other models.

The database table name is **myapp_mymodel**. An auto-incrementing ID field is added for each model.

Define a model:

```python
from django.db import models

class Musician(models.Model):
    first_name = models.CharField(max_length=50)
    last_name = models.CharField(max_length=50)
    instrument = models.CharField(max_length=100)
```

## What is the admin site?

## What are views?

## What is a field?

An attribute of a model, which maps to a database column.

Fields can have

## What are migrations?

Create and sync migrations with the database:

```bash
$ ./manage.py makemigrations
$ ./manage.py migrate
```

## What are templates?

## What are generic views?

## What is Mezzanine?

## How do I deploy?

Run this to check if your settings are ready for production.

```bash
$ ./manage.py check --deploy
```

## How to reference URLs?

Use `reverse` and `redirect`.

## How are URLs directed to views?

https://docs.djangoproject.com/en/2.1/topics/http/urls/#how-django-processes-a-request

By default it looks for matches to mappings in `urlpatterns` in `urls.py`.

## TODO

```bash
$ django-admin startproject
$ ./manage.py startapp
$ ./manage.py createsuperuser
$ ./manage.py runserver
$ ./manage.py makemigrations
$ ./manage.py makemigrations YOUR_APP_LABEL
$ ./manage.py migrate
$ ./manage.py collectstatic
$ ./manage.py shell
$ ./manage.py shell_plus
```

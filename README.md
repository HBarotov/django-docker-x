> A boilerplate for quick prototyping Django projects on Docker

## Features

- Django 5.0 & Python 3.10
- Database on Docker with [Postgres](https://www.postgresql.org/)
- Install via [Docker](https://www.docker.com/)
- Custom User [model](https://docs.djangoproject.com/en/5.0/topics/auth/customizing/)
- Debugging with [django-debug-toolbar](https://github.com/jazzband/django-debug-toolbar)

## Table of Contents

* [Rationale](#rationale)
* [Installation](#installation)
* [Configuration](#configuration)
* [License](#license)

## Rationale

As a learner of Django, I build/prototype a lot of toy projects. I always find myself setting up the same infrastructure within Docker over and over, which takes around 15-30 minutes. I decided to build this boilerplate for such prototyping. It has no assumptions; the boilerplate is nothing like [Cookiecutter](https://github.com/cookiecutter/cookiecutter). It is deliberately simple.

Here is the boilerplate that I became accustomed to and use in every toy project. It is largely based on this [repo](https://github.com/testdrivenio/django-on-docker).

## Installation

django-docker-x can be installed via Docker. However, it is recommended to create a virtual environment to work more easily. To start, clone the repo to your local computer and change into the proper directory.

```
$ git clone https://github.com/HBarotov/django-docker-x.git
$ cd django-docker-x
```

### Pip

```
$ python -m venv .venv

# Windows
$ Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
$ .venv\Scripts\Activate.ps1

# macOS
$ source .venv/bin/activate

(.venv) $ pip install -r requirements.txt
(.venv) $ python manage.py migrate
(.venv) $ python manage.py createsuperuser
(.venv) $ python manage.py runserver
# Load the site at http://127.0.0.1:8000
```

### Docker

Build docker images, run containers, execute commands.

```
$ docker-compose up -d --build
$ docker-compose exec web python manage.py createsuperuser
# Load the site at http://127.0.0.1:8000
```

## Configuration

This project requires almost no configuration. Currently, the `.env.dev` and `.env.dev.db` files are in source control. In case you need to remove them, create your own `.env` files in the root directory next to `docker-compose.yml` and add them to the `.gitignore`. Then, update the `docker-compose.yml` file to point to your `.env` files.

## License
I will choose soon.

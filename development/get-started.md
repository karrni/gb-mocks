# Get Started

## Prerequisites

* [Python 3.10](https://www.python.org/downloads/)
* [Python Poetry](https://python-poetry.org/docs/#installation)
* [Git](https://git-scm.com/downloads)
* Access to the GitHub project (contact David Ziegelwanger)

## Setup

Clone the repository and install the requirements using Poetry:

```bash
git clone git@github.com:karrni/mocks.git
cd mocks
poetry install
```

Install the pre-commit hooks that run code formatters when committing new changes:

```bash
poetry shell
pre-commit install
```

## Configuration

Just like a normal configuration, Mocks still needs to be configured via environment variables. Use the `.env.example` file as a reference.

## Running

Django applications are managed using `manage.py`. The official documentation:

{% embed url="https://docs.djangoproject.com/en/4.0/ref/django-admin/" %}

Apply the database migrations, load initial data, and create a superuser:

```bash
poetry shell
python manage.py migrate
python manage.py loaddata initial
python manage.py createsuperuser
```

Now start the testserver by running:

```bash
python manage.py runserver
```

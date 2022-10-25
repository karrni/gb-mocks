# Entwicklung \[OLD]

## Überblick

Mocks ist eine in [Python 3.10](https://www.python.org/downloads/release/python-3100/) geschriebene [Django 4.0](https://docs.djangoproject.com/en/4.0/) Webanwendung und verwendet [Poetry](https://python-poetry.org/) zur Verwaltung der Abhängigkeiten. Zusätzlich werden [flake8](https://flake8.pycqa.org/), [black](https://black.readthedocs.io/) und [isort](https://pycqa.github.io/isort/) in Kombination mit [pre-commit](https://pre-commit.com/) verwendet, um einen einheitlichen Coding Style zu erreichen.

Das Frontend besteht aus [Django-Templates](https://docs.djangoproject.com/en/4.0/topics/templates/) und verwendet [HTMX](https://htmx.org/) für AJAX, damit sämtliches HTML serverseitig gerendert werden kann. Als CSS-Framework wird [Bootstrap 5.2](https://getbootstrap.com/docs/5.2/getting-started/introduction/) verwendet und eigene Styles werden als SCSS geschrieben und mit [SASS](https://sass-lang.com/) kompiliert.

Die Installation erfolgt mittels [Docker](https://www.docker.com/) und [docker-compose](https://docs.docker.com/compose/). Der WSGI-Server ist [Gunicorn](https://gunicorn.org/) und [nginx](https://www.nginx.com/) wird als Reverse Proxy verwendet.

## Entwicklungsumgebung







[Python 3.10](https://www.python.org/downloads/)

[Poetry](https://python-poetry.org/docs/#installation)

[Git](https://git-scm.com/download/win)









## Entwicklungsumgebung

### Voraussetzungen

* Python 3.10
* Pip
  * Poetry - `pip install poetry`
* Git

### Setup

Klonen und Installieren des Projekts:

```
git clone <MOCKS>
cd <MOCKS>
poetry install
```

{% hint style="info" %}
Poetry installiert Packages in virtuelle Environments. Mittels poetry shell kann eine Shell im aktuellen Environment gestartet werden.
{% endhint %}

Als nächste müssen die pre-commit Hooks installiert werden:

```
poetry shell
pre-commit install
```

### Konfiguration

Mocks wird mithilfe von Umgebungsvariablen konfiguriert. Diese können in der .env Datei angegeben werden. Die .env.example Datei kann als Referenz verwendet werden.

{% hint style="info" %}
Beim lokalen Testen werden keine separaten Datenbank- oder Webserver gestartet. Das passiert nur beim Deployment mittels docker-compose.
{% endhint %}

### Starten

Django Anwendungen werden mittels manage.py verwaltet. Siehe hierzu:

{% embed url="https://docs.djangoproject.com/en/4.0/ref/django-admin/" %}

Zu Beginn muss die Datenbank bespielt und ein Superuser angelegt werden:

```bash
python manage.py migrate
python manage.py loaddata initial
python manage.py createsuperuser
```

Danach kann der Testserver gestartet werden:

```
python manage.py runserver
```






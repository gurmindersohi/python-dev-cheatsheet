# 🐍 Python Enterprise Commands & Setup Guide

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-4.0-green?logo=django)](https://www.djangoproject.com/)
[![Flask](https://img.shields.io/badge/Flask-2.0-lightgrey?logo=flask)](https://flask.palletsprojects.com/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-teal?logo=fastapi)](https://fastapi.tiangolo.com/)
[![Docker](https://img.shields.io/badge/Docker-Enabled-blue?logo=docker)](https://www.docker.com/)

A curated collection of **enterprise-level Python commands** for setting up environments, managing dependencies, running popular frameworks (Django, Flask, FastAPI), testing, linting, Docker, and deployment.  

This repo serves as a **developer quick reference**. 🚀

---

### 📑 Table of Contents
1. [Virtual Environment & Package Management](#-virtual-environment--package-management)  
2. [Django](#-django)  
3. [Flask](#-flask)  
4. [FastAPI + Uvicorn](#-fastapi--uvicorn)  
5. [Testing & Linting](#-testing--linting)  
6. [Database](#-database-common-commands)  
7. [Docker](#-docker-python-apps-in-containers)  
8. [Poetry](#-poetry-enterprise-dependency-manager)  
9. [Deployment](#-deployment-production-servers)  
10. [Contributing](#-contributing)  
11. [License](#-license)  

---

### 📦 Virtual Environment & Package Management
```bash
python3 -m venv .venv                 # Create virtual environment

source .venv/bin/activate             # Activate (Linux/Mac)

.venv\Scripts\Activate                # Activate (Windows)

pip list                              # List installed libraries

pip freeze > requirements.txt         # Generate requirements.txt

pip install -r requirements.txt       # Install from requirements.txt

pip install --upgrade pip             # Upgrade pip

pip freeze | xargs pip uninstall -y   # Uninstall all libraries

rm -rf .venv/                         # Delete venv (Linux/Mac)

rmdir /s /q .venv                     # Delete venv (Windows)
```

---

### 🌐 Django
```bash
pip install django                    # Install Django

django-admin startproject projectname # Start new project

python manage.py startapp appname     # Start new app

python manage.py migrate              # Apply migrations

python manage.py makemigrations       # Create migrations

python manage.py runserver            # Run dev server

python manage.py runserver 8080       # Run on custom port

python manage.py createsuperuser      # Create superuser

python manage.py collectstatic        # Collect static files

python manage.py test                 # Run tests
```

---

### 🌐 Flask
```bash
pip install flask                     # Install Flask

export FLASK_APP=app.py               # Set app (Linux/Mac)

flask run                             # Run Flask app

export FLASK_ENV=development          # Debug mode (Linux/Mac)

flask run                             # Run in debug
```

---

### ⚡ FastAPI + Uvicorn
```bash
pip install fastapi uvicorn           # Install FastAPI + Uvicorn

uvicorn main:app --reload             # Run FastAPI app

uvicorn main:app --host 0.0.0.0 --port 8080  # Run with host/port
```

---

### 🧪 Testing & Linting
```bash
pip install pytest flake8 black       # Install testing & linting tools

pytest                                # Run all tests

pytest -v                             # Run with detailed output

pytest tests/test_users.py            # Run specific test

flake8 .                              # Run linting

black .                               # Auto-format code
```

---

### 🗄️ Database (Common Commands)
```bash
pip install psycopg2-binary           # PostgreSQL client

pip install mysqlclient               # MySQL client

alembic revision --autogenerate -m "init"   # Alembic migration

alembic upgrade head                  # Apply migration
```

---

### 🐳 Docker (Python Apps in Containers)
```bash
docker build -t myapp:latest .        # Build image

docker run -p 8000:8000 myapp:latest  # Run container

docker stop $(docker ps -aq)          # Stop all containers

docker rm $(docker ps -aq)            # Remove all containers

docker rmi $(docker images -q)        # Remove all images
```

---

### 📜 Poetry (Enterprise Dependency Manager)
```bash
pip install poetry                    # Install Poetry

poetry init                           # Initialize project

poetry install                        # Install dependencies

poetry add requests                   # Add dependency

poetry run python main.py             # Run script in Poetry venv
```

---

### 🚀 Deployment (Production Servers)
```bash
python manage.py migrate --noinput    # Run migrations (CI/CD)

python manage.py collectstatic --noinput # Collect static files

pip install gunicorn                  # Install Gunicorn

gunicorn projectname.wsgi:application --bind 0.0.0.0:8000

pip install "uvicorn[standard]" gunicorn

gunicorn -k uvicorn.workers.UvicornWorker main:app --bind 0.0.0.0:8000
```

---

### 🤝 Contributing

### Contributions are welcome!
If you have useful Python commands, deployment tricks, or enterprise tips, feel free to open a pull request.

---

### 📜 License
This project is licensed under the MIT License – feel free to use, modify, and share.
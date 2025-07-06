# Kanhaiya-Lal-Bohra-Python-Development-internship
It is an internship assignment
Django Internship Assignment
Overview
This Django project demonstrates backend development skills with Django REST Framework (DRF), authentication, Celery, and Telegram bot integration. It includes public and protected API endpoints, a welcome email task, and Telegram username storage.
Tech Stack

Framework: Django, Django REST Framework
Task Queue: Celery with Redis
Bot: Python-telegram-bot
Database: PostgreSQL (local setup)

Setup Instructions

Clone the repository:git clone https://github.com/yourusername/django-intern-assignment.git
cd django-intern-assignment


Install dependencies:pip install -r requirements.txt


Configure environment variables:
Create a .env file based on the example provided.
Update secrets (e.g., SECRET_KEY, TELEGRAM_BOT_TOKEN).


Set up PostgreSQL:
Create a database named intern_db.
Update DB_USER, DB_PASSWORD, etc., in .env.


Apply migrations:python manage.py migrate


Start Redis (for Celery):
Ensure Redis is running locally (redis-server).


Run the Django server:python manage.py runserver


Run Celery worker:celery -A django_intern worker -l info


Run Telegram bot (in a separate terminal):python app/telegram_bot.py



Environment Variables

SECRET_KEY: Django secret key
DEBUG: Set to False for production
ALLOWED_HOSTS: Comma-separated hostnames
DB_NAME, DB_USER, DB_PASSWORD, DB_HOST, DB_PORT: Database credentials
TELEGRAM_BOT_TOKEN: Telegram bot token from BotFather
DEFAULT_FROM_EMAIL, EMAIL_HOST_USER, EMAIL_HOST_PASSWORD: Email settings

API Documentation

GET /api/public/: Public endpoint returning a welcome message.
GET /api/protected/: Protected endpoint (requires Token Authentication).
POST /api-token-auth/: Login to get authentication token (e.g., {"username": "user", "password": "pass"}).

Notes

Replace placeholder values in .env with actual credentials.
Ensure Telegram bot is created and token is obtained from BotFather.
No deployment is required; focus is on local setup and code quality.

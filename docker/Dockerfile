FROM python:3.7-buster

COPY append-settings.py /install/

RUN \
    apt-get update && \
    apt-get install -y --no-install-recomends \
        git && \
    git clone https://github.com/vitorfs/bootcamp && \
    cd bootcamp && \
    pip install -r requirements/local.txt && \
    pip install django-seed && \
    # Prep the repo
    mv env.example .env && \
    cat /install/append-settings.py >> config/settings/local.py && \
    python manage.py seed --number=15
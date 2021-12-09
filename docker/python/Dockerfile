FROM python:3.9.6-alpine

WORKDIR /usr/src/app

RUN mkdir /usr/src/app/static
RUN mkdir /usr/src/app/media

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apk update \
    && apk add postgresql-dev gcc python3-dev musl-dev

RUN pip install --upgrade pip

COPY . /docker/python/

# RUN pip uninstall django

RUN pip install -r /docker/python/requirements.txt

RUN pip install virtualenv

COPY . /application

# ENTRYPOINT ["/usr/src/app/entrypoint.sh"]
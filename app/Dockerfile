#pull official base image
FROM python:3.8.3-alpine

#set work directory
WORKDIR /usr/src/app

# set environment varriable
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONBUFFERED 1

# install psycopg2 dependencies
RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev

# install dependencies
RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

# copy entrypoint.sh
COPY ./entrypoint.sh .

# copy project
COPY  . .

# run entrypoint.ch
ENTRYPOINT [ "/usr/src/app/entrypoint.sh" ]
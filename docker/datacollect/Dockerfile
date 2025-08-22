FROM python:slim-trixie

ENV database=crypto-executor
ENV host=localhost
ENV user=executor
ENV password=123456
ENV port=5432

MAINTAINER Aureliano Sinatra "sinaure@gmail.com"
RUN apt-get update -y && apt-get install -y build-essential postgresql-server-dev-all

WORKDIR /app

ADD docker/datacollect/requirements.txt .

ENV LC_ALL C.UTF-8
ENV LC_CTYPE C.UTF-8

RUN pip3 install -r requirements.txt
COPY docker/datacollect/scripts .
CMD ["python3", "/app/datacollect.py"]

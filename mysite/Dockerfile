FROM python:3.6

MAINTAINER Aadesh

ADD . /usr/src/app

WORKDIR /usr/src/app

COPY requirements.txt ./

RUN pip3 install --no-cache-dir -r requirements.txt

EXPOSE 80

CMD exec gunicorn mysite.wsgi:application --bind 0.0.0.0:80 --workers 3

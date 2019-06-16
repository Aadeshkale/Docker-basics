FROM aadeshkale/welcome_project:test_flex

MAINTAINER Aadesh

ADD . /usr/src/app

WORKDIR /usr/src/app

COPY requirements.txt ./

RUN pip3 install --no-cache-dir -r requirements.txt

EXPOSE 8080

CMD exec gunicorn welpro.wsgi:application --bind 0.0.0.0:8080 --workers 3


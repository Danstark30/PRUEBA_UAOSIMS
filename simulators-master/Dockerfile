FROM python:3.8

RUN apt-get -y update

ENV PYTHONUNBUFFERED 1

COPY . /app/

WORKDIR /app/

RUN pip install -r requirements.txt
RUN pip install gunicorn

RUN python manage.py collectstatic --clear --noinput

EXPOSE 8000

CMD gunicorn myproject.wsgi:application --bind 0.0.0.0:$PORT

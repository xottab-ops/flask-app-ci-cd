FROM python:3.10-slim

WORKDIR /app

COPY . /app/

RUN pip install -r requirements.txt && pip install -r requirements-server.txt

RUN flask db upgrade && python seed.py

EXPOSE 8000

CMD ["gunicorn", "app:app", "-b", "0.0.0.0:8000"]

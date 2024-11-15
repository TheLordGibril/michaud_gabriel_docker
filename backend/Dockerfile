FROM python:3.9-slim

WORKDIR /app

RUN apt-get update && apt-get install -y netcat-openbsd && apt-get clean

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

ENV FLASK_APP=application.py
ENV FLASK_RUN_HOST=0.0.0.0
ENV DEBUG=1

COPY wait-for-it.sh .
RUN chmod +x wait-for-it.sh

EXPOSE 5000

# CMD ["flask", "run"]
CMD ["sh", "-c", "./wait-for-it.sh db 3306 -- flask db upgrade && flask run --host=0.0.0.0 --port=5000"]


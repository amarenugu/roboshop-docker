FROM python:3.9
WORKDR /app
COPY requirement.txt .
COPY payment.ini .
COPY payment.py .
COPY rabbitmq.py .
RUN pip3 install -r requirements.txt
EXPOSE 8080
CMD ["uwsgi", "--ini", "payment.ini"]
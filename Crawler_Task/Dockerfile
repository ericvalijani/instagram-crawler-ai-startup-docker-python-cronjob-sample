FROM python:3.10.8

RUN apt-get update && apt-get -y install cron vim

WORKDIR /usr/src/app

RUN pip3 install requests
COPY requirements.txt requirements.txt
RUN pip3 install --no-cache-dir -r requirements.txt

COPY crontab /etc/cron.d/crontab
RUN chmod 0644 /etc/cron.d/crontab
RUN /usr/bin/crontab /etc/cron.d/crontab

COPY . .
RUN echo $PYTHONPATH

# run crond as main process of container
CMD ["cron", "-f"]

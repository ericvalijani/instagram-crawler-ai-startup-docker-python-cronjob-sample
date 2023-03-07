FROM python:3.10.8

WORKDIR /usr/src/app
#EXPOSE 8501
#EXPOSE 47017

RUN pip install --upgrade pip
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

RUN apt update
RUN apt install -y vim
COPY . .

#CMD [ "python", "./main.py" ]
ENTRYPOINT ["streamlit", "run"]

CMD ["main.py"]

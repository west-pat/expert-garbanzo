FROM redislabs/redismod:latest

RUN apt-get update &&\
    apt-get install -y python python3-pip python3-setuptools python3-distutils curl &&\
    apt clean

RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py &&\
    python3 get-pip.py

RUN echo never > /etc/rc.local

COPY ./ /redis

RUN pip install --upgrade pip

RUN pip install -r /redis/requirements.txt 

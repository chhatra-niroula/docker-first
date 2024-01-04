FROM ubuntu:22.04
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

#install python 3 
RUN apt-get update && apt-get install -y python3 python3.10-venv python3-pip


#CMD ["/usr/bin/python3", "-m", "venv", "/opt/venv/bin"]
RUN /usr/bin/python3 -m venv /opt/venv/bin
# Enable venv
ENV PATH="/opt/venv/bin:$PATH"

WORKDIR /usr/src/app
COPY ./requirements.txt /usr/src/app
RUN pip install -Ur requirements.txt

COPY . /usr/src/app

CMD ["/usr/bin/python3", "/usr/src/app/api.py"]


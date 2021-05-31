FROM ubuntu:18.04
ADD requirements.txt /tmp/
RUN /bin/bash -c 'DEBIAN_FRONTEND=noninteractive apt update;\
	apt -y install python-all python-pip'
WORKDIR /tmp
RUN pip install -qr requirements.txt
RUN mkdir /opt/webapp
ADD Procfile /opt/webapp/
ADD app.py /opt/webapp/
ADD tests.py /opt/webapp/
WORKDIR /opt/webapp
EXPOSE 5000
CMD python app.py

FROM ubuntu:20.04
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN  apt-get update && apt -y install default-jdk tomcat9 maven git
RUN /bin/bash -c 'cd /tmp;\
	git clone https://github.com/iaantdz/App42PaaS-Java-MySQL-Sample.git'
COPY Config.properties /tmp/App42PaaS-Java-MySQL-Sample/WebContent/
RUN /bin/bash -c 'cd  /tmp/App42PaaS-Java-MySQL-Sample;	mvn package'



FROM ubuntu:20.04
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN  apt-get update && apt -y install default-jdk tomcat9 maven git
RUN /bin/bash -c 'cd /tmp;\
	git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello;\
	cd boxfuse-sample-java-war-hello;\
	mvn package'



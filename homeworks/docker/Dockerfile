FROM ubuntu:20.04
RUN DEBIAN_FRONTEND=noninteractive \
    TZ=Europe/Moscow \
    apt-get update && RUN apt -y install default-jdk tomcat9 maven git
RUN /bin/bash -c 'cd /tmp;\
	git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello;\
	cd boxfuse-sample-java-war-hello;\
	mvn package;\
   	cd target/;\
     	cp hello-1.0.war /var/lib/tomcat9/webapps/'
EXPOSE 8080
CMD service tomcat9 start && tail -f /var/lib/tomcat9/logs/catalina.out


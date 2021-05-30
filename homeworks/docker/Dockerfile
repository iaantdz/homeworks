FROM ubuntu:20.04
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN  apt-get update && apt -y install default-jdk tomcat9 maven git
RUN /bin/bash -c 'cd /tmp;\
	git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello;\
	cd boxfuse-sample-java-war-hello;\
	mvn package;\
   	cd target/;\
     	cp hello-1.0.war /var/lib/tomcat9/webapps/'
ENV CATALINA_HOME=/usr/share/tomcat9
ENV CATALINA_BASE=/var/lib/tomcat9
ENV CATALINA_TMPDIR=/tmp
EXPOSE 8080

CMD /usr/share/tomcat9/bin/catalina.sh run


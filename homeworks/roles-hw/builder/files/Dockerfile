FROM ubuntu:20.04 AS builder
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN  apt-get update && apt -y install default-jdk tomcat9 maven git
RUN /bin/bash -c 'cd /tmp;\
	git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello;\
	cd boxfuse-sample-java-war-hello;\
	mvn package'


FROM tomcat:9-alpine
COPY --from=builder /tmp/boxfuse-sample-java-war-hello/target/hello-1.0.war /usr/local/tomcat/webapps/
ENV CATALINA_HOME=/usr/local/tomcat
ENV CATALINA_BASE=/usr/local/tomcat
ENV CATALINA_TMPDIR=/tmp
EXPOSE 8080

CMD /usr/local/tomcat/bin/catalina.sh run



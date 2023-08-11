FROM ubuntu:20.04

RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y git default-jdk maven

WORKDIR /home/app
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
RUN cd /home/app/boxfuse-sample-java-war-hello && mvn package
WORKDIR /home/webapps
RUN cp /home/app/boxfuse-sample-java-war-hello/target/hello-1.0.war /home/webapps

CMD echo "/home/webapps" && ls /home/webapps -la
FROM centos:7
MAINTAINER Christian Mueller
RUN yum update -y \
  && yum -y install curl \
  && yum -y install unzip \
  && yum -y install tar \
  && yum -y install java-1.8.0-openjdk-devel \
  && yum clean all
ENV JAVA_HOME /usr/lib/jvm/java-1.8.0
ENV PATH "$PATH":/${JAVA_HOME}/bin:.:
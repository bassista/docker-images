FROM cmueller/java8-latest
MAINTAINER Christian Mueller


ENV VERSION apache-cassandra-3.7
ENV INSTALL_DIR /usr/local/cassandra
ENV CASSANDRA_HOME ${INSTALL_DIR}/${VERSION}


# Download and install Cassandra
RUN curl -O http://www-eu.apache.org/dist/cassandra/3.7/${VERSION}-bin.tar.gz
RUN mkdir ${INSTALL_DIR}
RUN tar -xvf ${VERSION}-bin.tar.gz -C ${INSTALL_DIR}
RUN rm /${VERSION}-bin.tar.gz


# Add volume to externalize logs
VOLUME ${CASSANDRA_HOME}/logs

# 7000: intra-node communication
# 7001: TLS intra-node communication
# 7199: JMX
# 9042: CQL
# 9160: thrift service
EXPOSE 7000 7001 7199 9042 9160
ENTRYPOINT ${CASSANDRA_HOME}/bin/cassandra -f -R
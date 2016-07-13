FROM cmueller/java8-latest
MAINTAINER Christian Mueller

ENV VERSION wildfly-10.0.0.Final
ENV INSTALL_DIR /usr/local/wildfly
ENV WILDFLY_HOME ${INSTALL_DIR}/${VERSION}
ENV DEPLOYMENT_DIR ${WILDFLY_HOME}/standalone/deployments/

# Download and install Wildfly
RUN curl -O https://download.jboss.org/wildfly/10.0.0.Final/${VERSION}.zip
RUN unzip ${VERSION}.zip -d ${INSTALL_DIR}
RUN rm /${VERSION}.zip

# Add our customized standalone.conf
RUN rm ${WILDFLY_HOME}/bin/standalone.conf
ADD standalone.conf ${WILDFLY_HOME}/bin/

# Add volume to externalize logs
VOLUME ${WILDFLY_HOME}/standalone/logs

# Add default admin user
RUN ${WILDFLY_HOME}/bin/add-user.sh admin admin123! --silent=true

ENTRYPOINT ${WILDFLY_HOME}/bin/standalone.sh -b=0.0.0.0
EXPOSE 9990 9999 8080 8787
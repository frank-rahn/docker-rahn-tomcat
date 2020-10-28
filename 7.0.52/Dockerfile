FROM openjdk:7-jre-alpine
LABEL Maintainer="Frank Rahn <frank@frank-rahn.de>"

RUN apk add --no-cache curl && mkdir /opt

ENV TOMCAT_MAJOR_VERSION 7
ENV TOMCAT_MINOR_VERSION 0
ENV TOMCAT_BUGFIX_VERSION 52
ENV CATALINA_HOME /opt/tomcat

RUN curl -O http://archive.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR_VERSION}/v${TOMCAT_MAJOR_VERSION}.${TOMCAT_MINOR_VERSION}.${TOMCAT_BUGFIX_VERSION}/bin/apache-tomcat-${TOMCAT_MAJOR_VERSION}.${TOMCAT_MINOR_VERSION}.${TOMCAT_BUGFIX_VERSION}.tar.gz && \
curl http://archive.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR_VERSION}/v${TOMCAT_MAJOR_VERSION}.${TOMCAT_MINOR_VERSION}.${TOMCAT_BUGFIX_VERSION}/bin/apache-tomcat-${TOMCAT_MAJOR_VERSION}.${TOMCAT_MINOR_VERSION}.${TOMCAT_BUGFIX_VERSION}.tar.gz.md5 | md5sum -c - && \
gunzip apache-tomcat-*.tar.gz && \
tar xf apache-tomcat-*.tar && \
rm apache-tomcat-*.tar* && mv apache-tomcat-* ${CATALINA_HOME} && \
rm -rf ${CATALINA_HOME}/webapps/examples ${CATALINA_HOME}/webapps/docs ${CATALINA_HOME}/webapps/ROOT ${CATALINA_HOME}/webapps/host-manager ${CATALINA_HOME}/webapps/manager ${CATALINA_HOME}/RELEASE-NOTES ${CATALINA_HOME}/RUNNING.txt ${CATALINA_HOME}/NOTICE ${CATALINA_HOME}/LICENSE ${CATALINA_HOME}/bin/*.bat ${CATALINA_HOME}/bin/*.tar.gz

WORKDIR /opt/tomcat
EXPOSE 8080
EXPOSE 8009

VOLUME [ "${CATALINA_HOME}" ]
ENTRYPOINT [ "bin/catalina.sh" ]
CMD [ "run" ]

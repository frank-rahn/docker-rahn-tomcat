# Docker rahn/tomcat
Ein Docker Image mit Apache Tomcat basierend auf OpenJDK von Alpine.

## Quelle
[docker-tomcat-rahn](https://github.com/frank-rahn/docker-tomcat-rahn)

## Beispiel
Dockerfile:
    FROM rahn/tomcat:latest
    LABEL Maintainer="Frank Rahn <frank@frank-rahn.de>"
    ADD *.jar ${CATALINA_HOME}/lib/
    ADD context.xml ${CATALINA_HOME}/conf/
    ADD *.war ${CATALINA_HOME}/webapps/

In das Verzeichnis `lib` werden z. B. der Datenbanktreiber kopiert.
In der Datei `context.xml` werden die [Resource-Einträge](https://tomcat.apache.org/tomcat-7.0-doc/config/context.html) für die Datenbank eingetragen.

## Exposed Ports
* 8080/tcp
* 8009/ajp

## Environment
* CATALINA_HOME

## Versions
* latest, 7, 7.0, 7.0.106 (OpenJDK: 7-jre-alpine, Tomcat: 7.0.106)
* 7.0.81 (OpenJDK: 7-jre-alpine, Tomcat: 7.0.81)
* 7.0.52 (OpenJDK: 7-jre-alpine, Tomcat: 7.0.52) [(Dockerfile)]()

## Homepage des Autors
[Frank W. Rahn](https://www.frank-rahn.de/)
# dockerhub-jboss-eap-7.1 [![Build Status](https://travis-ci.org/daggerok/dockerhub-jboss-eap-7.1.svg?branch=master)](https://travis-ci.org/daggerok/dockerhub-jboss-eap-7.1)
JBoss EAP 7.1 automation build for docker hub (Linux Alpine, OpenJDK 8u151)

NOTE: Current repository might be renamed to daggerok/jboss-eap-7.1 soon. Sorry for inconviniance

usage:

```docker
FROM daggerok/jboss-eap-7.1
RUN echo "JAVA_OPTS=\"\$JAVA_OPTS -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \"" >> ${JBOSS_HOME}/bin/standalone.conf
EXPOSE 5005 8080 9990 8443
ADD ./build/libs/*.war ${JBOSS_HOME}/standalone/deployments/
```

Console user / password:

admin
Admin.123

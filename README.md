# dockerhub-jboss-eap-7.1 [![Build Status](https://travis-ci.org/daggerok/dockerhub-jboss-eap-7.1.svg?branch=master)](https://travis-ci.org/daggerok/dockerhub-jboss-eap-7.1)
JBOSS EAP 7.1 docker image (Linux Alpine, OpenJDK 8u151)

note: In furute, current repository might be renamed to `daggerok/jboss-eap-7.1`. Sorry for inconviniance


**Exposed ports**:

- 8080 - deployed apps
- 9990 - console
- 8443 - https

**Usage**:

```
FROM daggerok/jboss-eap-7.1
ADD ./build/libs/*.war ${JBOSS_HOME}/standalone/deployments/
```

**Remote debug**:

```
FROM daggerok/jboss-eap-7.1
RUN echo "JAVA_OPTS=\"\$JAVA_OPTS -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \"" >> ${JBOSS_HOME}/bin/standalone.conf
EXPOSE 5005
ADD ./build/libs/*.war ${JBOSS_HOME}/standalone/deployments/
```

**Console**:

- url: http://127.0.0.1:9990/console
- user: admin
- password: Admin.123

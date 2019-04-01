FROM  codibly/java:jdk-11

ENV MAVEN_VER 3.6.0
ENV MAVEN_HOME /opt/maven

RUN mkdir -p ${MAVEN_HOME} && \
    wget https://www-eu.apache.org/dist/maven/maven-3/${MAVEN_VER}/binaries/apache-maven-${MAVEN_VER}-bin.tar.gz && \
    tar -xvzf apache-maven-${MAVEN_VER}-bin.tar.gz && \
    mv apache-maven-${MAVEN_VER}/* ${MAVEN_HOME}

ENV M2_HOME=${MAVEN_HOME}
ENV PATH=${M2_HOME}/bin:${PATH}

RUN mvn --version
FROM  codibly/java:jdk-8

ENV GRADLE_VER 4.8.1
ENV GRADLE_HOME /opt/gradle

RUN mkdir -p ${GRADLE_HOME} && \
    wget https://services.gradle.org/distributions/gradle-${GRADLE_VER}-bin.zip && \
    unzip -d /tmp gradle-${GRADLE_VER}-bin.zip && \
    mv /tmp/gradle-${GRADLE_VER}/* ${GRADLE_HOME}/ && \
    ln -s ${GRADLE_HOME}/bin/gradle /usr/bin/gradle

RUN gradle --version
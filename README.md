# Images for Java development

### Supported tags and respective ```Dockerfile``` links

* ```jdk-8``` Oracle Java 8 on Ubuntu base image

* ```gradle-4.8``` Above + Gradle 4.8

* ```maven-3.5``` Above + Maven 3.5

### How to create a new image
1. Create a new directory for the image for example `gradle/5.0`
2. Create a new `Dockerfile` in the new directory
3. Build a new image 
```bash
$ cd gradle/5.0
$ docker build -f Dockerfile -t codibly/gradle:5.0-jdk-8 .
```
4. Login into the docker hub `docker login`
5. Push new image
```bash
$ docker push codibly/gradle:5.0-jdk-8 .
```
6. Done!
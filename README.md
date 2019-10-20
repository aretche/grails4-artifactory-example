# Grails 4 example application using Artifactory

[Grails](https://grails.org/index.html) 4 application using [Artifactory](https://jfrog.com/open-source/#artifactory)

## Features

* Uses local Artifactory repo to cache dependencies at build, test and runtime.
* Uses local Artifactory repo to store gradle cache objects
* TODO: Use local Artifactory repo to publish jar and war

## Relevant files

* build.gradle
* gradle.properties
* settings.gradle

## Requisites

Artifactory OSS runnig in http://localhost with default credentials (user='admin', password='password')

You could run a local with [docker-compose](https://docs.docker.com/compose/) using [Artifactory's examples repo](https://github.com/jfrog/artifactory-docker-examples):

```
git clone https://github.com/jfrog/artifactory-docker-examples.git
cd artifactory-docker-examples/docker-compose/
sudo ./prepareHostEnv.sh -t oss -c
sudo docker-compose -f artifactory-oss.yml up -d
```

After this command navigate to http://localhost to access Artifactory web interface.

Configure 2 remote maven repositories to cache https://repo.grails.org/grails/core and https://jcenter.bintray.com. 
Create a local repository for gradle cache.
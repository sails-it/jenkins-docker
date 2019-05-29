# Jenkins Manager with Docker

This image contains a jenkins manager with docker support. It is kept up-to-date with `jenkins/jenkins:latest`.

## Usage

To start a jenkins instance, execute:

```bash
docker run \
	-p 8080:8080 \
	-p 50000:50000 \
	-v /path/to/jenkins/home:/var/jenkins_home \
	-v /path/to/root/home:/root \
  	sailsit/jenkins-docker
```


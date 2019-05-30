# Jenkins Manager with Docker

This image contains a jenkins manager with docker support. It is kept up-to-date with `jenkins/jenkins:latest`.

## Usage

To start a jenkins instance, execute:

```bash
docker run \
        --restart always \
        --detach
	-p 8080:8080 \
	-p 50000:50000 \
	-v /path/to/jenkins/home:/var/jenkins_home \
	-v /path/to/root/home:/root \
  	sailsit/jenkins-docker
```

Or create a `docker-compose.yml`:

```yaml
version: '3.6'

services:
  jenkins:
    image: sailsit/jenkins-docker
    restart: always
    ports:
      - 8080:8080
      - 50000:50000
    volumes:
      - jenkins_home:/var/jenkins_home
      - root:/root 

volumes:
  jenkins_home:
  root:
```

And run `docker-compose up -d`.


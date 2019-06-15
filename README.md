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
	-v /var/run/docker.sock:/var/run/docker.sock
        sailsit/jenkins-docker
```

Or create a `docker-compose.yml`:

```yaml
version: '3.7'

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
      - /var/run/docker.sock:/var/run/docker.sock

volumes:
  jenkins_home:
  root:
```

And run `docker-compose up -d`.


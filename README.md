# docker-alpine-php-nightly
Docker Image for PHP nightly. Currently 7.4.0-dev.

This image is highly inspired by the [official Alpine PHP images](https://hub.docker.com/_/php/).

## How to use this image

### Run a single PHP script

```
$ docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp tommymuehle/docker-alpine-php-nightly php your-script.php
```

### Create a Dockerfile in your PHP project

```
FROM tommymuehle/docker-alpine-php-nightly
COPY . /usr/src/myapp
WORKDIR /usr/src/myapp
CMD [ "php", "./your-script.php" ]
```

Then, run the commands to build and run the Docker image:

```
$ docker build -t my-php-app .
$ docker run -it --rm --name my-running-app my-php-app
```

## Issues
If you have any problems with or questions about this image, please contact me through a [GitHub issue](https://github.com/tommy-muehle/docker-alpine-php-nightly/issues).

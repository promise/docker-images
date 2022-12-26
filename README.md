# Docker images

Just a collection of Docker images of stuff that don't already have a Docker image.

See all the available images by browsing the branches on the repository.


## Build an image

Here's an example on how to build and use the `jmusicbot` image:

```
$ docker build https://github.com/promise/docker-images.git#jMusicBot -t jmusicbot-image
$ docker run -d --name jmusicbot jmusicbot-image
```


## Docker Compose

You can also use it directly in a Compose file. Here's an example with the jMusicBot image:

```yaml
version: '3'

services:
  jmusicbot:
    build: https://github.com/promise/docker-images.git#jMusicBot
    ...
```

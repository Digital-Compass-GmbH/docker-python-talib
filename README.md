# docker-python-talib

## Preparation
Before creating the new docker image, copy the current requirements file into the directory.
Manually remove talib from the dependency list as it is installed later.
(Yes we could install everything in the end but we follow a fail fast approach, since building talib on 
an M1 for amd64 takes a lot of time)

## build the image

Important: Since we would like to use this image in bitbucket pipelines, we need to have as an os/platform amd64.
Therefore, the command is:
```
docker buildx build . -t digitalcompass/docker-python-talib:latest --platform linux/amd64
```

## deploy
docker push digitalcompass/docker-python-talib:latest

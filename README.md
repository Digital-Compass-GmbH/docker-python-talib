# docker-python-talib

## Preparation
Before creating the new docker image, copy the current requirements file into the directory.

## build the image

Important: Since we would like to use this image in bitbucket pipelines, we need to have as an os/platform amd64.
Therefore, the command is:
```
docker buildx build . -t digitalcompass/docker-python-talib:latest --platform linux/amd64
```

## deploy
docker push digitalcompass/docker-python-talib:latest

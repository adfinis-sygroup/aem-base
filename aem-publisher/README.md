# aem-publisher

This Docker image installs [Adobe Experience Manager 6.2](http://docs.adobe.com/docs/en/aem/6-2.html), and allows it
to be run within a Docker container.

## About docker-aem-publisher

> *You must have a copy of the AEM 6 installation Media for this to work

You must copy your AEM installation media into the base directory before
running this image. The image expects the following files within the base directory:
* AEM_6.2_Quickstart.jar
* license.properties

## Usage
Create a new Dockerfile within your directory, and insert the following:

```
# DOCKER-VERSION 1.0.1
FROM ggotti/aem-publisher
MAINTAINER <your_username>
```

Then execute your build:
```bash
docker build --tag="<your_build_tag>" .
```

To run your image, with the AEM instance:
```bash
$ docker run --name AEM_PUB -p 4503:4503 -d "<your_build_tag>"
```
Where
* `-d` will run a detached session running in the background
* `--name` will assign the given name to the running container instance
* `<your_build_tag>` the name of your docker image
* `-p 4503:4503` will expose the AEM default publisher port

# Day 1: Hello Container

## Objective
Run your first custom Docker container and understand the flow from image to container.

## Build Image

```bash
docker build -t hello-docker .
```

## Run Container

```bash
docker run hello-docker
```

## What You Learn

- How a `Dockerfile` defines an image
- How `docker build` creates an image
- How `docker run` starts a container from that image

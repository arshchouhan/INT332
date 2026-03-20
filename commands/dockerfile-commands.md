# Dockerfile and Build Commands

Useful commands for building images from Dockerfiles and managing the result.

## Build an Image

```bash
docker build -t my-app:1.0 .
```

## Build With a Specific Dockerfile

```bash
docker build -f Dockerfile.dev -t my-app:dev .
```

## Build Without Cache

```bash
docker build --no-cache -t my-app:fresh .
```

## Pass Build Arguments

```bash
docker build --build-arg APP_VERSION=1.2.0 -t my-app:1.2.0 .
```

## List Images

```bash
docker images
```

## Show Image Layers

```bash
docker history my-app:1.0
```

## Inspect Image Metadata

```bash
docker image inspect my-app:1.0
```

## Tag an Image

```bash
docker tag my-app:1.0 my-app:latest
```

## Remove an Image

```bash
docker rmi my-app:1.0
```

## Run Container From Built Image

```bash
docker run -d -p 3000:3000 --name my-app-container my-app:1.0
```

## Follow Logs

```bash
docker logs -f my-app-container
```

## Stop and Remove Container

```bash
docker stop my-app-container
docker rm my-app-container
```

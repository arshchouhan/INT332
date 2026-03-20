# Dockerfile Study Guide

This folder explains Dockerfile basics, important instructions, and build/run commands.

## What Is a Dockerfile?

A Dockerfile is a text file with instructions used by Docker to build an image.

## Core Dockerfile Instructions

## `FROM`
Sets the base image.

```dockerfile
FROM node:20-alpine
```

## `WORKDIR`
Sets the working directory inside the image.

```dockerfile
WORKDIR /app
```

## `COPY`
Copies files from host to image.

```dockerfile
COPY package*.json ./
COPY . .
```

## `RUN`
Executes commands at image build time.

```dockerfile
RUN npm install
```

## `EXPOSE`
Documents the application port.

```dockerfile
EXPOSE 3000
```

## `CMD`
Default command when container starts.

```dockerfile
CMD ["node", "server.js"]
```

## `ENTRYPOINT`
Sets the main executable for the container.

```dockerfile
ENTRYPOINT ["node", "server.js"]
```

## `ENV`
Defines environment variables.

```dockerfile
ENV NODE_ENV=production
```

## `ARG`
Defines build-time variables.

```dockerfile
ARG APP_VERSION=1.0.0
```

## `LABEL`
Adds metadata to the image.

```dockerfile
LABEL maintainer="student@example.com"
```

## `USER`
Sets the user for runtime security.

```dockerfile
USER node
```

## Example Dockerfile (Node.js)

```dockerfile
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install --omit=dev

COPY . .

EXPOSE 3000

CMD ["node", "server.js"]
```

## Build Commands

```bash
docker build -t users-api:1.0 .
docker build -t users-api:latest .
```

## Run Commands

```bash
docker run -d -p 3000:3000 --name users-api-container users-api:1.0
docker logs users-api-container
docker stop users-api-container
docker rm users-api-container
```

## Inspect and Manage

```bash
docker images
docker image inspect users-api:1.0
docker history users-api:1.0
```

## Learning Goal

Understand how Dockerfile instructions create an image and how that image runs as a container.

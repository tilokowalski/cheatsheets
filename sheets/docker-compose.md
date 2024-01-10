# Docker and Docker Compose

This cheatsheet provides a comprehensive overview of Docker and Docker Compose, focusing on their use, management of containers, images, and implementing secrets for environment variables.

Compose file library: [/docker-compose/examples]()

## Basic Docker Concepts

### Docker Images and Containers
- **Docker Image**: A read-only template used to create containers.
- **Docker Container**: A runnable instance of an image.

### Dockerfile
- A text document that contains all the commands to assemble an image.

### Docker Hub
- A cloud-based registry service for building and sharing container images.

## Docker Commands

### Managing Images
- **Pull an Image**: `docker pull [image-name]`
- **Build an Image**: `docker build -t [image-name] .`
- **List Images**: `docker images`

### Managing Containers
- **Create and Start a Container**: `docker run -d --name [container-name] [image-name]`
- **List Running Containers**: `docker ps`
- **Stop a Container**: `docker stop [container-name]`
- **Remove a Container**: `docker rm [container-name]`

### Executing Commands
- **Execute Command in Running Container**: `docker exec -it [container-name] [command]`

### Viewing Logs
- **View Container Logs**: `docker logs [container-name]`

## Docker Compose

### Overview
- A tool for defining and running multi-container Docker applications.

### docker-compose.yml
- A YAML file defining services, networks, and volumes.

### Basic Commands
- **Start Services**: `docker-compose up -d`
- **Stop Services**: `docker-compose down`
- **Rebuild Services**: `docker-compose up --build`

## Docker Secrets

### Overview
- Docker secrets provide a secure way to store and manage sensitive data like passwords and API keys.

### Creating Secrets
- **Using File**: `echo 'secret_data' | docker secret create [secret-name] -`
- **Using Docker Compose**: Define secrets in `docker-compose.yml` and reference them in services.

### Accessing Secrets
- Secrets are mounted into `/run/secrets/[secret-name]` in the container.

## Implementing Secrets for Environment Variables

### In Dockerfile
- Use `ENV` to set environment variables, referencing secrets as needed.

### In docker-compose.yml
- Use `environment` key to set environment variables, referencing secrets.

### Best Practices
- Do not hardcode sensitive information in Dockerfiles or image layers.
- Use Docker secrets to securely manage sensitive data.
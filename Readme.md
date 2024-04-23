# Building Docker Images

This section details how to build Docker images for your Node.js (`node-app`) and Spring Boot (`spring-boot-app`) applications using Docker Buildx.

## Prerequisites:

- Docker: Installed and running. Verify with `docker --version` in your terminal.
- Docker Buildx: Enabled. Follow the official Docker documentation ([Docker Buildx documentation](https://docs.docker.com/reference/cli/docker/buildx/)) for instructions.

## Building the Node.js Application:

1. Open your terminal and navigate to the root directory of your project where `Dockerfile.nodeapp` resides.

2. Run the following command to build the Docker image for your Node.js application, tagging it with `node-app`:

    ```bash
    docker buildx build -t node-app -f Dockerfile.nodeapp .
    ```

    - `docker buildx build`: Instructs Docker Buildx to perform the build.
    - `-t node-app`: Tags the image with the name `node-app` (customize if needed).
    - `-f Dockerfile.nodeapp`: Specifies the Dockerfile to use for the build.
    - `.`: Refers to the current working directory.

## Building the Spring Boot Application:

1. Navigate to the root directory where `Dockerfile.springboot` is located.

2. Run the following command to build the Docker image for your Spring Boot application, tagging it with `spring-boot-app`:

    ```bash
    docker buildx build -t spring-boot-app -f Dockerfile.springboot .
    ```

    The options have the same meaning as in the Node.js build command.

## Verification:

After running the build commands, use the following command to verify that the images have been created:

```bash
docker image ls




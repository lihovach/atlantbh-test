# Running Docker Compose

This markdown file provides instructions for running a Docker Compose file that sets up a Java API service and a Node.js application. Follow these steps to get started:

## Prerequisites:

    Docker: Installed and running. Verify with `docker --version` in your terminal.
    Docker Compose: Installed and configured.

## Environment Variables:

Before running the Docker Compose file, ensure the following environment variables are set:

```bash

export DB_PASSWORD=test
export DB_USER=test
export DB_NAME=test

```
## VInstallation of HTTPie:

If not already installed, install HTTPie using the following command:

```bash
sudo apt install httpie
```

## Running Docker Compose:

Navigate to the directory containing your Docker Compose file.
Run the following command to start the services defined in the Docker Compose file:

```bash
docker-compose up -d
```
This command will launch the containers in detached mode.

## Verification:

After the containers have started, you can verify that the services are running correctly using HTTPie. Run the following commands:

```bash
http GET localhost:8080/java/api/v1/status
```
Expected Output:

```bash
HTTP/1.1 200 
Content-Type: application/json;charset=UTF-8
Date: Tue, 23 Apr 2024 22:44:48 GMT
Transfer-Encoding: chunked

{
    "postgresVersion": "PostgreSQL 15.6 (Debian 15.6-1.pgdg120+2) on x86_64-pc-linux-gnu, compiled by gcc (Debian 12.2.0-14) 12.2.0, 64-bit",
    "status": "UP"
}
```

```bash
http GET localhost:8080/java/api/v1/node
```
Expected Output:

```bash
HTTP/1.1 200 
Content-Type: application/json;charset=UTF-8
Date: Tue, 23 Apr 2024 22:44:59 GMT
Transfer-Encoding: chunked

{
    "data": "Hello world from node app"
}
```
If you see the expected output for both commands, the Docker Compose setup is working correctly.

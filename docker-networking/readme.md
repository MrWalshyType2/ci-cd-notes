# Docker networking

Learn how to run services and expose ports to other applications to allow the running of servers inside Docker containers.

## Docker commands

| Docker command                                                   | Description |
| ---                                                              | ---         |
| docker logs <container-id>                                       | Displays logs for a container |
| docker run -d -p <host-port>:<container-port> <image>            | Runs a detached (-d) container using the specified host and container ports (-p) |
| docker run -d -p <ip>:<host-port>:<container-port> <image>       | Same as above, except publishing to the specific host network instead|
| docker inspect <container-id>                                    | Inspects and outputs a response of network information about a running container |
| docker inspect --format <filter-string> <container-id>           | Inspects and filters the response. Example: docker inspect --format '{{ .NetworkSettings.IPAddress }}' <container-id> |
| docker network ls                                                | Lists current active Docker networks |

## Running a Tomcat server directly from Docker Hub

```
docker run -d -p 8080:8080 tomcat
```

- Runs a Tomcat server in a Docker container in detached mode on port 8080 in the container, exposes this port to port 8080 on the host machine

## Change the Docker network type

Use the `--network` flag to set the network type:

- bridge (default): Default Docker bridge to host system

- none: no network

- container: Network joined to other container (specified)

- host: Host's network stack

- NETWORK: User-created network via 'docker network create'

## Informing the User of which Port to Publis

Dockerfile instructions can use the `EXPOSE` command to expose a port:

```
EXPOSE <port>
```

- This is only a suggestion to inform users of which port should be published exposed from the container

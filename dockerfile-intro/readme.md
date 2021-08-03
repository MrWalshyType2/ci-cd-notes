# Docker commands

| Command                                   | Description |
| ---                                       | ---         |
| docker info                               | Displays information about the current docker environment |
| docker run <image>                        | Runs docker images |
| docker run -i -t <image> <terminal>       | Runs images in interactive (i) mode and connects using the specified terminal/teletype (t). Example usage: docker run -i -t ubuntu:18.04 /bin/bash |
| docker run -d -t <image>                  | Runs an image in background mode using -d (--detach). Starts the container but doesn't attach the console |
| docker search <image>                     | Returns a list of images on docker hub that match the specified image |
| docker diff <container-id>                | Compares the container to its default image. |
| docker commit <container-id> <image-name> | Commit the container to an image. Example: docker commit dee2jdos8943jj ubuntu-with-python |
| docker build -t <image-name>              | Builds the specified image for use |
| docker images                             | Displays local images |
| docker ps                                 | Lists the current running containers |
| docker ps -a                              | Lists all containers (statuses included: Up, Exited, Paused, Restarting) |
| docker stop <container-id>                | Stops the container with the specified id |
| docker create <image>                     | Creates a container without starting it |

# Running this file

Building:

`docker build -t ubuntu-with-python .`

Passing an env variable:

`docker run -e NAME=Bob ubuntu-with-python`

Defaulting to Dockerfile env:

`docker run ubuntu-with-python`

## Env variables

Either pass them at the command line:

`docker run -e ENV_NAME=VALUE`

- `-e` is the environment variable flag

Or pass via the Dockerfile:

`ENV ENV_NAME VALUE`

Command-line env variables override Dockerfile env variables

### Getting the env variable

Python 3:

```python
import os
print("Hello from", os.environ['ENV_NAME'])
```
```

# FROM defines the image that this image will be built on top of
FROM ubuntu:18.04
# RUN specifies commands to run inside the container
RUN apt-get update && \
    apt-get install -y python && \
    apt-get install -y git && \
    apt-get install -y openjdk-8-jdk
# COPY copies a file or directory into the filesys of the image
COPY hello.py .
# ENTRYPOINT defines the app to run in the image
ENTRYPOINT ["python", "hello.py"]

# ENV declares a ENV variable
ENV NAME Bob

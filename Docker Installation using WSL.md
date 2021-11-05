# Docker on Windows without Docker Desktop

A quick and parctical replacement for Docker Desktop in just a few steps.

## Install WSL
Install Ubuntu 20.04 LTS from Windows Store for instance and start it. Enter default user name and passowrd when asked to.

## Setup Docker in WSL
Install `docker.io` and update user's profile to **atumatically** start the Docker daemon. See this nicely written article for details on how to do this: [Run Docker in WSL (Windows 10/11) without Docker Desktop](https://medium.com/geekculture/run-docker-in-windows-10-11-wsl-without-docker-desktop-a2a7eb90556d)

Create a file named `daemon.json` under `/etc/docker/` with the following content and then *restart* the docker daemon (or you could do this before starting the Docker daemon for the first time).
```
# sudo nano /etc/docker/daemon.json
{
  "hosts": ["unix:///var/run/docker.sock", "tcp://0.0.0.0:2375"]
}
```

## Setup Docker Client in Windows
Download a Docker client from [here](https://download.docker.com/win/static/stable/x86_64/) and add its extracted folder path to you `PATH` environment variable.

Try out the client by running `docker version` in a new CMD window.

## Pull Images in Windows
Add a new environment variable named `DOCKER_HOST` and set its value to `localhost:2375`. 

Trying pulling an image by running `docker run hello-world` in a new CMD window.

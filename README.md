# Tufa Stack Dockerfiles (based on Lambda Stack)

Dockerfiles with rolling-release Lambda Stack, designed for use with nvidia-container-toolkit

### Installing nvidia-container-toolkit

1. Ensure that you have a docker version > 19.03. On Ubuntu, you can simply run `sudo apt-get install docker.io`. On a different OS, or if you prefer to use upstream docker, follow [Docker's installation instructions](https://docs.docker.com/engine/install/ubuntu/)

2. If using Lambda Stack on your host machine, install nvidia-container-toolkit with `sudo apt-get install nvidia-container-toolkit`. Otherwise, follow [NVIDIA's installation instructions](https://github.com/NVIDIA/nvidia-docker)

### Building images

Build the image with the appropriate command for the distribution you wish to use.
Note that only current LTS versions are supported: 20.04, 22.04, and 24.04.

```
sudo docker build -t tufa-stack:24.04 --build-arg UBUNTU_VERSION=24.04 .
```

Note that building these docker images requires acceptance of the [cuDNN license agreement](https://docs.nvidia.com/deeplearning/cudnn/latest/reference/eula.html)

### Pushing images

```
sudo docker tag tufa-stack:24.04 ghcr.io/dominiquegarmier/tufa-stack:24.04
sudo docker push ghcr.io/dominiquegarmier/tufa-stack:24.04
```

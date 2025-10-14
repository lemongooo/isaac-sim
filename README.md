# Isaac Sim Docker Images

This project provides two Docker images and one compose.yml:

- **data-collector**: Runs Isaac Sim and executes simulation scripts.  
- **trainer**: Runs the training process with datasets and saves checkpoints.
- **isaac-node**: Runs the robot simulation and publishes joint states to ROS topics.
- **model-node**: Receives joint/camera data, runs model inference and publishes control commands.
- **docker-compose.yml**:Defines and starts both services with GPU support, mounted volumes, and proper resource limits.

## ⚙️ Prerequisites

Before running, please ensure the following are installed on your machine:

- [Docker](https://docs.docker.com/get-docker/)  
- [Docker Compose](https://docs.docker.com/compose/)  
- NVIDIA GPU with correct drivers installed  
- [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html) (for GPU access in Docker)

Test if GPU works in Docker:

```bash
docker run --rm --gpus all nvidia/cuda:12.2.0-base-ubuntu22.04 nvidia-smi
```

## Pull Images
```bash
docker pull ghcr.io/lemongooo/data-collector:latest
docker pull ghcr.io/lemongooo/trainer:latest
docker pull ghcr.io/lemongooo/isaac-node:latest
docker pull ghcr.io/lemongooo/model-node:latest
```

## Run with Docker Compose
Clone this repository:
```bash
git clone https://github.com/lemongooo/isaac-sim.git
cd isaac-sim
```

Start the services:
```bash
docker compose up data-collector
docker compose up trainer
docker compose up isaac-node
docker compose up model-node
```

Enter the container:
```bash
docker compose run --rm --entrypoint /bin/bash [SERVICE-NAME]
```
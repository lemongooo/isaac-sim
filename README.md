# Isaac Sim Docker Images

This project provides two Docker images and one compose.yml:

- **data-collector**: Runs Isaac Sim and executes simulation scripts.  
- **trainer**: Runs the training process with datasets and saves checkpoints.
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
```

Enter the container:
```bash
docker compose run --rm --service-ports --entrypoint /bin/bash data-collector
```
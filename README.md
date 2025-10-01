# Isaac Sim Docker Images

This project provides two Docker images and one compose.yml:

- **data-collector**: Runs Isaac Sim and executes simulation scripts.  
- **trainer**: Runs the training process with datasets and saves checkpoints.
- **docker-compose.yml**:Defines and starts both services with GPU support, mounted volumes, and proper resource limits.

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

# Docker Compose for Machine Learning

This repository contains a Docker Compose configuration file (`docker-compose-ml.yml`) to set up a JupyterLab environment with Python 3.8 for machine learning tasks.

## 1. Prerequisites

Before you begin, ensure you have Docker and Docker Compose installed on your system.

## Docker Compose Structure

Below is the Docker Compose configuration for setting up a JupyterLab environment with Python 3.8.

```yaml
version: '3'
services:
  jupyterlab:
    image: jupyter/base-notebook:python-3.8
    ports:
      - "8888:8888"
    volumes:
      - ./notebooks:/home/jovyan/work
    environment:
      - JUPYTER_ENABLE_LAB=yes
```

### JupyterLab Docker Setup

We have defined a service named `jupyterlab` with the following specifications:

- Docker image: `jupyter/base-notebook:python-3.8`, which includes Python 3.8 and JupyterLab pre-installed.
- Port Mapping: We map port 8888 from the container to port 8888 on your host machine for accessing JupyterLab in a web browser.
- Volume: We create a volume named `./notebooks` and mount it to the `/home/jovyan/work` directory inside the container. This allows you to persist your JupyterLab notebooks and data outside the container.
- Environment Variable: We set the `JUPYTER_ENABLE_LAB` environment variable to "yes" to enable JupyterLab.

## Running Docker Compose

To run the `docker-compose-ml.yml` file, use the following command:

```bash
docker-compose -f docker-compose-ml.yml up -d
```

## 2. Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/your-username/docker-ml.git
cd docker-ml
```
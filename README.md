# Monitoring Stack

[![Build, Scan & Publish Docker image](https://github.com/mbasri/monitoring/actions/workflows/main.yml/badge.svg)](https://github.com/mbasri/monitoring/actions/workflows/main.yml)

**Docker images to run the Monitoring Stack.**

> Docker base images:
> * [https://hub.docker.com/r/prom/prometheus](https://hub.docker.com/r/prom/prometheus)
> * [https://hub.docker.com/r/prom/node-exporter](https://hub.docker.com/r/prom/node-exporter)

## Prerequisites

* [Docker](https://docs.docker.com/get-docker/)

## Usage

### Manual Build

```bash
git clone https://github.com/mbasri/monitoring.git monitoring
cd monitoring/docker
./build
```

> Ensure the `build` file is executable: `chmod +x ~/monitoring/build`

### Github Action

#### Requirements

| Name | Version |
|------|---------|
| <a name="requirement_actions_checkout"></a> [actions/checkout](https://github.com/actions/checkout) | 4 |
| <a name="requirement_mbasri_actions_dockerize"></a> [mbasri-actions/dockerize](https://github.com/mbasri-actions/dockerize) | 1.0.0 |
| <a name="requirement_mbasri_actions_docker_scan"></a> [mbasri-actions/docker-scan](https://github.com/mbasri-actions/docker-scan) | 1.0.0 |

#### Inputs

`No Inputs.`

#### Outputs

`No Outputs.`

### Quickstart

#### Simple

```bash
docker run -p 9090:9090 ghcr.io/mbasri/prometheus:latest
# Go to http://localhost:9090 and start the configuration
```

#### With Custom Config File

```bash
docker run -p 9090:9090 \
  -v $PWD/files.d/etc/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml \
  -v $PWD/files.d/prometheus:/prometheus \
  ghcr.io/mbasri/prometheus:latest
```

### Run via Docker Compose

```bash
git clone https://github.com/mbasri/monitoring.git monitoring
cd monitoring/docker-compose
docker-compose up -d
```

## Backup & Restore

### Backup

`N/A`

### Restore

`N/A`

## Volumes

* Prometheus
  * `/prometheus`
  * `/etc/prometheus/prometheus.yml`

* Node Exporter
  * `N/A`

## Ports

* Prometheus
  * TCP: 9090

* Node Exporter
  * TCP: 9100

## Author

* [**Mohamed BASRI**](https://github.com/mbasri)

## License

This is free and unencumbered software released into the public domain. See the [LICENSE](./LICENSE) file for details.

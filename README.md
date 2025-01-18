# Monitoring Stack

**Prometheus**

![Prometheus Docker Pulls](https://img.shields.io/docker/pulls/mbasri/prometheus.svg)
![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/mbasri/prometheus)

**Node Exporter**

![Docker Pulls](https://img.shields.io/docker/pulls/mbasri/node-exporter.svg)
![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/mbasri/node-exporter)

**Docker images to run the Monitoring Stack.**

> * Docker base images:
>
>   * [https://hub.docker.com/r/prom/prometheus](https://hub.docker.com/r/prom/prometheus)
>   * [https://hub.docker.com/r/prom/node-exporter](https://hub.docker.com/r/prom/node-exporter)

## Prerequisites

* [Docker](https://docs.docker.com/get-docker/)

## Usage

### Build New Images

```bash
git clone https://github.com/mbasri/monitoring.git monitoring
cd monitoring/docker
./build
```

> Ensure the `build` file is executable: `chmod +x ~/monitoring/build`

### Run Manually

#### Quickstart

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

//TODO

### Restore

//TODO

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

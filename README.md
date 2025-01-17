# Monitoring Stack

**Prometheus**

![Prometheus Docker Pulls](https://img.shields.io/docker/pulls/mbasri/prometheus.svg)
![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/mbasri/prometheus)

**Node Exporter**

![Docker Pulls](https://img.shields.io/docker/pulls/mbasri/node-exporter.svg)
![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/mbasri/node-exporter)

**A docker images to run Monitoring Stack.**

> * Docker base images:
>
>   * [https://hub.docker.com/r/prom/prometheus](https://hub.docker.com/r/prom/prometheus)
>   * [https://hub.docker.com/r/prom/node-exporter](https://hub.docker.com/r/prom/node-exporter)

## Prerequisites

* [docker](https://www.google.com/search?q=how+to+install+docker)

## Usage

###  Build a new images

```bash
git clone https://github.com/mbasri/monitoring.git monitoring
cd monitoring/docker
./build
```

> Make sure that the `build` file can be executed via '`chmod +x ~/monitoring/build`'

###  Run manually

#### Quickstart

```bash
docker run -p 9090:9090 mbasri/prometheus:latest
# Go to http://localhost:9090 and start the configuration
```

#### With custom config file

```bash
docker run -p 9090:9090 \
  -v $PWD/files.d/etc/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml \
  -v $PWD/files.d/prometheus:/prometheus \
  mbasri/prometheus:latest
```

###  Run via docker-compose

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
  * /prometheus
  * /etc/prometheus/prometheus.yml

* Node Exporter

## Ports

* Prometheus
  * TCP: 9090

* Node Exporter
  * TCP: 9100

## Author

* [**Mohamed BASRI**](https://github.com/mbasri)

## License

This is free and unencumbered software released into the public domain - see the [LICENSE](./LICENSE) file for details

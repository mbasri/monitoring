# sensorgraph/nginx

* Prometheus
 ![Docker Pulls](https://img.shields.io/docker/pulls/mbasri/prometheus.svg)
 ![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/mbasri/prometheus)

* Node Exporter
 ![Docker Pulls](https://img.shields.io/docker/pulls/mbasri/node-exporter.svg)
 ![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/mbasri/node-exporter)

**A docker images to run Monitoring Stack.**

> * Docker base image: [https://hub.docker.com/_/nginx](https://hub.docker.com/_/nginx)

## Prerequisites

* [docker](https://www.google.com/search?q=how+to+install+docker)

## Usage

###  Build a new image

```bash
git clone https://gitlab.com/mbasri/monitoring.git monitoring
cd monitoring/docker
./build
```

> Make sure that the `build` file can be executed via '`chmod +x ~/monitoring/build`'

###  Run manually

#### Quickstart

```bash
docker run -p 80:80 sensorgraph/nginx:latest
# Go to http://localhost:80 and start the configuration
```

#### Automated Setup

```bash
docker run -p 80:80 \
  -v $PWD/files.d/etc/nginx/conf.d/default.conf:/etc/nginx/conf.d/default.conf \
  -v $PWD/files.d/etc/nginx/.htpasswd:/etc/nginx/.htpasswd \
  -v $PWD/files.d/etc/ssl/certs/nginx.crt:/etc/ssl/certs/nginx.crt \
  -v $PWD/files.d/etc/ssl/private/nginx.key:/etc/ssl/private/nginx.key \
  nginx:latest
```

###  Run via docker-compose

```bash
git clone https://gitlab.com/mbasri/monitoring.git monitoring
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
  * /var/lib

* Node Exporter
  * /var/lib

## Ports

* Prometheus
  * TCP: 9090

* Node Exporter
  * TCP: 9100

## Author

* [**Mohamed BASRI**](https://gitlab.com/mbasri)

## License

This is free and unencumbered software released into the public domain - see the [LICENSE](./LICENSE) file for details

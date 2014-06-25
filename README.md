## Haproxy Dockerfile


This repository contains a tweaked **Dockerfile** of [Haproxy](http://haproxy.1wt.eu/) for [Docker](https://www.docker.com/) published to the public [Docker Registry](https://registry.hub.docker.com/).


### Dependencies

* [ubuntu:14.04](https://registry.hub.docker.com/_/ubuntu)


### Installation

1. Install [Docker](https://www.docker.io/).

2. Download [this build](https://registry.hub.docker.com/u/bhang/haproxy/) from public [Docker Registry](https://registry.hub.docker.com/): `docker pull bhang/haproxy`

   (alternatively, you can build an image from Dockerfile: `docker build -t="bhang/haproxy" github.com/bhang/haproxy`)


### Usage

    docker run -d -p 80:80 bhang/haproxy

#### Customizing Haproxy

    docker run -d -p 80:80 -v <override-dir>:/haproxy-override bhang/haproxy

where `<override-dir>` is an absolute path of a directory that could contain:

  - `haproxy.cfg`: custom config file (replace `/dev/log` with `127.0.0.1`, and comment out `daemon`)
  - `errors/`: custom error responses

After few seconds, open `http://<host>` to see the haproxy stats page.

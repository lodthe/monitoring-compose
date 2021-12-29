# Monitoring compose

The repository contains configuration information for running the following services:
- [Prometheus](https://prometheus.io/)
- [Cadvisor](https://github.com/google/cadvisor) &mdash; for containers resource usage monitoring
- [Grafana](https://grafana.com/)
- [Node exporter](https://github.com/prometheus/node_exporter)  &mdash; machine metrics exporter
- [Loki](https://grafana.com/oss/loki/) and [Promtail](https://grafana.com/docs/loki/latest/clients/promtail/) &mdash; log aggregation system

## How to run

First of all, you need to create a new network:
```bash
docker network create -d bridge monitoring
```

After that, execute the following command in the root directory of the repo:
```bash
docker-compose up -d
```

Grafana is now available at `localhost:3000` (admin;secret). The password can be changed in the [config.monitoring](./grafana/config.monitoring) file.

## Plugins

I use the following Grafana plugins:
- [Cadvisor exporter](https://grafana.com/grafana/dashboards/14282)
- [Node Exporter Full](https://grafana.com/grafana/dashboards/1860)
# 🚀 Prometheus + Grafana (Docker Compose)

This repository contains a minimal Docker Compose setup to run Prometheus, Grafana and a sample `python-app` exposing metrics.

- 📈 Prometheus: collects metrics
- 📊 Grafana: visualizes dashboards
- 🐳 Docker Compose: runs the stack

![logo](./images/logos.png)

Quick start

Run the stack from the project root:

```bash
docker compose up -d
```

Or (if you use the docker-compose binary):

```bash
docker-compose up -d
```

Available services and ports

- Prometheus: http://localhost:9090 (config: `prometheus.yml`) ✅
- Grafana: http://localhost:3000 (datasources in `provisioning/datasources`) 🎛️
- python-app (example): http://localhost:7590 (metrics at :8590) 🐍
- node-exporter example: :9100 🖥️
- blackbox-exporter: http://localhost:9115 (probes URLs) 🔍

Prometheus configuration

Prometheus reads `prometheus.yml` mounted into the container. Add or adjust `scrape_configs` there to include additional targets (for example the `python-app`).

Notes & next steps ⚙️

- To change the metrics path or port for `python-app`, update `prometheus.yml` and restart the Prometheus container:

```bash
docker compose restart prometheus
```

<h1 id="top" align="center">Monitor Loki</h1>

<br>

<div align="center">
    <img width=auto src="assets/banner/banner.png">
</div>

<br>

## 🔍 Table of Contents

- [About Project](#intro)
- [Dashboard](#dashboard)
- [Technologies](#technologies)
- [Features](#features)
- [Releases](#releases)
- [System Startup](#system-startup)
- [Contributors](#contributors)

<br/>

<h2 id="intro">📌 About Project</h2>

This project simplifies the deployment of Loki, a log aggregation system, using Docker Compose. It includes a pre-configured setup for scraping logs from Promtail and integrates with Grafana for visualization.

<br/>

<h2 id="dashboard">🔥 Dashboard</h2>

<div align="center">
    <img width=800 src="assets/dashboard/dashboard.png">
</div>

<br/>

<h2 id="technologies">☄️ Technologies</h2>

&nbsp; [![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com)

&nbsp; [![Loki](https://img.shields.io/badge/Loki-F2F4F9?style=for-the-badge&logo=grafana&logoColor=orange&labelColor=F2F4F9)](https://grafana.com/docs/loki/latest/send-data/Loki)

&nbsp; [![.Env](https://img.shields.io/badge/.ENV-ECD53F.svg?style=for-the-badge&logo=dotenv&logoColor=black)](https://www.ibm.com/docs/bg/aix/7.2?topic=files-env-file)

<br/>

<h2 id="features">🔥 Features</h2>

- **Docker Containerization:** The application is containerized using Docker to ensure consistent deployment, scalability, and isolation across different environments.
- **Docker Compose Deployment:** Simplifies deployment with Docker Compose configuration, enabling easy setup and service orchestration without complex commands.
- **Persistent Data:** Utilizes a named Docker volume to ensure persistent storage of application data, allowing data to persist across container restarts, rebuilds, and removals.
- **Network Compatibility:** Uses shared Docker network to work with other monitoring tools.
- **.env Configuration:** All environment variables are easily configurable using the `.env` file, simplifying configuration management.
- **Log Scraping:** Preconfigured scraping configuration for Promtail.
- **Traefik Integration:** Promtail collects logs directly from Traefik and push to Loki, enabling easy monitoring of your reverse proxy activity.
- **Grafana Integration:** Loki integrates smoothly with Grafana for visualizing access logs.

<br/>

<h2 id="releases">🚢 Releases</h2>

&nbsp; [![.](https://img.shields.io/badge/1.1.1-233838?style=flat&label=version&labelColor=111727&color=1181A1)](https://github.com/ahmettoguz/monitor-loki/tree/v1.1.1)

&nbsp; [![.](https://img.shields.io/badge/1.1.0-233838?style=flat&label=version&labelColor=111727&color=1181A1)](https://github.com/ahmettoguz/monitor-loki/tree/v1.1.0)

&nbsp; [![.](https://img.shields.io/badge/1.0.0-233838?style=flat&label=version&labelColor=111727&color=1181A1)](https://github.com/ahmettoguz/monitor-loki/tree/v1.0.0)

<br/>

<h2 id="system-startup">🚀 System Startup</h2>

- Create a new directory named `monitor`.

```
mkdir monitor
cd monitor
```

- Clone project.

```
git clone https://github.com/ahmettoguz/monitor-loki
cd monitor-loki
```

- Switch version.

```
git checkout v1.1.1
```

- Create `.env` file based on the `.env.example` file with credentails and configurations.

```
cp .env.example .env
nano .env
```

- Create `network-monitor` network if not exists.

```
docker network create network-monitor
```

- Manage container.

```
docker stop                     container-loki
docker rm                       container-loki
docker volume rm                volume-loki
docker compose -p monitor up -d service-loki
docker logs -f                  container-loki
```

- Refer to [`cAdvisor`](https://github.com/ahmettoguz/monitor-cadvisor) repository to expose contianer metrics.

- Refer to [`Node-Exporter`](https://github.com/ahmettoguz/monitor-node-exporter) repository to expose node metrics.

- Refer to [`Prometheus`](https://github.com/ahmettoguz/monitor-prometheus) repository to integrate prometheus to scrap metrics.

- Refer to [`Promtail`](https://github.com/ahmettoguz/monitor-promtail) repository to push traefik access logs to Loki.

- Refer to [`Traefik`](https://github.com/ahmettoguz/proxy-traefik) repository to expose traefik access logs, metrics and also launch reverse proxy.

- Refer to [`Grafana`](https://github.com/ahmettoguz/monitor-grafana) repository to integrate grafana to visualize logs and metrics.

<br/>

<h2 id="contributors">👥 Contributors</h2>

<a href="https://github.com/ahmettoguz" target="_blank"><img width=60 height=60 src="https://avatars.githubusercontent.com/u/101711642?v=4"></a>

### [🔝](#top)

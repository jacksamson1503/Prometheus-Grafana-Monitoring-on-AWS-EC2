# Prometheus-Grafana-Monitoring-on-AWS-EC2
## Project Overview

This project demonstrates how I set up a monitoring stack on an AWS EC2 Ubuntu server using Prometheus, Node Exporter, and Grafana.

The setup collects real-time server metrics and visualizes them through Grafana dashboards.

---

## Technologies Used

- AWS EC2
- Ubuntu Linux
- Prometheus
- Node Exporter
- Grafana

---

## Architecture

Linux Server
      |
Node Exporter (9100)
      |
Prometheus (9090)
      |
Grafana (3000)

---

## Steps Performed

### 1. Launched AWS EC2 Instance

- Created Ubuntu EC2 instance
- Instance Type: t2.medium
- Connected using SSH

### 2. Configured Security Group

Opened the following ports:

| Port | Purpose |
|--------|----------|
| 22 | SSH |
| 3000 | Grafana |
| 9090 | Prometheus |
| 9100 | Node Exporter |

### 3. Installed Prometheus

Downloaded and configured Prometheus on the EC2 server.

Verified Prometheus UI:

http://PUBLIC-IP:9090

### 4. Installed Node Exporter

Installed Node Exporter for collecting Linux system metrics.

Verified metrics endpoint:

http://PUBLIC-IP:9100/metrics

### 5. Configured Prometheus Targets

Added Node Exporter target in prometheus.yml

```yaml
scrape_configs:
  - job_name: "node_exporter"
    static_configs:
      - targets: ["localhost:9100"]
```

Verified target status:

UP

### 6. Installed Grafana

Installed Grafana and connected it with Prometheus.

Accessed Grafana:

http://PUBLIC-IP:3000

### 7. Imported Dashboard

Imported Node Exporter Full Dashboard.

Monitored:

- CPU Usage
- Memory Usage
- Disk Usage
- Network Traffic
- Uptime
- System Load

---

## Validation

### Prometheus Targets

- Prometheus : UP
- Node Exporter : UP

### Node Exporter Metrics

Successfully exposed metrics through:

http://PUBLIC-IP:9100/metrics

### Grafana Dashboard

Successfully visualized Linux server metrics using Grafana dashboards.

---

## Screenshots

### AWS EC2 Instance Running

<img width="1898" height="973" alt="ec2" src="https://github.com/user-attachments/assets/56d0e7e0-cc1e-4aea-9473-c401ce0e3579" />


### Security Group Configuration

<img width="1897" height="952" alt="security group" src="https://github.com/user-attachments/assets/a5ed8737-b078-4a8a-9da6-a2797481c14d" />

### Prometheus Targets

<img width="1917" height="1083" alt="promo targets" src="https://github.com/user-attachments/assets/229449db-bbc2-48db-8d26-0d28f7f64ea7" />

### Node Exporter Metrics

<img width="1917" height="1083" alt="metrics" src="https://github.com/user-attachments/assets/a5249b4d-56f2-45f0-bcd3-aebb92d639cf" />

### Grafana Dashboard

<img width="1906" height="1073" alt="grafana" src="https://github.com/user-attachments/assets/60b615f2-854c-4ce2-b039-f661ea4c0044" />

## Skills Demonstrated

- AWS EC2
- Linux Administration
- Prometheus Monitoring
- Grafana Dashboarding
- Node Exporter
- Networking
- Security Groups
- Infrastructure Monitoring





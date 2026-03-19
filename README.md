# Cloud Monitoring & Self-Healing Infrastructure 🚀

A DevOps monitoring system built using Prometheus, Grafana, and Node Exporter to track application and system metrics in real time.

---

## 📌 Project Overview

This project demonstrates how to build a cloud monitoring stack on AWS that collects metrics from applications and servers, visualizes them in dashboards, and enables automated monitoring.

The system monitors:

- Application metrics
- CPU usage
- Memory usage
- Disk usage
- Network traffic
- Service health

---

## 🏗 Architecture

<img width="850" height="1100" alt="Cloud Monitoring Architecture " src="https://github.com/user-attachments/assets/9c5142c9-abf8-4811-bd9a-1349a6612242" />


---

## ⚙️ Tech Stack

- AWS EC2
- Linux (Ubuntu)
- Prometheus
- Grafana
- Node Exporter
- Python
- Flask
- Prometheus Client Library

---

## 🔄 Monitoring Flow

User Browser → Grafana Dashboard  
Grafana → Queries Prometheus  
Prometheus → Scrapes metrics from:

- Flask Application
- Node Exporter

---

## 📊 Components

### 1. Flask Application
A Python application exposing custom metrics using Prometheus client.

Metrics exposed:
- Total requests
- Application health

Runs on:localhost:5000

---

### 2. Prometheus
Collects and stores metrics from exporters.

Runs on:localhost:9090

---

### 3. Node Exporter
Collects system metrics such as:

- CPU
- Memory
- Disk
- Network

Runs on:localhost:9100

---

### 4. Grafana
Visualizes monitoring data using dashboards.

Runs on:localhost:3000
<img width="1918" height="847" alt="prometheus" src="https://github.com/user-attachments/assets/d425346f-4fc5-4152-909e-5155ab52df70" />
<img width="1893" height="856" alt="grafana" src="https://github.com/user-attachments/assets/f019fc48-b95c-4ab2-9451-7143f6c73997" />

---

## 🚀 How to Run the Project

### Clone the repository

```bash
git clone https://github.com/yourusername/cloud-monitoring-project.git
cd cloud-monitoring-project
1.Start Flask Application
```bash
python3 app.py
2.Start Prometheus
```bash
./prometheus --config.file=prometheus.yml
3.Start Node Exporter
```bash
./node_exporter
4.Start Grafana
```bash
sudo systemctl start grafana-server
Access the Services
1.Grafana Dashboard
```bash
http://<EC2-PUBLIC-IP>:3000
2.Prometheus
```bash
http://<EC2-PUBLIC-IP>:9090

# 🚀 Introduction to Prometheus

---

## 📌 Introduction

In modern DevOps, monitoring systems need to be **fast, reliable, and scalable**.

👉 This is where **Prometheus** comes in.

Prometheus is one of the most popular **open-source monitoring tools** used in cloud-native environments.

---

## 🎯 What is Prometheus?

Prometheus is an **open-source monitoring and alerting toolkit** designed for:

- 📊 Collecting metrics  
- 📈 Storing time-series data  
- 🚨 Triggering alerts  

👉 Originally developed at :contentReference[oaicite:0]{index=0}

---

## 🧠 Key Features of Prometheus

---

### 📊 1️⃣ Time-Series Database

- Stores data with timestamps ⏰  
- Example:
```text
CPU Usage → 10:00 (40%), 10:05 (60%)
```

---

### 🔄 2️⃣ Pull-Based Model

- Prometheus **pulls metrics** from targets  
- Uses HTTP endpoints  

👉 More reliable than push-based systems

---

### 🔍 3️⃣ Powerful Query Language (PromQL)

- Used to query and analyze metrics  
- Example:
```text
rate(http_requests_total[1m])
```

---

### 🚨 4️⃣ Built-in Alerting

- Sends alerts based on conditions  
- Integrated with Alertmanager  

---

### 📦 5️⃣ Multi-Dimensional Data Model

- Metrics stored with **labels (key-value pairs)**  
- Example:
```text
http_requests_total{status="200", method="GET"}
```

---

## 🧩 How Prometheus Works

```text
Targets (Servers, Apps)
        ↓
   Exporters
        ↓
   Prometheus Server
        ↓
 Storage (Time-Series DB)
        ↓
   Grafana / Alerts
```

---

## 🛠️ Components of Prometheus

---

### 🖥️ 1️⃣ Prometheus Server

- Core component  
- Scrapes and stores metrics  

---

### 📡 2️⃣ Exporters

- Convert system data into Prometheus format  
- Example:
  - Node Exporter (system metrics)

---

### ⚙️ 3️⃣ Alertmanager

- Handles alerts  
- Sends notifications (Email, Slack)

---

### 📊 4️⃣ Grafana

- Visualizes metrics using dashboards  

---

## ⚙️ Example: Basic Prometheus Configuration

```yaml
# prometheus.yml

global:
  scrape_interval: 15s  # Collect metrics every 15 seconds

scrape_configs:
  - job_name: 'node'
    static_configs:
      - targets: ['localhost:9100']
```

### 📖 Explanation:
- `scrape_interval` → How often metrics are collected  
- `job_name` → Name of monitoring job  
- `targets` → Systems to monitor  

👉 This config collects metrics from **Node Exporter**

---

## ⚙️ Example: Running Prometheus (Docker)

```bash
# Run Prometheus container
docker run -d \
  -p 9090:9090 \
  -v /path/to/prometheus.yml:/etc/prometheus/prometheus.yml \
  prom/prometheus
```

### 📖 Explanation:
- `-p 9090:9090` → Exposes UI  
- `-v` → Mount config file  
- `prom/prometheus` → Official image  

👉 Access UI at: `http://localhost:9090`

---

## 🚨 Why Prometheus is Important?

- 🔥 Industry standard monitoring tool  
- ⚡ High performance  
- ☁️ Works well with Kubernetes  
- 📊 Powerful querying with PromQL  
- 🚨 Built-in alerting system  

---

## ⚠️ Limitations

- ❌ Not ideal for long-term storage  
- ❌ Limited log support (metrics-focused)  

👉 Usually combined with other tools like Grafana, Loki

---

## 🧪 Interview Questions

### ❓ What is Prometheus?

Prometheus is an open-source monitoring and alerting tool used to collect and analyze metrics.

---

### ❓ What is the pull model in Prometheus?

Prometheus pulls metrics from targets using HTTP endpoints.

---

### ❓ What is PromQL?

PromQL is the query language used to query and analyze metrics in Prometheus.

---

## 🚀 Summary

- Prometheus = Monitoring + Alerting tool 📊  
- Uses pull-based model 🔄  
- Stores time-series data ⏰  
- Uses PromQL for querying 🔍  
- Works with Grafana for visualization 📈  

👉 **Prometheus is the backbone of modern monitoring systems**

---

## 🤝 Contribute

Contributions are welcome!  

If you find any improvements, feel free to fork the repository and submit a pull request.

---


# 🚀 Node Exporter Setup

---

## 📌 Introduction

To monitor system-level metrics like CPU, memory, and disk, Prometheus needs a way to collect data from machines.

👉 This is done using **Node Exporter**

Node Exporter exposes **hardware and OS metrics** in a format that Prometheus can understand.

---

## 🎯 What is Node Exporter?

Node Exporter is an **exporter for machine-level metrics**

👉 It provides data like:
- CPU usage 🔥  
- Memory usage 🧠  
- Disk usage 💾  
- Network stats 🌐  

👉 Runs as a service on the system

---

## 🧠 How It Works

```text
Node Exporter → /metrics endpoint → Prometheus → Dashboard (Grafana)
```

👉 Prometheus **scrapes data** from Node Exporter

---

## ⚙️ Step-by-Step Setup (Linux)

---

### 🔽 1️⃣ Download Node Exporter

```bash
# Download latest version
wget https://github.com/prometheus/node_exporter/releases/latest/download/node_exporter-*.linux-amd64.tar.gz
```

---

### 📦 2️⃣ Extract Files

```bash
tar -xvf node_exporter-*.linux-amd64.tar.gz
cd node_exporter-*.linux-amd64
```

---

### ▶️ 3️⃣ Run Node Exporter

```bash
./node_exporter
```

👉 Runs on:
```text
http://localhost:9100/metrics
```

---

### 🔍 4️⃣ Verify Metrics

Open browser:
```text
http://localhost:9100/metrics
```

👉 You will see system metrics in text format

---

## ⚙️ Run as a Service (Recommended 🔥)

---

### 📝 Create Service File

```bash
sudo nano /etc/systemd/system/node_exporter.service
```

---

### 📄 Add Configuration

```ini
[Unit]
Description=Node Exporter
After=network.target

[Service]
User=nobody
ExecStart=/path/to/node_exporter

[Install]
WantedBy=default.target
```

---

### ▶️ Start Service

```bash
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl start node_exporter
sudo systemctl enable node_exporter
```

---

### 🔍 Check Status

```bash
sudo systemctl status node_exporter
```

---

## ⚙️ Configure Prometheus

Add Node Exporter as a target:

```yaml
scrape_configs:
  - job_name: 'node_exporter'
    static_configs:
      - targets: ['localhost:9100']
```

👉 Now Prometheus will collect system metrics

---

## 📊 Common Metrics Exposed

- `node_cpu_seconds_total` → CPU usage  
- `node_memory_MemAvailable_bytes` → Available memory  
- `node_disk_io_time_seconds_total` → Disk activity  
- `node_network_receive_bytes_total` → Network traffic  

---

## 🚨 Why Node Exporter is Important?

- 📊 Provides system-level metrics  
- ⚡ Lightweight and efficient  
- 🔌 Easy integration with Prometheus  
- ☁️ Works across environments  

---

## ⚠️ Best Practices

- ✅ Run as a system service  
- ✅ Secure endpoint (if public)  
- ✅ Monitor multiple nodes  
- ✅ Use labels for identification  

---

## 🧪 Interview Questions

### ❓ What is Node Exporter?

Node Exporter is a tool that exposes system-level metrics for Prometheus.

---

### ❓ On which port does Node Exporter run?

By default, it runs on port 9100.

---

### ❓ How does Prometheus collect Node Exporter data?

Prometheus scrapes metrics from the `/metrics` endpoint.

---

## 🚀 Summary

- Node Exporter collects system metrics 📊  
- Runs on port 9100 🌐  
- Exposes `/metrics` endpoint 🔍  
- Prometheus scrapes data from it 🔄  

👉 **Essential tool for infrastructure monitoring**

---

## 🤝 Contribute

Contributions are welcome!  

If you find any improvements, feel free to fork the repository and submit a pull request.

---



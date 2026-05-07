# 🚀 Introduction to Grafana

---

## 📌 Introduction

Collecting metrics is important, but raw numbers are difficult to understand ❌

👉 We need a way to visualize data using:
- 📊 Dashboards  
- 📈 Graphs  
- 🚨 Alerts  

This is where **Grafana** comes in 🔥

---

## 🎯 What is Grafana?

Grafana is an **open-source visualization and monitoring platform**

👉 It helps visualize data from monitoring tools like:
- Prometheus  
- Elasticsearch  
- Loki  
- InfluxDB  

---

## 🧠 Why Grafana is Popular?

Grafana is widely used because it provides:

- 📊 Beautiful dashboards  
- ⚡ Real-time monitoring  
- 🔔 Alerting system  
- 🔌 Multiple data source support  
- ☁️ Cloud-native compatibility  

---

## 🧩 How Grafana Works

```text
Data Source → Grafana → Dashboards & Alerts
```

👉 Grafana does not collect metrics directly  
👉 It visualizes data from external sources

---

## 📊 Common Data Sources

| Data Source | Purpose |
|------------|---------|
| Prometheus 📈 | Metrics monitoring |
| Loki 📜 | Log monitoring |
| Elasticsearch 🔍 | Search & analytics |
| MySQL 🗄️ | Database data |
| CloudWatch ☁️ | AWS monitoring |

---

## 🖥️ Main Components of Grafana

---

### 📊 1️⃣ Dashboards

- Collection of visual panels  
- Shows system metrics in one place  

👉 Example:
- CPU usage  
- Memory usage  
- Network traffic  

---

### 📈 2️⃣ Panels

Individual visualization components

#### 📊 Examples:
- Graphs  
- Tables  
- Gauges  
- Heatmaps  

---

### 🔌 3️⃣ Data Sources

Connections to external monitoring systems

👉 Example:
- Prometheus  
- Loki  

---

### 🚨 4️⃣ Alerting

Grafana can send alerts when conditions are met

#### 📢 Example:
- CPU > 80%  
- Server down  

---

## ⚙️ Install Grafana Using Docker

```bash
# Run Grafana container

docker run -d \
  --name=grafana \
  -p 3000:3000 \
  grafana/grafana
```

---

### 📖 Explanation:
- `-d` → Run in background  
- `-p 3000:3000` → Expose Grafana UI  
- `grafana/grafana` → Official image  

👉 Access Grafana at:
```text
http://localhost:3000
```

---

## 🔐 Default Login Credentials

```text
Username: admin
Password: admin
```

👉 Grafana will ask to change password after first login

---

## ⚙️ Connect Prometheus to Grafana

---

### 📝 Steps:

1️⃣ Open Grafana UI  
2️⃣ Go to:
```text
Connections → Data Sources
```

3️⃣ Select:
```text
Prometheus
```

4️⃣ Add Prometheus URL:
```text
http://localhost:9090
```

5️⃣ Click:
```text
Save & Test
```

👉 Grafana is now connected to Prometheus 🎉

---

## 📊 Example Dashboard Metrics

- CPU usage 🔥  
- Memory usage 🧠  
- Disk usage 💾  
- Request latency ⏱️  
- Error rate ❌  

---

## 🚨 Why Grafana is Important?

- 📈 Makes monitoring easy to understand  
- ⚡ Real-time visualization  
- 🔔 Powerful alerting system  
- ☁️ Essential in DevOps & Kubernetes  

---

## ⚠️ Best Practices

- ✅ Organize dashboards properly  
- ✅ Use meaningful panel names  
- ✅ Avoid too many graphs in one dashboard  
- ✅ Set proper alert thresholds  

---

## 🧪 Interview Questions

### ❓ What is Grafana?

Grafana is an open-source platform used for data visualization, dashboards, and monitoring.

---

### ❓ Does Grafana collect metrics?

No, Grafana only visualizes data from external sources.

---

### ❓ Which monitoring tool is commonly used with Grafana?

Prometheus is the most commonly used data source with Grafana.

---

## 🚀 Summary

- Grafana = Visualization platform 📊  
- Used for dashboards & alerts 📈  
- Works with Prometheus and other data sources 🔌  
- Essential for modern monitoring systems 🚀  

👉 **Grafana transforms raw metrics into meaningful insights**

---

## 🤝 Contribute

Contributions are welcome!  

If you find any improvements, feel free to fork the repository and submit a pull request.

---

## 👨‍💻 Author

**Aditya Jadhav**  
Beginner Cloud & DevOps Learner  

📧 adijadhav8446@gmail.com  
🌐 https://github.com/AdiJadhav1608  
🔗 https://www.linkedin.com/in/aditya-jadhav-718087339/

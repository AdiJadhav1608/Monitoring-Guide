# 🚀 Grafana Dashboards

---

## 📌 Introduction

Monitoring data is useful only when it is easy to understand.

👉 Grafana Dashboards help visualize monitoring data using:
- 📊 Graphs  
- 📈 Charts  
- 📉 Gauges  
- 📋 Tables  

Dashboards provide a **centralized view of system health and performance**

---

## 🎯 What is a Grafana Dashboard?

A Grafana Dashboard is a collection of **visual panels** used to display monitoring data.

👉 It helps users:
- Monitor systems in real-time ⚡  
- Analyze performance 📊  
- Detect issues quickly 🚨  

---

## 🧠 Real-World Example

A DevOps team dashboard may contain:

- CPU usage 🔥  
- Memory usage 🧠  
- Disk usage 💾  
- Network traffic 🌐  
- API response time ⏱️  

👉 All in one place 🎯

---

## 🧩 Dashboard Components

---

### 📊 1️⃣ Panels

Panels are the individual visualization blocks inside dashboards.

#### 📈 Examples:
- Time-series graph  
- Gauge chart  
- Table  
- Heatmap  

---

### 🔌 2️⃣ Data Source

Dashboards pull data from connected sources like:
- Prometheus  
- Loki  
- Elasticsearch  

---

### 🏷️ 3️⃣ Variables

Variables make dashboards dynamic and reusable.

#### 🧠 Example:
```text
Select Server → server1 / server2
```

👉 Changes dashboard data dynamically

---

### ⏱️ 4️⃣ Time Range

Controls the time period for displayed data.

#### 📊 Example:
- Last 5 minutes  
- Last 1 hour  
- Last 24 hours  

---

## ⚙️ Creating a Dashboard

---

### 📝 Step 1️⃣ Open Grafana

Go to:
```text
http://localhost:3000
```

---

### 📝 Step 2️⃣ Create Dashboard

Navigate:
```text
Dashboards → New Dashboard
```

---

### 📝 Step 3️⃣ Add Visualization

Click:
```text
Add Visualization
```

Select your data source:
```text
Prometheus
```

---

### 📝 Step 4️⃣ Add Query

Example PromQL query:

```text
rate(node_cpu_seconds_total[1m])
```

👉 Displays CPU usage metrics

---

### 📝 Step 5️⃣ Save Dashboard

Add:
- Dashboard name  
- Description  

👉 Dashboard is now ready 🎉

---

## 📊 Common Dashboard Panels

| Panel Type | Purpose |
|------------|---------|
| Time Series 📈 | Show trends over time |
| Gauge 📊 | Current metric value |
| Stat 🔢 | Single numeric value |
| Table 📋 | Structured data |
| Heatmap 🌡️ | Data distribution |

---

## ⚙️ Example Dashboard JSON

```json
{
  "title": "System Monitoring Dashboard",
  "panels": [
    {
      "type": "graph",
      "title": "CPU Usage"
    }
  ]
}
```

### 📖 Explanation:
- `title` → Dashboard name  
- `panels` → Visualization components  
- `graph` → Graph panel type  

👉 Grafana stores dashboards in JSON format

---

## 🚨 Dashboard Best Practices

- ✅ Keep dashboards simple  
- ✅ Group related metrics together  
- ✅ Use meaningful titles  
- ✅ Avoid too many panels  
- ✅ Use alert thresholds  

---

## ⚠️ Common Mistakes

❌ Too much information in one dashboard  
👉 Creates confusion  

❌ No labels or titles  
👉 Difficult to understand  

❌ Wrong time range  
👉 Misleading analysis  

---

## 🧪 Interview Questions

### ❓ What is a Grafana dashboard?

A Grafana dashboard is a collection of visual panels used to monitor and analyze data.

---

### ❓ What are panels in Grafana?

Panels are visualization components like graphs, tables, and gauges.

---

### ❓ Which data source is commonly used with Grafana dashboards?

Prometheus is one of the most commonly used data sources.

---

## 🚀 Summary

- Grafana dashboards visualize monitoring data 📊  
- Panels display graphs, gauges, tables 📈  
- Dashboards provide centralized monitoring 🔍  
- Helps analyze performance in real-time ⚡  

👉 **Dashboards transform metrics into actionable insights**

---

## 🤝 Contribute

Contributions are welcome!  

If you find any improvements, feel free to fork the repository and submit a pull request.

---

## 👨‍💻 Author


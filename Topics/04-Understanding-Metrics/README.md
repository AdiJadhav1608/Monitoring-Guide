# 🚀 Understanding Metrics

---

## 📌 Introduction

Metrics are the **foundation of monitoring systems**.

They provide **numerical data over time** that helps us understand system performance and behavior.

👉 In simple terms:  
**Metrics = Numbers that tell how your system is performing 📊**

---

## 🎯 What are Metrics?

Metrics are **quantitative measurements** collected at regular intervals.

### 📊 Examples:
- CPU usage (%) 🔥  
- Memory usage (MB/GB) 🧠  
- Request count 📈  
- Response time (ms) ⏱️  

👉 These values help track system health continuously

---

## 🧠 Real-World Example

Imagine a **web application**:

- Requests per second = 500 📈  
- Response time = 200ms ⏱️  
- Error rate = 2% ❌  

👉 If response time increases to 2 seconds:
- System is slow ⚠️  
- Users get frustrated 😓  

👉 Metrics help detect this instantly

---

## 🧩 Key Characteristics of Metrics

---

### 1️⃣ Time-Based Data ⏳

Metrics are always tracked **over time**

👉 Example:
```text
CPU Usage:
10:00 → 40%
10:05 → 60%
10:10 → 85%
```

---

### 2️⃣ Numerical Values 🔢

Metrics are always **numbers**

👉 No text, only measurable values

---

### 3️⃣ Continuous Collection 🔄

Metrics are collected **continuously at intervals**

👉 Example:
- Every 5 seconds  
- Every 1 minute  

---

### 4️⃣ Stored in Time-Series Databases 📦

Metrics are stored in systems like:
- Prometheus  
- InfluxDB  

👉 Called **Time-Series Data**

---

## 🏷️ Metric Structure (Important 🔥)

A metric usually has:

```text
metric_name{label="value"} = number
```

### 🧠 Example:
```text
http_requests_total{status="200"} = 1500
```

### 📖 Explanation:
- `http_requests_total` → Metric name  
- `status="200"` → Label (extra info)  
- `1500` → Value  

👉 Labels help filter and analyze data easily

---

## 📊 Common Use Cases of Metrics

- ⚡ Performance monitoring (CPU, memory)
- 🌐 API monitoring (requests, latency)
- 📈 Traffic analysis
- 🚨 Alerting (threshold-based)

---

## ⚙️ Example: Collecting CPU Metrics (Linux)

```bash
#!/bin/bash

# This script collects CPU usage every 5 seconds

while true
do
    CPU=$(top -bn1 | grep "Cpu(s)" | awk '{print $2 + $4}')
    
    echo "CPU Usage: $CPU%"
    
    sleep 5
done
```

### 📖 Explanation:
- `while true` → Runs continuously  
- `top` → Gets CPU data  
- `sleep 5` → Runs every 5 seconds  

👉 This simulates **continuous metric collection**

---

## 🧪 Interview Questions

### ❓ What are metrics?

Metrics are numerical data points collected over time to measure system performance and health.

---

### ❓ Why are metrics important?

They help track performance, detect issues, and enable data-driven decisions.

---

### ❓ What is a time-series metric?

A metric that is recorded with timestamps over time.

---

### ❓ What are labels in metrics?

Labels are key-value pairs that provide additional information about a metric.

---

## 🚀 Summary

- Metrics = Numerical performance data 📊  
- Collected continuously over time ⏳  
- Stored as time-series data 📦  
- Used for monitoring, alerting, and analysis 🚨  

👉 **Metrics are the backbone of monitoring systems**

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

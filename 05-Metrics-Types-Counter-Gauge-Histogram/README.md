# 🚀 Metrics Types: Counter, Gauge, Histogram

---

## 📌 Introduction

Not all metrics are the same — they are categorized into **different types based on how data behaves**.

👉 The most important metric types used in monitoring systems are:
- Counter 📈  
- Gauge 📊  
- Histogram 📉  

These are widely used in tools like **Prometheus**

---

## 🎯 Why Metric Types Matter?

Choosing the correct metric type helps:
- 📊 Accurate data collection  
- ⚡ Better analysis  
- 🚨 Correct alerting  

👉 Wrong metric type = Wrong insights ❌

---

## 📈 1️⃣ Counter

### 📌 Definition

A Counter is a metric that **only increases (or resets to zero)**

👉 It never decreases

---

### 📊 Examples:
- Total number of requests  
- Total errors  
- Number of logins  

---

### 🧠 Real-World Example

```text
http_requests_total:
100 → 200 → 350 → 500
```

👉 Always increasing 📈

---

### ⚙️ Example Code (Python)

```python
# Counter example using Prometheus client

from prometheus_client import Counter

# Create a counter metric
request_count = Counter('http_requests_total', 'Total HTTP Requests')

# Simulate requests
request_count.inc()      # +1
request_count.inc(5)     # +5
```

### 📖 Explanation:
- `Counter()` → Creates a counter metric  
- `.inc()` → Increments value  
- Only increases, never decreases  

---

## 📊 2️⃣ Gauge

### 📌 Definition

A Gauge is a metric that **can increase or decrease**

👉 Represents current value

---

### 📊 Examples:
- CPU usage  
- Memory usage  
- Active users  

---

### 🧠 Real-World Example

```text
CPU Usage:
40% → 70% → 55% → 80% → 30%
```

👉 Can go up ⬆️ and down ⬇️

---

### ⚙️ Example Code (Python)

```python
# Gauge example using Prometheus client

from prometheus_client import Gauge

# Create a gauge metric
cpu_usage = Gauge('cpu_usage_percent', 'Current CPU Usage')

# Set values
cpu_usage.set(50)
cpu_usage.set(75)
cpu_usage.set(30)
```

### 📖 Explanation:
- `Gauge()` → Creates gauge metric  
- `.set()` → Assigns value  
- Value can increase or decrease  

---

## 📉 3️⃣ Histogram

### 📌 Definition

A Histogram measures **distribution of values over time**

👉 It groups data into **buckets**

---

### 📊 Examples:
- Request duration  
- Response size  
- Latency  

---

### 🧠 Real-World Example

```text
Request Duration:
<100ms → 50 requests
100–300ms → 30 requests
>300ms → 20 requests
```

👉 Shows distribution of response times

---

### ⚙️ Example Code (Python)

```python
# Histogram example using Prometheus client

from prometheus_client import Histogram

# Create histogram metric
request_latency = Histogram('request_duration_seconds', 'Request latency')

# Observe values
request_latency.observe(0.2)
request_latency.observe(0.5)
request_latency.observe(1.2)
```

### 📖 Explanation:
- `Histogram()` → Creates histogram  
- `.observe()` → Records value  
- Data is grouped into buckets  

---

## 🔥 Quick Comparison

| Metric Type | Behavior | Example | Use Case |
|------------|--------|--------|---------|
| Counter 📈 | Only increases | Total requests | Count events |
| Gauge 📊 | Up & Down | CPU usage | Current state |
| Histogram 📉 | Distribution | Request time | Performance analysis |

---

## ⚠️ Common Mistakes

❌ Using Counter for CPU usage  
👉 CPU changes → Use Gauge  

❌ Using Gauge for total requests  
👉 Requests only increase → Use Counter  

👉 Always choose correct metric type

---

## 🧪 Interview Questions

### ❓ What is a Counter metric?

A metric that only increases over time and is used to count events.

---

### ❓ What is the difference between Gauge and Counter?

Gauge can increase and decrease, while Counter only increases.

---

### ❓ What is a Histogram used for?

It is used to measure the distribution of values like latency or response time.

---

## 🚀 Summary

- Counter → Increasing values 📈  
- Gauge → Variable values 📊  
- Histogram → Distribution of data 📉  

👉 **Correct metric type = Accurate monitoring**

---

## 🤝 Contribute

Contributions are welcome!  

If you find any improvements, feel free to fork the repository and submit a pull request.

---

## 👨‍💻 Author

**Aditya Jadhav**  
Beginner Cloud & DevOps Learner  



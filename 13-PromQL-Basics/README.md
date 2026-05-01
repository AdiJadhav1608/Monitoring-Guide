# 🚀 PromQL Basics

---

## 📌 Introduction

Collecting metrics is not enough — we need a way to **query and analyze them**.

👉 That’s where **PromQL (Prometheus Query Language)** comes in.

PromQL is a powerful language used to **retrieve and manipulate time-series data** in Prometheus.

---

## 🎯 What is PromQL?

PromQL is the query language used in Prometheus to:

- 📊 Fetch metrics  
- 📈 Analyze data  
- 🚨 Create alerts  
- 📉 Perform calculations  

👉 In simple terms:  
**PromQL = SQL for monitoring data 🔍**

---

## 🧠 Basic Query Structure

```text
metric_name{label="value"}
```

### 📊 Example:
```text
http_requests_total{status="200"}
```

### 📖 Explanation:
- `http_requests_total` → Metric name  
- `status="200"` → Filter using label  

---

## 📊 Types of PromQL Data

---

### 1️⃣ Instant Vector

- Value at a **single point in time**

#### Example:
```text
cpu_usage
```

---

### 2️⃣ Range Vector

- Values over a **time range**

#### Example:
```text
cpu_usage[5m]
```

👉 Last 5 minutes data

---

### 3️⃣ Scalar

- Single numeric value  

#### Example:
```text
5
```

---

## 🔥 Common PromQL Functions

---

### 📈 1️⃣ rate()

- Calculates per-second rate of increase  

#### Example:
```text
rate(http_requests_total[1m])
```

👉 Requests per second over 1 minute

---

### 📊 2️⃣ sum()

- Adds values  

#### Example:
```text
sum(cpu_usage)
```

---

### 📉 3️⃣ avg()

- Calculates average  

#### Example:
```text
avg(cpu_usage)
```

---

### 🔢 4️⃣ count()

- Counts number of elements  

#### Example:
```text
count(http_requests_total)
```

---

## 🎯 Filtering with Labels

```text
metric_name{label1="value1", label2="value2"}
```

### 🧠 Example:
```text
http_requests_total{method="GET", status="500"}
```

👉 Filters only GET requests with error status

---

## ⚙️ Aggregation Example

```text
sum(rate(http_requests_total[1m]))
```

### 📖 Explanation:
- `rate()` → Requests per second  
- `sum()` → Total across all instances  

---

## ⚙️ Example: CPU Usage Query

```text
avg(rate(cpu_usage[1m])) * 100
```

👉 Gives average CPU usage percentage

---

## 🚨 PromQL in Alerting

```yaml
# Alert rule example

- alert: HighCPUUsage
  expr: avg(rate(cpu_usage[1m])) > 0.8
  for: 1m
  labels:
    severity: critical
  annotations:
    description: "CPU usage is above 80%"
```

### 📖 Explanation:
- `expr` → Condition  
- `for` → Duration  
- Alert triggers if condition is true  

---

## ⚠️ Common Mistakes

❌ Forgetting time range in `rate()`  
👉 Always use `[1m]`, `[5m]`  

❌ Wrong label filtering  
👉 Leads to incorrect results  

❌ Overusing complex queries  
👉 Impacts performance  

---

## 🧪 Interview Questions

### ❓ What is PromQL?

PromQL is the query language used in Prometheus to query and analyze metrics.

---

### ❓ What is the difference between instant and range vector?

Instant vector represents a single timestamp, while range vector represents data over time.

---

### ❓ What does rate() function do?

It calculates the per-second rate of increase of a metric.

---

## 🚀 Summary

- PromQL = Query language for Prometheus 🔍  
- Used for querying, analyzing, and alerting 📊  
- Supports functions like rate, sum, avg 📈  
- Uses labels for filtering 🏷️  

👉 **PromQL turns raw metrics into meaningful insights**

---

## 🤝 Contribute

Contributions are welcome!  

If you find any improvements, feel free to fork the repository and submit a pull request.

---

## 👨‍💻 Author


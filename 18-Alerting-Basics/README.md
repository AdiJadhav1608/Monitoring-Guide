# 🚀 Alerting Basics

---

## 📌 Introduction

Monitoring helps collect system data, but continuously checking dashboards manually is impossible ❌

👉 We need a way to get notified automatically when something goes wrong.

This is where **Alerting** comes in 🚨

---

## 🎯 What is Alerting?

Alerting is the process of:

👉 **Sending notifications when predefined conditions are met**

These conditions are based on:
- CPU usage 🔥  
- Memory usage 🧠  
- Error rates ❌  
- Service downtime 🌐  

---

## 🧠 Real-World Example

Imagine a production server:

```text
CPU Usage = 95%
```

👉 Without alerting:
- Nobody notices issue ❌  
- Server may crash 💀  

👉 With alerting:
- Notification sent instantly 🚨  
- Team fixes issue quickly ⚡  

---

## 🧩 Key Components of Alerting

---

### 📊 1️⃣ Metrics

Alerts are based on monitoring metrics.

#### 📈 Examples:
- CPU usage  
- Memory usage  
- Request latency  

---

### ⚙️ 2️⃣ Alert Rules

Conditions that trigger alerts.

#### 🧠 Example:
```text
CPU > 80%
```

---

### 🔔 3️⃣ Notification Channels

Where alerts are sent.

#### 📢 Examples:
- Email 📧  
- Slack 💬  
- Microsoft Teams  
- PagerDuty  

---

### 🚨 4️⃣ Alert Manager

Handles:
- Alert routing  
- Grouping  
- Deduplication  

👉 In Prometheus, this is handled by **Alertmanager**

---

## 🔄 Alerting Workflow

```text
Metrics → Alert Rule → Alertmanager → Notification
```

👉 Complete alert flow 🔍

---

## ⚙️ Example: Prometheus Alert Rule

```yaml
groups:
  - name: cpu_alerts
    rules:
      - alert: HighCPUUsage
        expr: avg(rate(node_cpu_seconds_total[1m])) > 0.8
        for: 1m
        labels:
          severity: critical
        annotations:
          summary: "High CPU Usage Detected"
```

---

## 📖 Explanation

- `alert` → Alert name  
- `expr` → Alert condition  
- `for` → Condition duration  
- `severity` → Alert priority  
- `summary` → Alert message  

👉 Alert triggers if CPU usage stays above 80% for 1 minute

---

## 📊 Types of Alerts

---

### 🚨 1️⃣ Threshold Alerts

Triggered when value crosses a limit.

#### 🧠 Example:
```text
Memory Usage > 90%
```

---

### ❌ 2️⃣ Availability Alerts

Triggered when service becomes unavailable.

#### 🧠 Example:
```text
Website Down
```

---

### ⏱️ 3️⃣ Latency Alerts

Triggered when response time increases.

#### 🧠 Example:
```text
API response time > 2 seconds
```

---

### 🔐 4️⃣ Security Alerts

Triggered for suspicious activities.

#### 🧠 Example:
```text
Multiple failed login attempts
```

---

## 🚨 Alert Severity Levels

| Severity | Meaning |
|----------|---------|
| Info ℹ️ | Informational |
| Warning ⚠️ | Potential issue |
| Critical 🔥 | Immediate action required |

---

## ⚠️ Alert Fatigue (Important 🔥)

Too many unnecessary alerts cause:
- Ignored alerts ❌  
- Delayed response ❌  
- Team frustration 😓  

👉 This is called **Alert Fatigue**

---

## ✅ Best Practices

- ✅ Create meaningful alerts  
- ✅ Avoid unnecessary alerts  
- ✅ Set proper thresholds  
- ✅ Use severity levels  
- ✅ Test alerts regularly  

---

## ⚠️ Common Mistakes

❌ Alert for every small issue  
👉 Creates noise  

❌ No severity classification  
👉 Hard to prioritize  

❌ Wrong thresholds  
👉 Too many false alerts  

---

## 🧪 Interview Questions

### ❓ What is alerting?

Alerting is the process of notifying teams when predefined monitoring conditions are met.

---

### ❓ What is Alertmanager?

Alertmanager is a Prometheus component that manages and routes alerts.

---

### ❓ What is alert fatigue?

Alert fatigue occurs when too many unnecessary alerts cause important alerts to be ignored.

---

## 🚀 Summary

- Alerting provides automatic notifications 🚨  
- Based on predefined monitoring conditions 📊  
- Helps detect issues quickly ⚡  
- Alertmanager handles routing & notifications 🔔  

👉 **Good alerting improves system reliability and response time**

---

## 🤝 Contribute

Contributions are welcome!  

If you find any improvements, feel free to fork the repository and submit a pull request.

---

## 👨‍💻 Author



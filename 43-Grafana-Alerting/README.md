# 🚀 Grafana Alerting

---

## 📌 Introduction

Dashboards help us visualize system metrics, but engineers cannot watch dashboards 24×7.

Imagine:

```text
CPU Usage = 95%

Memory Usage = 90%

Application Down
```

If nobody is looking at the dashboard, the problem may remain unnoticed.

👉 This is where **Grafana Alerting** becomes important.

Grafana Alerting continuously evaluates metrics and automatically sends notifications whenever problems occur.

---

# 🎯 What is Grafana Alerting?

Grafana Alerting is a feature that allows Grafana to:

✅ Monitor metrics

✅ Evaluate conditions

✅ Trigger alerts

✅ Send notifications

It helps DevOps and SRE teams detect incidents automatically.

---

# 🧠 Why Grafana Alerting is Important?

Without alerts:

❌ Engineers must manually check dashboards.

❌ Issues may remain undetected.

❌ Downtime may increase.

With alerts:

✅ Faster incident response

✅ Reduced downtime

✅ Better reliability

✅ Improved system availability

---

# 🔄 How Grafana Alerting Works

```text
Prometheus / Data Source
           ↓
      Grafana
           ↓
Evaluate Rules
           ↓
Alert Condition Met
           ↓
Notification Sent
           ↓
Engineer Responds
```

---

# 🏗️ Grafana Alerting Components

---

## 1️⃣ Data Source

Grafana reads metrics from:

- Prometheus
- Loki
- CloudWatch
- Elasticsearch
- InfluxDB

---

## 2️⃣ Alert Rule

Defines:

```text
When should an alert trigger?
```

Example:

```text
CPU Usage > 80%
```

---

## 3️⃣ Evaluation

Grafana periodically checks the rule.

Example:

```text
Every 1 minute
```

---

## 4️⃣ Contact Point

Defines where notifications go.

Examples:

- Email 📧
- Slack 💬
- Microsoft Teams
- Webhook 🌐
- PagerDuty
- Discord

---

## 5️⃣ Notification Policy

Determines:

- Who receives alerts
- Alert routing
- Grouping rules

---

# 📊 Alert States

Grafana alerts have multiple states.

---

## 🟢 Normal

Everything is healthy.

```text
CPU = 40%
```

---

## 🟡 Pending

Condition is true but waiting.

```text
CPU > 80% for 2 minutes
```

---

## 🔴 Firing

Alert is triggered.

```text
CPU = 95%
```

Notification sent.

---

## ⚫ No Data

Grafana cannot retrieve metrics.

---

## 🔵 Error

Alert evaluation failed.

---

# ⚙️ Creating an Alert

---

## Example Rule

```text
CPU Usage > 80%
```

---

### Query

```promql
100 - avg(rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100
```

---

### Condition

```text
IS ABOVE 80
```

---

### Evaluation

```text
Every 1 minute
```

---

### Duration

```text
For 5 minutes
```

Alert triggers only if the condition remains true.

---

# 📧 Email Notification Example

```text
ALERT: High CPU Usage

Instance: server-01

Current CPU: 92%

Time: 10:30 AM
```

---

# 🌐 Contact Points

Grafana supports many notification channels.

| Contact Point | Purpose |
|--------------|----------|
| Email 📧 | Notifications |
| Slack 💬 | Team alerts |
| Teams 💻 | Collaboration |
| Webhook 🌐 | Automation |
| PagerDuty 🚨 | Incident response |
| Discord 🎮 | Community alerts |

---

# ☸️ Kubernetes Example

Monitor:

```text
Pod CPU Usage
```

Alert:

```text
CPU > 90%
```

Result:

```text
Grafana Alert
       ↓
Slack Notification
       ↓
DevOps Team
```

---

# 📊 Real-World Example

Imagine an e-commerce application.

Metrics:

```text
CPU Usage

Memory Usage

API Errors

Latency
```

Alerts:

```text
CPU > 80%

Memory > 85%

HTTP 500 Errors > 5%

Latency > 2 seconds
```

Notifications:

```text
Email

Slack

PagerDuty
```

---

# 🔥 Grafana Alerting vs Prometheus Alertmanager

| Feature | Grafana Alerting | Alertmanager |
|---------|-----------------|--------------|
| Alert Rules | ✅ | ❌ |
| Notifications | ✅ | ✅ |
| Data Sources | Multiple | Prometheus Only |
| Dashboard Integration | Excellent | Limited |
| Alert Routing | Yes | Advanced |
| Multi-Source Support | Yes | No |

---

# 🛠️ Best Use Cases

### Grafana Alerting

- Multi-data-source environments
- Dashboard-based alerts
- Cloud monitoring
- Application monitoring

---

### Alertmanager

- Prometheus-only environments
- Advanced alert routing
- Large-scale alert management

---

# 🚨 Common Problems

### Alert Fatigue

Too many alerts.

---

### False Alerts

Improper thresholds.

---

### Missing Notifications

Incorrect contact points.

---

### No Alert Grouping

Duplicate notifications.

---

# ✅ Best Practices

- ✅ Alert on important metrics only
- ✅ Use meaningful thresholds
- ✅ Configure alert duration
- ✅ Group related alerts
- ✅ Test notifications regularly
- ✅ Create actionable alerts

---

# ❌ Common Mistakes

### ❌ Alerting on Every Metric

Creates noise.

---

### ❌ Low Threshold Values

Generates false alarms.

---

### ❌ No Escalation Policy

Critical alerts may be ignored.

---

### ❌ Not Testing Alerts

Notifications may fail.

---

# 🧪 Interview Questions

### ❓ What is Grafana Alerting?

Grafana Alerting evaluates metrics and sends notifications when alert conditions are met.

---

### ❓ What are Contact Points?

Contact points define where notifications are sent.

---

### ❓ What alert states exist in Grafana?

- Normal
- Pending
- Firing
- No Data
- Error

---

### ❓ Can Grafana send Slack notifications?

Yes. Grafana supports Slack, Email, Teams, Webhooks, and many other integrations.

---

### ❓ What is the difference between Grafana Alerting and Alertmanager?

Grafana supports multiple data sources, while Alertmanager is designed specifically for Prometheus alerts.

---

### ❓ Why is alert duration important?

It prevents temporary spikes from generating false alerts.

---

# 🚀 Summary

- Grafana Alerting automates monitoring notifications 🚨
- Supports multiple data sources 📊
- Sends alerts through Email, Slack, Teams, and Webhooks 📧
- Uses alert rules, contact points, and policies ⚙️
- Reduces downtime and improves reliability 🔒
- Essential for DevOps, SRE, and cloud monitoring ☁️

👉 **Grafana Alerting transforms dashboards into proactive monitoring systems by automatically notifying teams when problems occur.**

---

## 🤝 Contribute

Contributions are welcome!

If you find any improvements, feel free to fork the repository and submit a pull request.

---


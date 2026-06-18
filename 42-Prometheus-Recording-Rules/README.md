# 🚀 Prometheus Recording Rules

---

## 📌 Introduction

As monitoring environments grow, Prometheus often executes complex PromQL queries repeatedly.

For example:

```promql
sum(rate(http_requests_total[5m])) by (service)
```

Running such queries every time Grafana loads a dashboard can become expensive.

Problems include:

❌ Slow dashboards

❌ High CPU usage

❌ Increased query latency

❌ Heavy Prometheus workload

👉 To solve this problem, Prometheus provides **Recording Rules**.

Recording Rules precompute query results and store them as new time-series metrics.

---

# 🎯 What are Recording Rules?

Recording Rules allow Prometheus to:

👉 Execute PromQL expressions periodically and save the results as new metrics.

Instead of calculating:

```promql
sum(rate(http_requests_total[5m])) by (service)
```

every time,

Prometheus calculates it once and stores:

```text
service:http_requests_rate5m
```

as a new metric.

---

## 🧠 Why Recording Rules are Important?

Without Recording Rules:

```text
Grafana
      ↓
Complex Query
      ↓
Prometheus
      ↓
Slow Response
```

With Recording Rules:

```text
Grafana
      ↓
Precomputed Metric
      ↓
Fast Response
```

Benefits:

✅ Faster dashboards

✅ Reduced CPU usage

✅ Better scalability

✅ Simpler PromQL queries

---

# 🔄 How Recording Rules Work

```text
PromQL Query
      ↓
Recording Rule
      ↓
New Metric Created
      ↓
Stored in Prometheus
      ↓
Used by Dashboards & Alerts
```

---

# 📊 Basic Recording Rule Example

---

## Original Query

```promql
rate(http_requests_total[5m])
```

---

## Recording Rule

```yaml
groups:
  - name: application_rules

    rules:
      - record: job:http_requests_rate5m

        expr: rate(http_requests_total[5m])
```

---

## Result

Prometheus creates:

```text
job:http_requests_rate5m
```

as a new metric.

---

## Usage

Instead of:

```promql
rate(http_requests_total[5m])
```

you can now use:

```promql
job:http_requests_rate5m
```

---

# 🏗️ Recording Rule Structure

```yaml
groups:
  - name: example_rules

    interval: 30s

    rules:

      - record: metric_name

        expr: prometheus_query
```

---

## 📖 Explanation

### groups

Collection of recording rules.

---

### interval

How often Prometheus evaluates rules.

Example:

```yaml
interval: 30s
```

---

### record

Name of the generated metric.

---

### expr

PromQL query to execute.

---

# ⚙️ Configuring Recording Rules

Create file:

```text
recording_rules.yml
```

Example:

```yaml
groups:
  - name: node_rules

    rules:

      - record: node:cpu_usage_percent

        expr: 100 -
              (avg by(instance)
              (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)
```

---

## Add to Prometheus

```yaml
rule_files:
  - "recording_rules.yml"
```

---

## Reload Configuration

```bash
curl -X POST \
http://localhost:9090/-/reload
```

---

# 🌐 Real-World Example

Imagine a Kubernetes cluster.

You monitor:

```promql
sum(rate(container_cpu_usage_seconds_total[5m]))
by (namespace)
```

This query is expensive.

Instead:

```yaml
- record: namespace:cpu_usage_rate5m

  expr: sum(rate(container_cpu_usage_seconds_total[5m]))
        by (namespace)
```

Prometheus stores:

```text
namespace:cpu_usage_rate5m
```

Grafana dashboards become much faster.

---

# 🚨 Recording Rules vs Alert Rules

Many beginners confuse them.

---

## Recording Rules

Purpose:

```text
Precompute Metrics
```

Result:

```text
New Time-Series Metric
```

---

## Alert Rules

Purpose:

```text
Generate Alerts
```

Result:

```text
Alertmanager Notifications
```

---

## Comparison

| Feature | Recording Rules | Alert Rules |
|----------|----------------|-------------|
| Creates Metric | ✅ Yes | ❌ No |
| Generates Alert | ❌ No | ✅ Yes |
| Improves Performance | ✅ Yes | ❌ No |
| Used in Dashboards | ✅ Yes | ⚠️ Sometimes |

---

# 🛠️ Common Use Cases

---

## Dashboard Optimization

Precompute expensive queries.

---

## Kubernetes Monitoring

Aggregate namespace metrics.

---

## Service-Level Metrics

Create service-level latency metrics.

---

## Alert Optimization

Use precomputed metrics inside alerts.

---

# ☸️ Kubernetes Example

---

## Without Recording Rule

```promql
sum(rate(container_network_receive_bytes_total[5m]))
by (pod)
```

Executed repeatedly.

---

## With Recording Rule

```yaml
- record: pod:network_receive_rate5m

  expr: sum(rate(container_network_receive_bytes_total[5m]))
        by (pod)
```

Now Grafana reads:

```promql
pod:network_receive_rate5m
```

Much faster.

---

# 📊 Recording Rule Evaluation Cycle

```text
Every 30 Seconds
         ↓
Prometheus Executes Query
         ↓
Stores Result
         ↓
Creates New Metric
         ↓
Available for Queries
```

---

# 🚨 Common Mistakes

### ❌ Creating Too Many Rules

Can increase storage consumption.

---

### ❌ Poor Naming Conventions

Makes dashboards difficult to manage.

---

### ❌ Recording Simple Queries

Not every query needs optimization.

---

### ❌ Long Evaluation Intervals

May delay metric updates.

---

# ✅ Best Practices

- ✅ Record expensive PromQL queries
- ✅ Use meaningful metric names
- ✅ Organize rules into groups
- ✅ Use recording rules for dashboard optimization
- ✅ Reuse recorded metrics in alerts
- ✅ Monitor Prometheus performance

---

# 🧪 Interview Questions

### ❓ What are Prometheus Recording Rules?

Recording Rules execute PromQL expressions periodically and store the results as new metrics.

---

### ❓ Why are Recording Rules used?

To improve query performance and reduce Prometheus workload.

---

### ❓ What is the difference between Recording Rules and Alert Rules?

Recording Rules create metrics, while Alert Rules generate alerts.

---

### ❓ Where are Recording Rules stored?

Inside rule files configured in Prometheus.

---

### ❓ Can Recording Rules improve Grafana dashboard performance?

Yes. Dashboards can use precomputed metrics instead of expensive queries.

---

### ❓ What happens when a Recording Rule executes?

Prometheus evaluates the query and stores the result as a new time-series metric.

---

# 🚀 Summary

- Recording Rules precompute PromQL queries ⚡
- Create new metrics automatically 📊
- Improve dashboard performance 🚀
- Reduce Prometheus query load 🔍
- Commonly used in Kubernetes and large environments ☸️
- Essential for scalable Prometheus deployments 🌐

👉 **Recording Rules transform expensive PromQL queries into reusable metrics, making monitoring systems faster and more efficient.**

---

## 🤝 Contribute

Contributions are welcome!

If you find any improvements, feel free to fork the repository and submit a pull request.

---


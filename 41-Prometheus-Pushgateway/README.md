# 🚀 Prometheus Pushgateway

---

## 📌 Introduction

Prometheus follows a **pull-based model**.

Normally, Prometheus works like this:

```text
Prometheus
      ↓
Scrapes Metrics
      ↓
Application / Exporter
```

Prometheus periodically pulls metrics from targets.

But what happens if an application:

- Runs only for a few seconds ⏱️
- Finishes before Prometheus scrapes it ❌
- Is a batch or cron job 🕒

In such cases, metrics may be lost.

👉 This is where **Pushgateway** becomes useful.

---

# 🎯 What is Pushgateway?

Pushgateway is a component in the Prometheus ecosystem that allows short-lived jobs to push metrics.

Instead of:

```text
Prometheus → Application
```

the flow becomes:

```text
Application → Pushgateway → Prometheus
```

Pushgateway temporarily stores metrics until Prometheus scrapes them.

---

## 🧠 Why Pushgateway is Needed?

Prometheus pull model works well for:

✅ Long-running applications

But not for:

❌ Batch jobs

❌ Scheduled scripts

❌ Short-lived containers

Pushgateway solves this problem.

---

# 🔄 How Pushgateway Works

```text
Batch Job
    ↓
Push Metrics
    ↓
Pushgateway
    ↓
Prometheus Scrapes Metrics
    ↓
Grafana Visualizes Data
```

---

# 🛠️ Common Use Cases

---

## 1️⃣ Cron Jobs

Example:

```text
Database Backup Job
```

Runs:

```text
Every Night at 12 AM
```

After completion:

```text
Push Success Metric
```

---

## 2️⃣ Batch Processing Jobs

Example:

```text
ETL Pipeline
```

Metrics:

- Records Processed
- Job Duration
- Success Status

---

## 3️⃣ CI/CD Pipelines

Example:

```text
Jenkins Build Job
```

Push metrics:

```text
Build Success

Build Duration
```

---

## 4️⃣ Temporary Containers

Short-lived containers can push metrics before termination.

---

# ⚙️ Installing Pushgateway

Run using Docker:

```bash
docker run -d \
  --name pushgateway \
  -p 9091:9091 \
  prom/pushgateway
```

Access Pushgateway:

```text
http://localhost:9091
```

---

# 📤 Pushing Metrics Manually

Example:

```bash
echo "backup_success 1" | \
curl --data-binary @- \
http://localhost:9091/metrics/job/backup
```

---

## 📖 Explanation

Metric:

```text
backup_success 1
```

means:

```text
Backup completed successfully
```

Job name:

```text
backup
```

identifies the metric source.

---

# 📊 Viewing Metrics

Open:

```text
http://localhost:9091/metrics
```

Output:

```text
backup_success{job="backup"} 1
```

---

# ⚙️ Configure Prometheus

Add Pushgateway as a scrape target.

```yaml
scrape_configs:
  - job_name: "pushgateway"

    static_configs:
      - targets:
          - "localhost:9091"
```

Prometheus now scrapes Pushgateway automatically.

---

# 🐍 Python Example

Install library:

```bash
pip install prometheus_client
```

---

## Sample Code

```python
from prometheus_client import CollectorRegistry
from prometheus_client import Gauge
from prometheus_client import push_to_gateway

registry = CollectorRegistry()

job_status = Gauge(
    'backup_success',
    'Backup Job Status',
    registry=registry
)

job_status.set(1)

push_to_gateway(
    'localhost:9091',
    job='backup_job',
    registry=registry
)
```

---

## 📖 Explanation

Creates metric:

```text
backup_success
```

Pushes it to:

```text
Pushgateway
```

Prometheus later scrapes it.

---

# 🚨 Important Limitation

Pushgateway is **NOT** a general-purpose metrics store.

Prometheus best practice:

✅ Use Pushgateway only for:

- Batch jobs
- Scheduled tasks
- Short-lived workloads

❌ Do NOT use for:

- Long-running applications
- Servers
- Kubernetes services

These should expose `/metrics` endpoints directly.

---

# 🌐 Real-World Example

Imagine:

```text
Nightly Database Backup
```

Flow:

```text
Backup Script
      ↓
Push Success Metric
      ↓
Pushgateway
      ↓
Prometheus
      ↓
Grafana Dashboard
      ↓
Alert if Backup Fails
```

---

# 📊 Pull Model vs Push Model

| Feature | Pull Model | Pushgateway |
|---------|-----------|-------------|
| Metric Collection | Prometheus Pulls | Application Pushes |
| Best For | Long-running Services | Batch Jobs |
| Dynamic Targets | Excellent | Limited |
| Recommended Default | Yes | No |
| Storage | Prometheus | Temporary |

---

# 🚨 Common Mistakes

### ❌ Using Pushgateway for Servers

Servers should expose:

```text
/metrics
```

directly.

---

### ❌ Not Cleaning Old Metrics

Stale metrics can remain in Pushgateway.

---

### ❌ Using Pushgateway as a Database

Pushgateway is not designed for long-term storage.

---

# ✅ Best Practices

- ✅ Use only for short-lived jobs
- ✅ Delete stale metrics when necessary
- ✅ Use meaningful job names
- ✅ Monitor Pushgateway health
- ✅ Prefer pull model whenever possible

---

# 🧪 Interview Questions

### ❓ What is Prometheus Pushgateway?

Pushgateway allows short-lived jobs to push metrics for Prometheus scraping.

---

### ❓ Why is Pushgateway needed?

Short-lived jobs may finish before Prometheus can scrape metrics.

---

### ❓ Which workloads should use Pushgateway?

Batch jobs, cron jobs, and temporary tasks.

---

### ❓ Can Pushgateway replace the Prometheus pull model?

No. The pull model remains the recommended approach.

---

### ❓ Why should long-running services avoid Pushgateway?

They should expose `/metrics` endpoints directly for better monitoring.

---

# 🚀 Summary

- Pushgateway enables push-based metrics collection 📤
- Used mainly for short-lived jobs ⏱️
- Stores metrics temporarily before scraping 📊
- Integrates with Prometheus and Grafana 🔍
- Not intended for long-running services 🚫
- Complements the Prometheus pull model ⚡

👉 **Pushgateway bridges the gap between Prometheus's pull model and short-lived applications that cannot be scraped directly.**

---

## 🤝 Contribute

Contributions are welcome!

If you find any improvements, feel free to fork the repository and submit a pull request.

---


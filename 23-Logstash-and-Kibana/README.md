# 🚀 Logstash and Kibana

---

## 📌 Introduction

In the ELK Stack:

- Elasticsearch stores logs 📦  
- Logstash processes logs 🔄  
- Kibana visualizes logs 📊  

👉 Logstash and Kibana together make log analysis powerful and user-friendly.

---

# 🟢 Logstash

---

## 🎯 What is Logstash?

Logstash is a:
- Data collection tool 📥  
- Log processing pipeline 🔄  

👉 It collects logs from different sources, processes them, and sends them to Elasticsearch.

---

## 🧠 Why Logstash is Important?

Applications generate logs in different formats.

👉 Logstash helps:
- Parse logs 🔍  
- Filter logs ⚙️  
- Transform logs 🔄  
- Centralize logs 📦  

---

## 🔄 Logstash Workflow

```text
Input → Filter → Output
```

---

## 🧩 Logstash Components

---

## 📥 1️⃣ Input

Defines where logs come from.

### 🧠 Examples:
- Files 📄  
- Applications 🌐  
- Databases 🗄️  
- Kafka 📡  

---

## ⚙️ 2️⃣ Filter

Processes and transforms logs.

### 🧠 Examples:
- Parse timestamps ⏰  
- Remove unnecessary data ❌  
- Convert formats 🔄  

---

## 📤 3️⃣ Output

Defines where processed logs go.

### 🧠 Examples:
- Elasticsearch 📦  
- File 📄  
- Kafka 📡  

---

## ⚙️ Example Logstash Configuration

```conf
input {
  file {
    path => "/var/log/syslog"
    start_position => "beginning"
  }
}

filter {
  grok {
    match => { "message" => "%{SYSLOGBASE} %{GREEDYDATA:msg}" }
  }
}

output {
  elasticsearch {
    hosts => ["localhost:9200"]
  }
}
```

---

## 📖 Explanation

### Input:
Reads logs from:
```text
/var/log/syslog
```

### Filter:
Uses `grok` to parse log format.

### Output:
Sends processed logs to Elasticsearch.

---

# 🔵 Kibana

---

## 🎯 What is Kibana?

Kibana is a:
- Visualization tool 📊  
- Log analysis dashboard 🔍  

👉 Used with Elasticsearch to:
- Search logs  
- Visualize data  
- Create dashboards  

---

## 🧠 Why Kibana is Important?

Without Kibana:
- Logs are difficult to analyze manually ❌

With Kibana:
- Easy searching 🔍  
- Real-time dashboards 📈  
- Better troubleshooting ⚡  

---

## 🔍 Features of Kibana

---

### 📊 1️⃣ Dashboards

Visualize:
- Error rates  
- System activity  
- Request trends  

---

### 🔎 2️⃣ Discover

Search and filter logs easily.

#### 🧠 Example:
```text
status:500
```

---

### 📈 3️⃣ Visualizations

Create:
- Graphs  
- Pie charts  
- Heatmaps  

---

### 🚨 4️⃣ Alerts

Generate alerts based on log patterns.

---

## ⚙️ Running Kibana Using Docker

```bash
docker run -d \
  --name kibana \
  -p 5601:5601 \
  kibana:8.0.0
```

---

## 📖 Explanation

- `5601` → Kibana UI port  
- Access UI:
```text
http://localhost:5601
```

---

## 🔄 Complete ELK Flow

```text
Applications
     ↓
 Logstash
     ↓
Elasticsearch
     ↓
  Kibana
```

👉 End-to-end centralized logging pipeline 🔥

---

## 🧠 Real-World Example

### Scenario:
A web application generates logs:
```text
ERROR: Database connection failed
```

### Flow:
1️⃣ Logstash collects log  
2️⃣ Elasticsearch stores log  
3️⃣ Kibana visualizes error trends  

👉 Easy troubleshooting and monitoring

---

## 🚨 Advantages

### 🟢 Logstash
- Supports multiple inputs  
- Powerful filtering system  
- Flexible pipelines  

### 🔵 Kibana
- User-friendly dashboards  
- Real-time visualization  
- Powerful search capability  

---

## ⚠️ Challenges

- ❌ Logstash can consume high memory  
- ❌ Kibana depends on Elasticsearch health  
- ❌ Complex configurations for large environments  

---

## ✅ Best Practices

- ✅ Use structured logs (JSON)  
- ✅ Filter unnecessary logs  
- ✅ Create meaningful dashboards  
- ✅ Monitor Elasticsearch storage  

---

## ⚠️ Common Mistakes

❌ No log filtering  
👉 Too much noise  

❌ Poor dashboard organization  
👉 Difficult analysis  

❌ Unstructured logs  
👉 Hard searching and parsing  

---

## 🧪 Interview Questions

### ❓ What is Logstash?

Logstash is a log processing pipeline used to collect, parse, and forward logs.

---

### ❓ What is Kibana used for?

Kibana is used for searching, analyzing, and visualizing logs stored in Elasticsearch.

---

### ❓ What is the workflow of Logstash?

Input → Filter → Output.

---

## 🚀 Summary

- Logstash processes and forwards logs 🔄  
- Kibana visualizes and analyzes logs 📊  
- Together they form the ELK logging pipeline 🔥  
- Essential for centralized log monitoring 📜  

👉 **Logstash and Kibana make log management scalable and efficient**

---

## 🤝 Contribute

Contributions are welcome!  

If you find any improvements, feel free to fork the repository and submit a pull request.

---

## 👨‍💻 Author



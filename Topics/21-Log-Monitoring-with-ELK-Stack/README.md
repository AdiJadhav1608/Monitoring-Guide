# 🚀 Log Monitoring with ELK Stack

---

## 📌 Introduction

Modern applications generate huge amounts of logs every second 📜

Manually checking logs is difficult ❌

👉 We need a centralized system to:
- Collect logs 📥  
- Store logs 📦  
- Search logs 🔍  
- Visualize logs 📊  

This is where the **ELK Stack** comes in 🔥

---

## 🎯 What is ELK Stack?

ELK Stack is a popular log monitoring and analysis solution consisting of:

- 🟡 Elasticsearch  
- 🟢 Logstash  
- 🔵 Kibana  

👉 Together they provide centralized log management

---

## 🧩 ELK Stack Components

---

## 🟡 1️⃣ Elasticsearch

### 📌 What is Elasticsearch?

Elasticsearch is a:
- Distributed search engine 🔍  
- Log storage system 📦  

👉 Used to:
- Store logs  
- Search logs quickly  
- Analyze large datasets  

---

### ⚡ Features:
- Fast searching  
- Scalable architecture  
- Real-time analytics  

---

## 🟢 2️⃣ Logstash

### 📌 What is Logstash?

Logstash is a data processing pipeline.

👉 It:
- Collects logs 📥  
- Parses logs ⚙️  
- Transforms logs 🔄  
- Sends logs to Elasticsearch  

---

### 🧠 Example:
```text
Application Logs → Logstash → Elasticsearch
```

---

## 🔵 3️⃣ Kibana

### 📌 What is Kibana?

Kibana is a visualization tool for Elasticsearch.

👉 Used to:
- Search logs 🔍  
- Create dashboards 📊  
- Analyze events 📈  

---

## 🔄 ELK Stack Architecture

```text
Applications / Servers
          ↓
       Logstash
          ↓
    Elasticsearch
          ↓
        Kibana
```

👉 Complete centralized logging workflow

---

## 🧠 Real-World Example

Imagine:
- Multiple servers  
- Multiple applications  
- Thousands of logs per minute  

👉 Instead of checking each server manually:

ELK Stack centralizes everything in one dashboard 🔥

---

## ⚙️ Installing ELK Stack Using Docker

---

### 🟡 Elasticsearch

```bash
docker run -d \
  --name elasticsearch \
  -p 9200:9200 \
  -e "discovery.type=single-node" \
  elasticsearch:8.0.0
```

---

### 🟢 Logstash

```bash
docker run -d \
  --name logstash \
  -p 5044:5044 \
  logstash:8.0.0
```

---

### 🔵 Kibana

```bash
docker run -d \
  --name kibana \
  -p 5601:5601 \
  kibana:8.0.0
```

---

## 📖 Explanation

| Component | Port |
|-----------|------|
| Elasticsearch | 9200 |
| Logstash | 5044 |
| Kibana | 5601 |

---

## ⚙️ Simple Logstash Configuration

```conf
input {
  file {
    path => "/var/log/syslog"
    start_position => "beginning"
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
- Reads logs from system log file

### Output:
- Sends logs to Elasticsearch

👉 Logstash acts as the pipeline 🔄

---

## 🔍 Searching Logs in Kibana

Examples:
```text
ERROR
```

```text
status:500
```

👉 Helps identify issues quickly

---

## 🚨 Why ELK Stack is Important?

- 📦 Centralized logging  
- 🔍 Fast searching  
- 📊 Powerful visualization  
- ⚡ Real-time analysis  
- ☁️ Widely used in DevOps & SRE  

---

## ⚠️ Challenges of ELK Stack

- ❌ High memory usage  
- ❌ Complex setup for large environments  
- ❌ Elasticsearch storage can grow quickly  

---

## ✅ Best Practices

- ✅ Use log rotation  
- ✅ Filter unnecessary logs  
- ✅ Use structured logs (JSON)  
- ✅ Monitor Elasticsearch storage  

---

## ⚠️ Common Mistakes

❌ Storing all logs forever  
👉 Storage issues  

❌ No log filtering  
👉 Noise and high costs  

❌ Unstructured logs  
👉 Hard to search and analyze  

---

## 🧪 Interview Questions

### ❓ What is ELK Stack?

ELK Stack is a centralized logging solution consisting of Elasticsearch, Logstash, and Kibana.

---

### ❓ What is the role of Logstash?

Logstash collects, processes, and forwards logs.

---

### ❓ What is Kibana used for?

Kibana is used for searching, analyzing, and visualizing logs.

---

## 🚀 Summary

- ELK Stack = Centralized log monitoring 🔥  
- Elasticsearch stores logs 📦  
- Logstash processes logs 🔄  
- Kibana visualizes logs 📊  
- Helps in troubleshooting and monitoring 🔍  

👉 **ELK Stack is one of the most powerful logging solutions in DevOps**

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

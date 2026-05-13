# 🚀 Elasticsearch Basics

---

## 📌 Introduction

Modern applications generate massive amounts of data every second 📦

Searching through this data manually is difficult and slow ❌

👉 This is where **Elasticsearch** becomes powerful 🔥

Elasticsearch helps store, search, and analyze large volumes of data in real-time.

---

## 🎯 What is Elasticsearch?

Elasticsearch is an:
- Open-source distributed search engine 🔍  
- Analytics engine 📊  

👉 Built on top of Apache Lucene

It is mainly used for:
- Log analysis 📜  
- Full-text search 🔎  
- Monitoring systems 📈  
- Real-time analytics ⚡  

---

## 🧠 Why Elasticsearch is Popular?

- ⚡ Extremely fast searching  
- 📦 Handles huge amounts of data  
- ☁️ Scalable distributed architecture  
- 🔍 Real-time indexing and querying  
- 🔗 Integrates with ELK Stack  

---

## 🧩 Core Concepts of Elasticsearch

---

## 📦 1️⃣ Document

A document is the basic unit of data in Elasticsearch.

👉 Stored in JSON format

### 🧠 Example:
```json
{
  "name": "Aditya",
  "role": "DevOps Engineer"
}
```

---

## 📚 2️⃣ Index

An index is a collection of related documents.

👉 Similar to a database table

### 🧠 Example:
```text
employee_data
```

---

## 🗂️ 3️⃣ Shards

Large indexes are divided into smaller pieces called shards.

👉 Improves scalability and performance

---

## 🔄 4️⃣ Replicas

Copies of shards used for:
- High availability  
- Fault tolerance  

👉 Prevents data loss

---

## 🌐 Elasticsearch Architecture

```text
Client → Elasticsearch Cluster → Nodes → Shards
```

---

## 🧩 Main Components

| Component | Purpose |
|-----------|---------|
| Cluster 🌐 | Group of nodes |
| Node 🖥️ | Single Elasticsearch server |
| Index 📚 | Collection of documents |
| Document 📦 | Actual data |
| Shard 🗂️ | Partition of index |

---

## ⚙️ Installing Elasticsearch Using Docker

```bash
docker run -d \
  --name elasticsearch \
  -p 9200:9200 \
  -e "discovery.type=single-node" \
  elasticsearch:8.0.0
```

---

## 📖 Explanation

- `9200` → REST API port  
- `discovery.type=single-node` → Single-node mode  

👉 Access Elasticsearch:
```text
http://localhost:9200
```

---

## ⚙️ Basic Elasticsearch Operations

---

## 📥 Create a Document

```bash
curl -X POST "localhost:9200/employees/_doc/1" \
-H 'Content-Type: application/json' \
-d '
{
  "name": "Aditya",
  "role": "DevOps Engineer"
}'
```

---

## 🔍 Search Data

```bash
curl -X GET "localhost:9200/employees/_search?q=name:Aditya"
```

👉 Searches for documents containing "Aditya"

---

## 📊 Sample Response

```json
{
  "hits": {
    "total": 1,
    "hits": [
      {
        "_source": {
          "name": "Aditya",
          "role": "DevOps Engineer"
        }
      }
    ]
  }
}
```

---

## 🚨 Common Use Cases

- 📜 Log monitoring  
- 🔍 Search engines  
- 📊 Analytics dashboards  
- 🛒 E-commerce product search  
- ☁️ Cloud monitoring  

---

## ⚡ Advantages of Elasticsearch

- Fast searching 🔥  
- Real-time indexing ⚡  
- Distributed architecture 🌐  
- Scalable storage 📦  

---

## ⚠️ Limitations

- ❌ High memory usage  
- ❌ Complex cluster management  
- ❌ Storage grows quickly with logs  

---

## ✅ Best Practices

- ✅ Use proper index naming  
- ✅ Configure replicas properly  
- ✅ Delete old unused indexes  
- ✅ Monitor cluster health  

---

## ⚠️ Common Mistakes

❌ Too many shards  
👉 Performance issues  

❌ No replicas  
👉 Risk of data loss  

❌ Unstructured data  
👉 Poor search results  

---

## 🧪 Interview Questions

### ❓ What is Elasticsearch?

Elasticsearch is a distributed search and analytics engine used for storing and searching large datasets.

---

### ❓ What is a document in Elasticsearch?

A document is the basic unit of data stored in JSON format.

---

### ❓ What are shards in Elasticsearch?

Shards are smaller partitions of an index used for scalability and performance.

---

## 🚀 Summary

- Elasticsearch = Search + Analytics engine 🔍  
- Stores data as JSON documents 📦  
- Uses indexes, shards, and replicas 🗂️  
- Fast real-time searching ⚡  
- Widely used in ELK Stack 📜  

👉 **Elasticsearch is the backbone of modern log analytics systems**

---

## 🤝 Contribute

Contributions are welcome!  

If you find any improvements, feel free to fork the repository and submit a pull request.

---


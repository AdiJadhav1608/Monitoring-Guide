# 🚀 Log Levels and Formats

---

## 📌 Introduction

Logs are useful only if they are **properly structured and categorized**.

👉 Log levels help us understand **severity**  
👉 Log formats help us understand **structure**

---

## 🎯 What are Log Levels?

Log levels indicate the **importance or severity** of a log message.

👉 They help developers and monitoring tools:
- Filter logs 🔍  
- Prioritize issues 🚨  
- Debug efficiently 🧠  

---

## 📊 Common Log Levels

---

### 🐞 1️⃣ DEBUG

- Detailed information for debugging  
- Used by developers  

#### 🧠 Example:
```text
DEBUG: Variable x = 10
```

---

### ℹ️ 2️⃣ INFO

- Normal system operation  
- General events  

#### 🧠 Example:
```text
INFO: User logged in
```

---

### ⚠️ 3️⃣ WARN (Warning)

- Indicates a potential issue  
- Not a failure yet  

#### 🧠 Example:
```text
WARN: Memory usage is high
```

---

### ❌ 4️⃣ ERROR

- An issue has occurred  
- Needs attention  

#### 🧠 Example:
```text
ERROR: Database connection failed
```

---

### 💀 5️⃣ FATAL (Critical)

- Severe issue  
- System may crash or stop  

#### 🧠 Example:
```text
FATAL: Application crashed
```

---

## 🔥 Log Level Hierarchy

```text
DEBUG < INFO < WARN < ERROR < FATAL
```

👉 As you go higher → Severity increases

---

## 🎯 What are Log Formats?

Log format defines **how logs are structured and stored**

👉 Proper format makes logs:
- Easy to read 👀  
- Easy to search 🔍  
- Easy to analyze 📊  

---

## 📊 Common Log Formats

---

### 📝 1️⃣ Plain Text Format

Simple human-readable logs

#### 🧠 Example:
```text
2026-04-24 10:00:01 INFO User logged in
```

👉 Easy to read but harder to parse automatically

---

### 📦 2️⃣ JSON Format (Recommended 🔥)

Structured format widely used in modern systems

#### 🧠 Example:
```json
{
  "timestamp": "2026-04-24T10:00:01",
  "level": "INFO",
  "message": "User logged in"
}
```

👉 Best for tools like:
- ELK Stack  
- Loki  

---

### 📑 3️⃣ Key-Value Format

Logs stored as key=value pairs

#### 🧠 Example:
```text
time=2026-04-24 level=INFO msg="User logged in"
```

👉 Easy to parse and filter

---

## ⚙️ Example: Logging with Levels in Python

```python
import logging

# Configure logging format and level
logging.basicConfig(
    level=logging.DEBUG,
    format='%(asctime)s - %(levelname)s - %(message)s'
)

# Log messages
logging.debug("Debugging info")
logging.info("Application started")
logging.warning("Memory usage high")
logging.error("Database error occurred")
logging.critical("System crashed")
```

### 📖 Explanation:
- `level=logging.DEBUG` → Enables all log levels  
- `format` → Defines log structure  
- Different functions → Different log levels  

👉 Helps generate **structured and categorized logs**

---

## 🚨 Best Practices

- ✅ Use appropriate log levels  
- ✅ Avoid excessive DEBUG logs in production  
- ✅ Prefer JSON format for scalability  
- ✅ Include timestamp and context  

---

## ⚠️ Common Mistakes

❌ Logging everything as INFO  
👉 Hard to identify critical issues  

❌ No structure in logs  
👉 Difficult to analyze  

❌ Too many DEBUG logs in production  
👉 Performance impact  

---

## 🧪 Interview Questions

### ❓ What are log levels?

Log levels indicate the severity of log messages such as DEBUG, INFO, WARN, ERROR, and FATAL.

---

### ❓ Why is JSON format preferred for logs?

Because it is structured, easy to parse, and works well with monitoring tools.

---

### ❓ What is the difference between INFO and ERROR?

INFO indicates normal operation, while ERROR indicates a failure.

---

## 🚀 Summary

- Log levels define **severity** 📊  
- Log formats define **structure** 📦  
- JSON is the most recommended format 🔥  
- Proper logging improves debugging and monitoring 🔍  

👉 **Good logging = Easy troubleshooting**

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

# OWASP Juice Shop – Web Application Penetration Testing

## 📌 Overview

This project demonstrates hands-on web application security testing using OWASP Juice Shop and Burp Suite.
The focus was on identifying and exploiting common vulnerabilities such as SQL Injection and broken authentication.

---

## 🛠️ Tools Used

* Burp Suite Community Edition
* OWASP Juice Shop (Docker)
* Kali Linux
* JWT.io (token analysis)

---

## ⚙️ Setup

```bash
docker run -d -p 3000:3000 bkimminich/juice-shop
```

Access the application:

```
http://127.0.0.1:3000
```

---

## 🔍 Vulnerability #1: SQL Injection Authentication Bypass

### 📍 Endpoint

```
POST /rest/user/login
```

### 🧪 Payload Used

```json
{
  "email": "' OR 1=1--",
  "password": "a"
}
```

### ✅ Result

* Successfully bypassed authentication
* Logged in as admin user without valid credentials
* Received valid JWT token

---

## 🎯 Impact

* Full account takeover
* Unauthorized admin access
* Critical authentication bypass

---

## 🔐 Evidence

* HTTP 200 response after injection
* JWT token issued with admin privileges

---

## 🧠 Root Cause

* Unsanitized user input in SQL query
* No parameterized queries used

---

## 🛡️ Mitigation

* Use parameterized queries (prepared statements)
* Input validation & sanitization
* Implement proper authentication logic

---

## 📈 Skills Demonstrated

* Web application testing
* SQL Injection exploitation
* Burp Suite usage (Proxy, Repeater)
* Authentication bypass techniques
* JWT analysis

---

## 🚀 Future Work

* Cross-Site Scripting (XSS)
* Broken Access Control testing
* JWT attack scenarios

---

## 👤 Author

Iwin SIju ( XOUT1 )

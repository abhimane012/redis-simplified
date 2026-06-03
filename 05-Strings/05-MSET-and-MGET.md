# 📦 MSET and MGET in Redis

Redis provides `MSET` and `MGET` commands to work with multiple keys at the same time.

These commands help reduce multiple Redis calls and improve performance.

---

# 📝 MSET

`MSET` is used to set multiple key-value pairs in a single command.

---

# 💻 Syntax

```bash
MSET key1 value1 key2 value2 key3 value3
```

---

# 🧪 Example

```bash
MSET name "Abhishek" age 25 country "India"
```

This creates:

```text
name    -> "Abhishek"
age     -> 25
country -> "India"
```

---

# ✅ Output

```text
OK
```

---

# 📖 MGET

`MGET` is used to get values of multiple keys together.

---

# 💻 Syntax

```bash
MGET key1 key2 key3
```

---

# 🧪 Example

```bash
MGET name age country
```

Output:

```text
1) "Abhishek"
2) "25"
3) "India"
```

---

# ❌ Missing Keys

If a key does not exist, Redis returns:

```text
(nil)
```

Example:

```bash
MGET name city
```

Output:

```text
1) "Abhishek"
2) (nil)
```

---

# ⚡ Why Use MSET and MGET?

These commands are useful because they:

- 🚀 Reduce multiple Redis requests
- ⚡ Improve performance
- 📦 Handle multiple values easily

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 User Data | Store user details |
| ⚡ Cache | Store multiple cache values |
| 📊 Analytics | Read multiple counters |
| ⚙️ Configuration | Load multiple settings |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `MSET` | Set multiple key-value pairs |
| `MGET` | Get multiple values together |

`MSET` and `MGET` make working with multiple Redis keys faster and easier 🚀

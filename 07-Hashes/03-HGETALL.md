# 📖 HGETALL in Redis

Redis provides the `HGETALL` command to retrieve all fields and values from a hash.

---

# 💻 Syntax

```bash
HGETALL key
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 name "Abhishek" age 25 city "Bangalore"
```

Read all fields and values:

```bash
HGETALL user:1
```

Output:

```text
1) "name"
2) "Abhishek"
3) "age"
4) "25"
5) "city"
6) "Bangalore"
```

---

# 📌 Understanding the Output

Redis returns:

```text
field → value
```

Example:

```text
name → "Abhishek"
age  → "25"
city → "Bangalore"
```

---

# ❌ Non-Existing Hash

```bash
HGETALL unknown_user
```

Output:

```text
(empty list or set)
```

---

# ⚡ Important Points

- Returns all fields and values
- Works only with hashes
- Useful for reading complete objects

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 User profiles | Get all user details |
| 📦 Product data | Fetch complete product info |
| ⚙️ Settings | Load configuration data |
| 🛒 Cart details | Read full cart information |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HGETALL key` | Get all fields and values from a hash |

`HGETALL` is commonly used to retrieve complete Redis hash data 🚀
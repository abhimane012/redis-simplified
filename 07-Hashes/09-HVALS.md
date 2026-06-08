# 📖 HVALS in Redis

Redis provides the `HVALS` command to get all values from a hash.

---

# 💻 Syntax

```bash
HVALS key
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 name "Abhishek" age 25 city "Bangalore"
```

Get all values:

```bash
HVALS user:1
```

Output:

```text
1) "Abhishek"
2) "25"
3) "Bangalore"
```

---

# 📌 What HVALS Returns

`HVALS` returns only:

- 📖 Field values

It does not return field names.

---

# ❌ Non-Existing Hash

```bash
HVALS unknown_user
```

Output:

```text
(empty list or set)
```

---

# ⚡ Important Points

- Returns all values from the hash
- Works only with hashes
- Does not return field names

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 User profiles | Read stored values |
| ⚙️ Configuration data | Load settings values |
| 📦 Product info | Fetch attribute values |
| 🛒 Cart systems | Read stored details |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HVALS key` | Get all values from a hash |

`HVALS` helps retrieve all stored values inside Redis hashes 🚀
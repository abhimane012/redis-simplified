# 🔑 HKEYS in Redis

Redis provides the `HKEYS` command to get all field names from a hash.

---

# 💻 Syntax

```bash
HKEYS key
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 name "Abhishek" age 25 city "Bangalore"
```

Get all field names:

```bash
HKEYS user:1
```

Output:

```text
1) "name"
2) "age"
3) "city"
```

---

# 📌 What HKEYS Returns

`HKEYS` returns only:

- 🔑 Field names

It does not return values.

---

# ❌ Non-Existing Hash

```bash
HKEYS unknown_user
```

Output:

```text
(empty list or set)
```

---

# ⚡ Important Points

- Returns all field names
- Works only with hashes
- Does not return field values

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 User profiles | Get available fields |
| ⚙️ Configuration data | List setting names |
| 📦 Product info | View attributes |
| 🛒 Cart systems | Inspect stored fields |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HKEYS key` | Get all field names from a hash |

`HKEYS` helps inspect the structure of Redis hashes 🚀
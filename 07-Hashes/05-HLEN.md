# 📏 HLEN in Redis

Redis provides the `HLEN` command to get the number of fields inside a hash.

`HLEN` stands for:

> Hash Length

---

# 💻 Syntax

```bash
HLEN key
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 name "Abhishek" age 25 city "Bangalore"
```

Get total fields:

```bash
HLEN user:1
```

Output:

```text
(integer) 3
```

---

# 📌 Understanding the Result

Hash:

```text
user:1
├── name
├── age
└── city
```

Total fields:

```text
3
```

So Redis returns:

```text
(integer) 3
```

---

# ❌ Non-Existing Hash

```bash
HLEN unknown_user
```

Output:

```text
(integer) 0
```

Because the hash does not exist.

---

# ⚡ Important Points

- Counts fields only
- Works only with hashes
- Very fast operation

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 User profiles | Count stored attributes |
| 📦 Product data | Count product fields |
| ⚙️ Settings | Check configuration size |
| 🛒 Cart details | Count stored items |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HLEN key` | Get total number of fields in a hash |

`HLEN` helps measure the size of Redis hashes quickly 🚀
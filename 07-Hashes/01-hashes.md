# 🗃️ Redis Hashes

Redis Hashes store data in **field-value** format.

A hash is similar to:

- 📦 Objects
- 🧾 Dictionaries
- 📄 JSON objects

Each hash contains multiple fields inside a single key.

---

# 🧠 Think of a Hash Like

```text
user:1
├── name  → "Abhishek"
├── age   → "25"
└── city  → "Bangalore"
```

Here:

- `user:1` → Redis key
- `name`, `age`, `city` → fields
- Values are stored inside the hash

---

# ⚡ Features of Redis Hashes

- 📦 Store multiple fields in one key
- 💾 Memory efficient
- ⚡ Fast read and update operations
- 🧩 Great for structured data

---

# 🌍 Common Use Cases

- 👤 User profiles
- 📦 Product information
- ⚙️ Application settings
- 🛒 Shopping cart details
- 📊 Configuration data

---

# 🛠️ Common Redis Hash Commands

| Command | Purpose |
|---|---|
| `HSET` | Set field values |
| `HGET` | Get field value |
| `HGETALL` | Get all fields and values |
| `HDEL` | Delete fields |
| `HEXISTS` | Check field exists |
| `HLEN` | Count fields |
| `HKEYS` | Get all field names |
| `HVALS` | Get all values |
| `HMSET` | Set multiple fields |
| `HMGET` | Get multiple fields |

---

# ✅ Why Use Hashes Instead of Strings?

Instead of storing everything in one large JSON string:

```json
{"name":"Abhishek","age":25}
```

Redis Hashes allow storing fields separately.

This makes updates faster and more efficient.

---

# 📝 Summary

- 🗃️ Hashes store field-value pairs
- ⚡ Efficient for structured data
- 💾 Saves memory
- 👤 Commonly used for objects and profiles

Redis Hashes are one of the most useful Redis data types for real-world applications 🚀
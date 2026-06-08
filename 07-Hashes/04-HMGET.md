# 📖 HMGET in Redis

Redis provides the `HMGET` command to get values of multiple fields from a hash.

`HMGET` stands for:

> Hash Multiple GET

---

# 💻 Syntax

```bash
HMGET key field1 field2 field3
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 name "Abhishek" age 25 city "Bangalore"
```

Get multiple fields:

```bash
HMGET user:1 name city
```

Output:

```text
1) "Abhishek"
2) "Bangalore"
```

---

# 📌 Understanding the Output

Redis returns values in the same order as requested fields.

Example:

```bash
HMGET user:1 city age
```

Output:

```text
1) "Bangalore"
2) "25"
```

---

# ❌ Missing Field

```bash
HMGET user:1 name country
```

Output:

```text
1) "Abhishek"
2) (nil)
```

Because `country` field does not exist.

---

# ⚡ Important Points

- Fetches multiple fields in one command
- Works only with hashes
- More efficient than multiple `HGET` calls

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 User profiles | Fetch selected user details |
| 📦 Product data | Get specific attributes |
| ⚙️ Configurations | Load selected settings |
| 🛒 Cart systems | Read chosen fields |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HMGET key field1 field2` | Get multiple field values from a hash |

`HMGET` helps retrieve multiple hash fields efficiently 🚀
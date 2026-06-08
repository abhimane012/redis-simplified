# ✏️ HSET in Redis

Redis provides the `HSET` command to add or update fields inside a hash.

---

# 💻 Syntax

```bash
HSET key field value
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 name "Abhishek"
```

This creates:

```text
user:1
└── name → "Abhishek"
```

---

# ➕ Add Multiple Fields

```bash
HSET user:1 age 25 city "Bangalore"
```

Now hash becomes:

```text
user:1
├── name → "Abhishek"
├── age  → "25"
└── city → "Bangalore"
```

---

# 📖 View All Fields

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

# ✏️ Update Existing Field

```bash
HSET user:1 city "Mumbai"
```

The `city` field is updated.

---

# 🔢 Return Value

| Output | Meaning |
|---|---|
| `(integer) 1` | New field added |
| `(integer) 0` | Existing field updated |

---

# ⚡ Important Points

- Creates hash automatically if not present
- Adds new fields or updates existing ones
- Works only with hashes

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 User profiles | Store user details |
| 📦 Product info | Store attributes |
| ⚙️ Configurations | Application settings |
| 🛒 Cart details | Structured shopping data |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HSET key field value` | Add or update hash field |

`HSET` is the main command used for storing data inside Redis hashes 🚀
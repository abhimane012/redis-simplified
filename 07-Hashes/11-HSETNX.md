# 🛡️ HSETNX in Redis

Redis provides the `HSETNX` command to set a field in a hash **only if the field does not already exist**.

`HSETNX` stands for:

> Hash Set if Not eXists

---

# 💻 Syntax

```bash
HSETNX key field value
```

---

# 🧪 Example

Create a hash field:

```bash
HSET user:1 name "Abhishek"
```

Try setting the same field again:

```bash
HSETNX user:1 name "RedisUser"
```

Output:

```text
(integer) 0
```

Meaning:

- Field already exists ❌
- Value not updated

---

# ➕ Successful Case

Add a new field:

```bash
HSETNX user:1 age 25
```

Output:

```text
(integer) 1
```

Now hash becomes:

```text
user:1
├── name → "Abhishek"
└── age  → "25"
```

---

# 🔢 Return Values

| Output | Meaning |
|---|---|
| `(integer) 1` | Field created successfully |
| `(integer) 0` | Field already exists |

---

# ⚡ Important Points

- Does not overwrite existing fields
- Works only inside hashes
- Creates field only if missing

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 Default user setup | Add initial fields safely |
| ⚙️ Configuration | Set values only once |
| 🛒 Product initialization | Avoid overwriting data |
| 🔐 Safe data creation | Prevent accidental updates |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HSETNX key field value` | Set field only if it does not exist |

`HSETNX` is useful when you want to safely initialize hash fields without overwriting existing data 🚀
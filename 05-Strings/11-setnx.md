# 🛡️ SETNX in Redis

Redis provides the `SETNX` command to set a key only if it does not already exist.

`SETNX` stands for:

> **SET if Not eXists**

---

# 💻 Syntax

```bash
SETNX key value
```

---

# 🧪 Example

```bash
SETNX username "abhishek"
```

Output:

```text
(integer) 1
```

This means:

- Key was created successfully ✅

---

# 📖 Check the Value

```bash
GET username
```

Output:

```text
"abhishek"
```

---

# ❌ Example When Key Already Exists

```bash
SETNX username "redis_user"
```

Output:

```text
(integer) 0
```

Meaning:

- Key already exists
- Value was not changed ❌

---

# 📌 Important Behavior

`SETNX` never overwrites existing keys.

This makes it useful for safe inserts.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🔐 Distributed locks | Prevent multiple processes |
| 👤 Unique user creation | Avoid duplicates |
| ⚙️ One-time setup | Initialize data safely |
| 📦 Cache initialization | Store only once |

---

# ⚡ Difference Between SET and SETNX

| Command | Behavior |
|---|---|
| `SET` | Always sets value |
| `SETNX` | Sets value only if key does not exist |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SETNX key value` | Set key only if it does not exist |

`SETNX` is useful when you want to avoid overwriting existing Redis data 🚀
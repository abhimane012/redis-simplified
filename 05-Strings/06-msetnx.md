# 🛡️ MSETNX in Redis

Redis provides the `MSETNX` command to set multiple key-value pairs only if **none of the keys already exist**.

`MSETNX` stands for:

> **MSET if Not eXists**

---

# 💻 Syntax

```bash
MSETNX key1 value1 key2 value2
```

---

# 🧪 Example

```bash
MSETNX name "Abhishek" country "India"
```

Output:

```text
(integer) 1
```

This creates:

```text
name    -> "Abhishek"
country -> "India"
```

---

# ⚡ Important Behavior

`MSETNX` works like an **all-or-nothing operation**.

Meaning:

- ✅ All keys are set if none exist
- ❌ Nothing is set if even one key already exists

---

# ❌ Example with Existing Key

Create a key:

```bash
SET name "Redis"
```

Now run:

```bash
MSETNX name "Abhishek" age 25
```

Output:

```text
(integer) 0
```

Nothing is stored because `name` already exists.

Even `age` is not created ❌

---

# 🔢 Return Values

| Output | Meaning |
|---|---|
| `(integer) 1` | All keys set successfully |
| `(integer) 0` | Operation failed because at least one key exists |

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🔐 Avoid overwriting data | Safe inserts |
| 👤 User registration | Prevent duplicate users |
| ⚙️ Configuration setup | Create defaults only once |
| 📦 Atomic operations | Store multiple values safely |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `MSETNX` | Set multiple keys only if none exist |

`MSETNX` is useful when you want safe multi-key creation without overwriting existing data 🚀
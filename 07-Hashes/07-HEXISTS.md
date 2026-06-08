# ✅ HEXISTS in Redis

Redis provides the `HEXISTS` command to check whether a field exists inside a hash.

---

# 💻 Syntax

```bash
HEXISTS key field
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 name "Abhishek" age 25
```

Check if field exists:

```bash
HEXISTS user:1 name
```

Output:

```text
(integer) 1
```

Meaning:

- Field exists ✅

---

# ❌ Check Non-Existing Field

```bash
HEXISTS user:1 city
```

Output:

```text
(integer) 0
```

Meaning:

- Field does not exist ❌

---

# 🔢 Return Values

| Output | Meaning |
|---|---|
| `(integer) 1` | Field exists |
| `(integer) 0` | Field does not exist |

---

# ⚡ Important Points

- Checks only field existence
- Works only with hashes
- Does not return field value

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 Validate profile fields | Check user data |
| ⚙️ Verify settings | Ensure config exists |
| 📦 Product attributes | Check field availability |
| 🛒 Cart systems | Verify item details |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HEXISTS key field` | Check if field exists in hash |

`HEXISTS` helps verify fields inside Redis hashes quickly 🚀
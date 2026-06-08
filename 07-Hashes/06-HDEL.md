# ❌ HDEL in Redis

Redis provides the `HDEL` command to delete one or more fields from a hash.

---

# 💻 Syntax

```bash
HDEL key field
```

Delete multiple fields:

```bash
HDEL key field1 field2 field3
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 name "Abhishek" age 25 city "Bangalore"
```

Delete a field:

```bash
HDEL user:1 age
```

---

# 📖 Check Updated Hash

```bash
HGETALL user:1
```

Output:

```text
1) "name"
2) "Abhishek"
3) "city"
4) "Bangalore"
```

The `age` field was removed.

---

# ➕ Delete Multiple Fields

```bash
HDEL user:1 name city
```

Both fields are deleted.

---

# 🔢 Return Value

`HDEL` returns the number of fields removed.

Example:

```text
(integer) 1
```

---

# ❌ Non-Existing Field

```bash
HDEL user:1 country
```

Output:

```text
(integer) 0
```

Because the field does not exist.

---

# ⚡ Important Points

- Removes only specified fields
- Hash remains if other fields still exist
- Works only with hashes

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👤 Remove user data | Delete profile fields |
| ⚙️ Cleanup settings | Remove old configurations |
| 📦 Update product info | Delete unused attributes |
| 🛒 Modify cart data | Remove item details |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HDEL key field` | Delete field from hash |

`HDEL` helps remove unwanted fields from Redis hashes 🚀
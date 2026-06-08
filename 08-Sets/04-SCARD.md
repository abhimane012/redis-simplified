# 📏 SCARD in Redis

Redis provides the `SCARD` command to get the number of elements (cardinality) in a Set.

---

# 💻 Syntax

```bash
SCARD key
```

---

# 🧪 Example

Create a set:

```bash
SADD fruits apple banana mango orange
```

Check size:

```bash
SCARD fruits
```

---

# 📖 Output

```text
(integer) 4
```

---

# 📌 What SCARD Returns

- Total number of **unique members** in the set

Example set:

```text
{"apple", "banana", "mango", "orange"}
```

So result is:

```text
4
```

---

# ❌ Non-Existing Set

```bash
SCARD unknown_set
```

Output:

```text
(integer) 0
```

---

# ⚡ Important Points

- Works only with Sets
- Very fast operation (O(1))
- Only counts unique values

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 User count | Number of unique users |
| 👍 Likes | Count likes |
| 🏷️ Tags | Count tags |
| 🎮 Players | Active players count |
| 📊 Analytics | Unique event tracking |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SCARD key` | Get number of elements in a set |

`SCARD` helps quickly find the size of a Redis Set 🚀
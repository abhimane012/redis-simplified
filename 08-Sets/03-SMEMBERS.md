# 📖 SMEMBERS in Redis

Redis provides the `SMEMBERS` command to get all members of a Set.

It returns every value stored inside the set.

---

# 💻 Syntax

```bash
SMEMBERS key
```

---

# 🧪 Example

Create a set:

```bash
SADD fruits apple banana mango
```

Get all members:

```bash
SMEMBERS fruits
```

---

# 📖 Output

```text
1) "apple"
2) "banana"
3) "mango"
```

---

# 📌 Important Behavior

- Returns all unique values
- Order is not guaranteed
- Works only with Sets

---

# ❌ Empty or Non-Existing Set

```bash
SMEMBERS unknown_set
```

Output:

```text
(empty list or set)
```

---

# ⚡ Key Points

- Retrieves full set content
- No sorting or ordering
- Useful for reading complete unique data

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 User lists | Get all users |
| 🏷️ Tags | Fetch all tags |
| 👍 Likes | Get all likes |
| 🎮 Players | List active players |
| 🔐 Roles | View permissions |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SMEMBERS key` | Get all members of a set |

`SMEMBERS` is used to retrieve all unique values from Redis Sets 🚀
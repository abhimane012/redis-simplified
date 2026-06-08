# ➕ SADD in Redis

Redis provides the `SADD` command to add one or more members into a Set.

A Set automatically stores only **unique values**.

---

# 💻 Syntax

```bash
SADD key member1 member2 member3
```

---

# 🧪 Example

Add values to a set:

```bash
SADD fruits apple banana mango
```

---

# 📖 Result

```text
(integer) 3
```

Meaning:

- 3 new items were added

---

# ➕ Adding Duplicate Values

```bash
SADD fruits apple banana orange
```

Only `"orange"` is newly added.

Output:

```text
(integer) 1
```

Updated set:

```text
{"apple", "banana", "mango", "orange"}
```

---

# 📌 Important Behavior

- ❌ Duplicates are ignored
- 🔒 Only unique values are stored
- ⚡ Very fast insert operation

---

# ❌ Add to Non-Existing Set

```bash
SADD tags redis cache backend
```

Redis automatically creates the set.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 Unique users | Store user IDs |
| 🏷️ Tags system | Store post tags |
| 👍 Likes system | Track unique likes |
| 🎮 Game players | Store active players |
| 🔐 Permissions | Store roles |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SADD key member` | Add members to a set |

`SADD` is used to store unique values efficiently in Redis Sets 🚀
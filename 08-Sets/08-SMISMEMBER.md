# 🔍 SMISMEMBER in Redis

Redis provides the `SMISMEMBER` command to check whether **multiple values exist in a Set** at once.

It is like `SISMEMBER`, but for many members in a single call.

---

# 💻 Syntax

```bash
SMISMEMBER key member1 member2 member3
```

---

# 🧪 Example

Create a set:

```bash
SADD fruits apple banana mango orange
```

Check multiple values:

```bash
SMISMEMBER fruits apple kiwi mango
```

---

# 📖 Output

```text
1) (integer) 1
2) (integer) 0
3) (integer) 1
```

---

# 📌 Meaning of Output

| Member | Result | Meaning |
|---|---|---|
| apple | 1 | exists |
| kiwi | 0 | does not exist |
| mango | 1 | exists |

---

# ⚡ Important Points

- Checks multiple members in one command
- Faster than calling `SISMEMBER` multiple times
- Works only with Sets
- Returns results in same order as input

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 User validation | Check multiple users |
| 🏷️ Tags check | Validate multiple tags |
| 👍 Likes system | Check multiple likes |
| 🎮 Game players | Verify active players |
| 🔐 Permissions | Check multiple roles |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SMISMEMBER key members...` | Check multiple members in a set |

`SMISMEMBER` is useful for batch membership checks in Redis Sets 🚀
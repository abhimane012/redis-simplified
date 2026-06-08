# 🔍 SISMEMBER in Redis

Redis provides the `SISMEMBER` command to check whether a value exists in a Set.

---

# 💻 Syntax

```bash
SISMEMBER key member
```

---

# 🧪 Example

Create a set:

```bash
SADD fruits apple banana mango
```

Check if `"banana"` exists:

```bash
SISMEMBER fruits banana
```

---

# 📖 Output

```text
(integer) 1
```

Meaning:

- ✔️ Member exists in the set

---

# ❌ Example (Not Present)

```bash
SISMEMBER fruits orange
```

Output:

```text
(integer) 0
```

Meaning:

- ❌ Member not found

---

# 🔢 Return Values

| Output | Meaning |
|---|---|
| `(integer) 1` | Member exists |
| `(integer) 0` | Member does not exist |

---

# ⚡ Important Points

- Works only with Sets
- Very fast lookup (O(1))
- Checks membership only, not value details

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 User validation | Check if user exists |
| 👍 Likes system | Check if liked |
| 🏷️ Tags | Verify tag presence |
| 🎮 Game players | Check active players |
| 🔐 Permissions | Check role access |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SISMEMBER key member` | Check if a value exists in a set |

`SISMEMBER` is used for fast membership checking in Redis Sets 🚀
# 🔄 SMOVE in Redis

Redis provides the `SMOVE` command to move a member from one Set to another.

It removes the element from the source set and adds it to the destination set.

---

# 💻 Syntax

```bash
SMOVE source destination member
```

---

# 🧪 Example

Create source set:

```bash
SADD fruits apple banana mango
```

Create destination set:

```bash
SADD basket orange grape
```

---

# 🔄 Move a Member

```bash
SMOVE fruits basket banana
```

---

# 📖 Result

Source set (`fruits`):

```text
{"apple", "mango"}
```

Destination set (`basket`):

```text
{"orange", "grape", "banana"}
```

---

# ❌ If Member Does Not Exist

```bash
SMOVE fruits basket kiwi
```

Output:

```text
(integer) 0
```

Nothing happens.

---

# 🔢 Return Values

| Output | Meaning |
|---|---|
| `(integer) 1` | Move successful |
| `(integer) 0` | Member not found |

---

# ⚡ Important Points

- Removes from source set
- Adds to destination set
- Works only with Sets
- No duplicate values allowed in destination

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 User status change | Active → inactive |
| 🛒 Workflow systems | Move tasks between stages |
| 🎮 Game states | Move players between teams |
| 📦 Data processing | Move items across buckets |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SMOVE source destination member` | Move a member between sets |

`SMOVE` is useful for transferring data safely between Redis Sets 🚀
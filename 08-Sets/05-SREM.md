# ❌ SREM in Redis

Redis provides the `SREM` command to remove one or more members from a Set.

---

# 💻 Syntax

```bash
SREM key member1 member2 member3
```

---

# 🧪 Example

Create a set:

```bash
SADD fruits apple banana mango orange
```

Remove one item:

```bash
SREM fruits banana
```

---

# 📖 Result

```text
(integer) 1
```

Meaning:

- 1 item was removed successfully

---

# 📌 Check Updated Set

```bash
SMEMBERS fruits
```

Output:

```text
1) "apple"
2) "mango"
3) "orange"
```

---

# ➖ Remove Multiple Items

```bash
SREM fruits apple orange
```

Output:

```text
(integer) 2
```

---

# ❌ Removing Non-Existing Member

```bash
SREM fruits kiwi
```

Output:

```text
(integer) 0
```

Because `"kiwi"` is not in the set.

---

# ⚡ Important Points

- Removes only existing members
- Ignores missing values
- Works only with Sets
- Order does not matter

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 Remove users | Remove inactive users |
| 🏷️ Remove tags | Delete unwanted tags |
| 👍 Unlike system | Remove likes |
| 🎮 Game players | Remove disconnected players |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SREM key member` | Remove members from a set |

`SREM` helps delete specific values from Redis Sets efficiently 🚀
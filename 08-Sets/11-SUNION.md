# 🔗 SUNION in Redis

Redis provides the `SUNION` command to get the **union of multiple Sets**.

Union means:

> Combine all unique elements from multiple sets

---

# 💻 Syntax

```bash
SUNION key1 key2 key3
```

---

# 🧪 Example

Create sets:

```bash
SADD set1 apple banana mango
SADD set2 mango orange grape
```

---

# 🔗 Get Union

```bash
SUNION set1 set2
```

---

# 📖 Output

```text
1) "apple"
2) "banana"
3) "mango"
4) "orange"
5) "grape"
```

---

# 📌 Important Behavior

- Combines all elements
- Removes duplicates automatically
- Does NOT modify original sets

---

# ⚡ Key Idea

Example:

```text
set1 = {apple, banana, mango}
set2 = {mango, orange, grape}
```

Union result:

```text
{apple, banana, mango, orange, grape}
```

---

# ❌ Non-Existing Sets

```bash
SUNION set1 set3
```

If `set3` does not exist, Redis treats it as empty.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 User groups | Combine audiences |
| 🏷️ Tags merging | Merge tag sets |
| 👍 Likes aggregation | Combine reactions |
| 🎮 Game players | Merge teams |
| 📊 Analytics | Combine datasets |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SUNION key1 key2` | Get all unique elements from multiple sets |

`SUNION` is used to combine Redis Sets while keeping values unique 🚀
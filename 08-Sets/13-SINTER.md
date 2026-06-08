# 🔗 SINTER in Redis

Redis provides the `SINTER` command to get the **intersection of multiple Sets**.

Intersection means:

> Only the common elements present in all sets

---

# 💻 Syntax

```bash
SINTER key1 key2 key3
```

---

# 🧪 Example

Create sets:

```bash
SADD set1 apple banana mango
SADD set2 mango orange banana
SADD set3 banana mango grape
```

---

# 🔗 Get Intersection

```bash
SINTER set1 set2 set3
```

---

# 📖 Output

```text
1) "banana"
2) "mango"
```

---

# 📌 Important Behavior

- Returns only common elements
- Does NOT modify original sets
- Order is not guaranteed

---

# ⚡ Key Idea

Example:

```text
set1 = {apple, banana, mango}
set2 = {mango, orange, banana}
set3 = {banana, mango, grape}
```

Intersection result:

```text
{banana, mango}
```

---

# ❌ No Common Elements

If there are no common values:

```bash
SINTER set1 set2
```

Output:

```text
(empty set)
```

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 Common users | Users in multiple groups |
| 🏷️ Shared tags | Find overlapping tags |
| 👍 Mutual likes | Common liked items |
| 🎮 Game matchmaking | Shared players |
| 📊 Analytics | Common dataset analysis |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SINTER key1 key2` | Get common elements from sets |

`SINTER` is useful for finding shared values across Redis Sets 🚀
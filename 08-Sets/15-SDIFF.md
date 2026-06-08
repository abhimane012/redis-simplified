# ➖ SDIFF in Redis

Redis provides the `SDIFF` command to get the **difference between sets**.

Difference means:

> Elements present in the first set but NOT in the other sets

---

# 💻 Syntax

```bash
SDIFF key1 key2 key3
```

---

# 🧪 Example

Create sets:

```bash
SADD set1 apple banana mango orange
SADD set2 banana mango
SADD set3 mango grape
```

---

# ➖ Get Difference

```bash
SDIFF set1 set2 set3
```

---

# 📖 Output

```text
1) "apple"
2) "orange"
```

---

# 📌 Important Behavior

- Starts from first set only
- Removes elements found in other sets
- Does NOT modify original sets
- Order is not guaranteed

---

# ⚡ Key Idea

Example:

```text
set1 = {apple, banana, mango, orange}
set2 = {banana, mango}
set3 = {mango, grape}
```

Step-by-step:

- Remove elements in set2 → banana, mango
- Remove elements in set3 → mango

Final result:

```text
{apple, orange}
```

---

# ❌ No Difference

If everything matches:

```bash
SDIFF set1 set2 set3
```

Output:

```text
(empty set)
```

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 Unique users | Users not in other groups |
| 🏷️ Excluded tags | Filter unwanted tags |
| 👍 Recommendation systems | Remove common items |
| 🎮 Game logic | Players not in other teams |
| 📊 Data filtering | Find exclusive data |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SDIFF key1 key2` | Get elements only in first set |

`SDIFF` helps find unique elements in Redis Sets 🚀
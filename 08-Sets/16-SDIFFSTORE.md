# 💾 SDIFFSTORE in Redis

Redis provides the `SDIFFSTORE` command to **store the difference of sets into another set**.

It works like `SDIFF`, but instead of just returning the result, it saves it.

---

# 💻 Syntax

```bash
SDIFFSTORE destination key1 key2 key3
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

# 💾 Store Difference

```bash
SDIFFSTORE result set1 set2 set3
```

---

# 📖 Output

```text
(integer) 2
```

Meaning:

- 2 elements were stored in `result`

---

# 📦 Check Stored Set

```bash
SMEMBERS result
```

Output:

```text
1) "apple"
2) "orange"
```

---

# 📌 Important Behavior

- Takes difference from first set
- Removes elements found in other sets
- Stores result in destination set
- Overwrites destination if it already exists

---

# ⚡ Key Idea

```text
set1 = {apple, banana, mango, orange}
set2 = {banana, mango}
set3 = {mango, grape}
```

Result:

```text
{apple, orange}
```

Stored in `result`

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 Exclusion lists | Users not in other groups |
| 🏷️ Filtering data | Remove unwanted tags |
| 👍 Recommendation systems | Exclude common items |
| 🎮 Game logic | Remove overlapping players |
| 📊 Analytics | Store filtered datasets |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SDIFFSTORE dest key1 key2` | Store difference of sets |

`SDIFFSTORE` is used when you want to save set differences in Redis 🚀
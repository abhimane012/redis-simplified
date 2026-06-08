# 💾 SUNIONSTORE in Redis

Redis provides the `SUNIONSTORE` command to **combine multiple Sets and store the result in another Set**.

It is like `SUNION`, but instead of just returning the result, it saves it.

---

# 💻 Syntax

```bash
SUNIONSTORE destination key1 key2 key3
```

---

# 🧪 Example

Create sets:

```bash
SADD set1 apple banana mango
SADD set2 mango orange grape
```

---

# 💾 Store Union Result

```bash
SUNIONSTORE all_fruits set1 set2
```

---

# 📖 Result

```text
(integer) 5
```

Meaning:

- 5 unique elements were stored in `all_fruits`

---

# 📦 Check Stored Set

```bash
SMEMBERS all_fruits
```

Output:

```text
1) "apple"
2) "banana"
3) "mango"
4) "orange"
5) "grape"
```

---

# 📌 Important Behavior

- Combines multiple sets
- Removes duplicates automatically
- Stores result in destination set
- Overwrites destination if it already exists

---

# ⚡ Key Idea

Input:

```text
set1 = {apple, banana, mango}
set2 = {mango, orange, grape}
```

Output stored in `all_fruits`:

```text
{apple, banana, mango, orange, grape}
```

---

# ❌ Non-Existing Sets

If a set does not exist, Redis treats it as empty.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 User groups | Merge audiences |
| 🏷️ Tags aggregation | Combine tags |
| 👍 Likes system | Combine reactions |
| 🎮 Game teams | Merge players |
| 📊 Analytics | Store combined datasets |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SUNIONSTORE dest key1 key2` | Store union of sets in destination |

`SUNIONSTORE` is used when you want to persist union results in Redis Sets 🚀
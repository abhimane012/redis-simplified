# 🎯 Redis Sets

Redis Sets are a collection of **unique values**.

This means:

- ❌ Duplicate values are not allowed
- 📦 Order is not guaranteed

---

# 🧠 Think of a Set Like

A bag of unique items:

```text
["apple", "banana", "mango"]
```

If you try to add `"apple"` again, Redis will ignore it.

---

# ⚡ Features of Redis Sets

- 🔒 Stores only unique values
- 🚀 Very fast operations
- 🎲 No order guaranteed
- 🔍 Easy membership checking

---

# 🌍 Common Use Cases

- 👥 Unique users
- 🏷️ Tags system
- 👍 Likes / dislikes
- 🎮 Game players list
- 🔐 Permissions / roles

---

# 🛠️ Common Redis Set Commands

| Command | Purpose |
|---|---|
| `SADD` | Add values to set |
| `SMEMBERS` | Get all members |
| `SISMEMBER` | Check if value exists |
| `SREM` | Remove value |
| `SCARD` | Count elements |
| `SPOP` | Remove random element |
| `SRANDMEMBER` | Get random element |
| `SUNION` | Union of sets |
| `SINTER` | Intersection of sets |
| `SDIFF` | Difference between sets |

---

# ❗ Key Idea

Sets automatically handle uniqueness.

So if you insert duplicates:

```bash
SADD tags redis redis cache cache
```

Result will still be:

```text
{"redis", "cache"}
```

---

# 📝 Summary

- 🎯 Sets store unique values only
- ⚡ Fast and efficient
- 📦 No ordering guaranteed
- 🔍 Great for membership and uniqueness checks

Redis Sets are powerful for handling unique collections of data 🚀
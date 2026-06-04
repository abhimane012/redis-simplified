# ✂️ LTRIM in Redis

Redis provides the `LTRIM` command to keep only a specific range of items in a list.

All other items are removed automatically.

---

# 💻 Syntax

```bash
LTRIM key start end
```

---

# 🧪 Example

Create a list:

```bash
RPUSH fruits apple banana mango orange grape
```

List:

```text
["apple", "banana", "mango", "orange", "grape"]
```

Keep items from index `1` to `3`:

```bash
LTRIM fruits 1 3
```

---

# 📖 Check Updated List

```bash
LRANGE fruits 0 -1
```

Output:

```text
1) "banana"
2) "mango"
3) "orange"
```

Other items were removed.

---

# 📌 Understanding Indexes

| Index | Value |
|---|---|
| `0` | First item |
| `-1` | Last item |

---

# 🔚 Using Negative Indexes

Example:

```bash
LTRIM fruits -2 -1
```

Keeps only the last two items.

---

# ⚡ Important Points

- Items outside the range are deleted
- Start and end indexes are included
- Works only with lists

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 📜 Keep recent logs | Store latest activities |
| 💬 Chat history | Keep recent messages |
| 📨 Queues | Limit queue size |
| 📊 Recent events | Maintain rolling data |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LTRIM key start end` | Keep only selected range in list |

`LTRIM` is useful for limiting list size and keeping recent data 🚀
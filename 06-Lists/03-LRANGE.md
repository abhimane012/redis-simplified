# 📖 LRANGE in Redis

Redis provides the `LRANGE` command to read items from a list.

It returns elements between a start and end index.

---

# 💻 Syntax

```bash
LRANGE key start end
```

---

# 🧪 Example

Create a list:

```bash
RPUSH fruits apple banana mango orange
```

Read all items:

```bash
LRANGE fruits 0 -1
```

Output:

```text
1) "apple"
2) "banana"
3) "mango"
4) "orange"
```

---

# 📌 Understanding Indexes

| Index | Meaning |
|---|---|
| `0` | First item |
| `1` | Second item |
| `-1` | Last item |

---

# 🧪 Read Specific Range

```bash
LRANGE fruits 1 2
```

Output:

```text
1) "banana"
2) "mango"
```

Reads items from index `1` to `2`.

---

# 🔚 Using Negative Indexes

```bash
LRANGE fruits -2 -1
```

Output:

```text
1) "mango"
2) "orange"
```

Negative indexes start from the end of the list.

---

# ⚡ Important Points

- Start and end indexes are included
- `0 -1` means entire list
- Works only with Redis lists

---

# 🌍 Common Use Cases

- 📜 Read activity feeds
- 📨 Read queue items
- 💬 Fetch chat messages
- 📋 Retrieve ordered data

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LRANGE key start end` | Read items from a list |

`LRANGE` is used to fetch values from Redis lists efficiently 🚀
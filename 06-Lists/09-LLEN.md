# 📏 LLEN in Redis

Redis provides the `LLEN` command to get the number of items in a list.

`LLEN` stands for:

> List Length

---

# 💻 Syntax

```bash
LLEN key
```

---

# 🧪 Example

Create a list:

```bash
RPUSH fruits apple banana mango orange
```

Get list length:

```bash
LLEN fruits
```

Output:

```text
(integer) 4
```

---

# 📖 Understanding the Result

List:

```text
["apple", "banana", "mango", "orange"]
```

Total items:

```text
4
```

So Redis returns:

```text
(integer) 4
```

---

# ❌ Non-Existing List

```bash
LLEN unknown_list
```

Output:

```text
(integer) 0
```

Because the list does not exist.

---

# ⚡ Important Points

- Returns total number of items
- Works only with lists
- Very fast operation

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 📨 Queue size | Count pending jobs |
| 💬 Chat messages | Count messages |
| 📜 Activity feeds | Track feed size |
| 🛒 Task lists | Count tasks |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LLEN key` | Get total items in a list |

`LLEN` helps measure the size of Redis lists quickly 🚀
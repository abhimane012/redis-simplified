# 📋 Redis Lists

Redis Lists store multiple values in order.

Lists allow adding and removing items from both the left and right sides.

They are useful for handling ordered collections of data.

Example:

```text
["apple", "banana", "mango"]
```

---

# ⚡ Features of Redis Lists

- 📌 Ordered collection
- ➕ Add items from both sides
- ➖ Remove items from both sides
- 🔁 Duplicate values allowed
- 🚀 Fast insert and delete operations

---

# 🛠️ Common Redis List Commands

| Command | Purpose |
|---|---|
| `LPUSH` | Add item to left side |
| `RPUSH` | Add item to right side |
| `LPUSHX` | Push to existing list from left |
| `RPUSHX` | Push to existing list from right |
| `LPOP` | Remove item from left |
| `RPOP` | Remove item from right |
| `LRANGE` | Get list items |
| `LLEN` | Get list length |
| `LINDEX` | Get item by index |
| `LSET` | Update item at index |
| `LREM` | Remove matching items |
| `LTRIM` | Trim list to range |
| `LINSERT` | Insert before or after item |
| `LMOVE` | Move item between lists |
| `BLPOP` | Blocking left pop |
| `BRPOP` | Blocking right pop |

---

# 🌍 Common Use Cases

- 📨 Queues
- 💬 Chat systems
- 📜 Activity feeds
- 🛒 Task processing
- 🔄 Background jobs

Redis Lists are widely used for managing ordered and sequential data 🚀
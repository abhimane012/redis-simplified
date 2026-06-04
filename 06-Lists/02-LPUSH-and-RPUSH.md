# ➕ LPUSH and RPUSH in Redis

Redis provides `LPUSH` and `RPUSH` commands to add items into a list.

---

# ⬅️ LPUSH

`LPUSH` adds items to the **left side** of the list.

---

# 💻 Syntax

```bash
LPUSH key value1 value2
```

---

# 🧪 Example

```bash
LPUSH fruits apple banana mango
```

List becomes:

```text
["mango", "banana", "apple"]
```

Items are inserted from the left side.

---

# ➡️ RPUSH

`RPUSH` adds items to the **right side** of the list.

---

# 💻 Syntax

```bash
RPUSH key value1 value2
```

---

# 🧪 Example

```bash
RPUSH fruits apple banana mango
```

List becomes:

```text
["apple", "banana", "mango"]
```

Items are inserted from the right side.

---

# 📖 Read List Values

```bash
LRANGE fruits 0 -1
```

---

# ⚡ Difference Between LPUSH and RPUSH

| Command | Adds Item To |
|---|---|
| `LPUSH` | Left side |
| `RPUSH` | Right side |

---

# 🌍 Common Use Cases

| Command | Common Use |
|---|---|
| `LPUSH` | Stack behavior |
| `RPUSH` | Queue behavior |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LPUSH` | Insert items from left |
| `RPUSH` | Insert items from right |

`LPUSH` and `RPUSH` are basic and commonly used Redis list commands 🚀
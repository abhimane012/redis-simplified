# ➖ LPOP and RPOP in Redis

Redis provides `LPOP` and `RPOP` commands to remove items from a list.

---

# ⬅️ LPOP

`LPOP` removes and returns the item from the **left side** of the list.

---

# 💻 Syntax

```bash
LPOP key
```

---

# 🧪 Example

Create a list:

```bash
RPUSH fruits apple banana mango
```

List:

```text
["apple", "banana", "mango"]
```

Run:

```bash
LPOP fruits
```

Output:

```text
"apple"
```

Updated list:

```text
["banana", "mango"]
```

---

# ➡️ RPOP

`RPOP` removes and returns the item from the **right side** of the list.

---

# 💻 Syntax

```bash
RPOP key
```

---

# 🧪 Example

```bash
RPOP fruits
```

Output:

```text
"mango"
```

Updated list:

```text
["apple", "banana"]
```

---

# 📖 View Remaining List

```bash
LRANGE fruits 0 -1
```

---

# ❌ Empty List

If the list is empty:

```bash
LPOP fruits
```

Output:

```text
(nil)
```

---

# ⚡ Difference Between LPOP and RPOP

| Command | Removes From |
|---|---|
| `LPOP` | Left side |
| `RPOP` | Right side |

---

# 🌍 Common Use Cases

| Command | Common Use |
|---|---|
| `LPOP` | Queue processing |
| `RPOP` | Stack processing |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LPOP key` | Remove item from left |
| `RPOP key` | Remove item from right |

`LPOP` and `RPOP` are commonly used for queues and task processing 🚀
# ➕ LINSERT in Redis

Redis provides the `LINSERT` command to insert a new item before or after an existing item in a list.

---

# 💻 Syntax

```bash
LINSERT key BEFORE pivot value
```

or

```bash
LINSERT key AFTER pivot value
```

---

# 🧪 Example List

```bash
RPUSH fruits apple banana mango
```

List:

```text
["apple", "banana", "mango"]
```

---

# ⬅️ Insert BEFORE an Item

```bash
LINSERT fruits BEFORE banana orange
```

Updated list:

```text
["apple", "orange", "banana", "mango"]
```

---

# ➡️ Insert AFTER an Item

```bash
LINSERT fruits AFTER banana grape
```

Updated list:

```text
["apple", "banana", "grape", "mango"]
```

---

# 📖 View List

```bash
LRANGE fruits 0 -1
```

---

# ⚠️ If Pivot Item Does Not Exist

```bash
LINSERT fruits BEFORE kiwi lemon
```

Output:

```text
(integer) -1
```

Meaning:

- Pivot item was not found
- Nothing was inserted

---

# 🔢 Return Value

`LINSERT` returns:

- 📏 Length of updated list
- `-1` if pivot does not exist

---

# 🌍 Common Use Cases

- 📜 Insert ordered items
- 💬 Add messages at specific position
- 🛒 Modify task queues
- 📋 Manage custom sequences

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LINSERT BEFORE` | Insert before an item |
| `LINSERT AFTER` | Insert after an item |

`LINSERT` helps add elements at specific positions inside Redis lists 🚀
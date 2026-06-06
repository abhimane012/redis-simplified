# 🔄 LMOVE in Redis

Redis provides the `LMOVE` command to move an item from one list to another.

It removes an item from the source list and inserts it into the destination list.

---

# 💻 Syntax

```bash
LMOVE source destination LEFT|RIGHT LEFT|RIGHT
```

---

# 📌 Syntax Meaning

```text
LMOVE source destination source_side destination_side
```

- First `LEFT|RIGHT` → remove from source side
- Second `LEFT|RIGHT` → insert into destination side

---

# 🧪 Example

Create source list:

```bash
RPUSH fruits apple banana mango
```

Create destination list:

```bash
RPUSH basket orange grape
```

---

# 🔄 Move Item

```bash
LMOVE fruits basket LEFT RIGHT
```

Meaning:

- Remove from left side of `fruits`
- Insert into right side of `basket`

---

# 📖 Result

Updated `fruits` list:

```text
["banana", "mango"]
```

Updated `basket` list:

```text
["orange", "grape", "apple"]
```

---

# 📦 Another Example

```bash
LMOVE fruits basket RIGHT LEFT
```

Meaning:

- Remove from right side of `fruits`
- Insert into left side of `basket`

---

# ⚡ Possible Move Combinations

| Source Side | Destination Side |
|---|---|
| `LEFT LEFT` | Left → Left |
| `LEFT RIGHT` | Left → Right |
| `RIGHT LEFT` | Right → Left |
| `RIGHT RIGHT` | Right → Right |

---

# ❌ Empty Source List

If source list is empty:

```text
(nil)
```

is returned.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 📨 Queue processing | Move jobs between queues |
| ⚙️ Task management | Transfer tasks |
| 💬 Message handling | Move messages |
| 🔄 Workflow systems | Process pipelines |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LMOVE` | Move item between lists |

`LMOVE` is useful for queue systems and workflow processing in Redis 🚀
# ❌ LREM in Redis

Redis provides the `LREM` command to remove matching items from a list.

`LREM` stands for:

> List Remove

---

# 💻 Syntax

```bash
LREM key count value
```

---

# 🧪 Example List

```bash
RPUSH fruits apple banana mango banana banana orange
```

List:

```text
["apple", "banana", "mango", "banana", "banana", "orange"]
```

---

# 🔢 Understanding `count`

The `count` value controls:

- 🔄 How many items to remove
- 📍 Direction of removal

---

# ➡️ Remove from Left

```bash
LREM fruits 1 banana
```

Output:

```text
(integer) 1
```

Updated list:

```text
["apple", "mango", "banana", "banana", "orange"]
```

Only first matching `"banana"` from the left was removed.

---

# ⬅️ Remove from Right

```bash
LREM fruits -1 banana
```

Updated list:

```text
["apple", "banana", "mango", "banana", "orange"]
```

Removes one matching item starting from the right side.

---

# 🧹 Remove All Matching Items

```bash
LREM fruits 0 banana
```

Updated list:

```text
["apple", "mango", "orange"]
```

All `"banana"` values are removed.

---

# 📌 Meaning of Count Values

| Count | Behavior |
|---|---|
| `> 0` | Remove from left |
| `< 0` | Remove from right |
| `0` | Remove all matching items |

---

# 📖 Check Updated List

```bash
LRANGE fruits 0 -1
```

---

# ⚡ Important Points

- Removes matching values only
- Order of remaining items stays same
- Works only with lists

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🧹 Remove duplicate items | Cleanup lists |
| 💬 Delete messages | Remove chat entries |
| 📜 Manage task lists | Remove completed tasks |
| 📨 Queue cleanup | Delete processed jobs |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LREM key count value` | Remove matching items from list |

`LREM` helps clean and manage Redis lists efficiently 🚀
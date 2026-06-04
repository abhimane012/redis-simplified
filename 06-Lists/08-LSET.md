# ✏️ LSET in Redis

Redis provides the `LSET` command to update an item at a specific index in a list.

---

# 💻 Syntax

```bash
LSET key index value
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

Update item at index `1`:

```bash
LSET fruits 1 orange
```

---

# 📖 Check Updated List

```bash
LRANGE fruits 0 -1
```

Output:

```text
1) "apple"
2) "orange"
3) "mango"
```

The value `"banana"` was replaced with `"orange"`.

---

# 📌 Understanding Indexes

| Index | Value |
|---|---|
| `0` | First item |
| `1` | Second item |
| `-1` | Last item |

---

# 🔚 Using Negative Indexes

```bash
LSET fruits -1 grape
```

Updates the last item.

Updated list:

```text
["apple", "banana", "grape"]
```

---

# ❌ Invalid Index

```bash
LSET fruits 10 kiwi
```

Output:

```text
(error) ERR index out of range
```

Because index `10` does not exist.

---

# ⚡ Important Points

- Replaces existing value only
- Cannot add new items
- Works only with lists

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| ✏️ Edit task list | Update queue items |
| 💬 Modify messages | Change list content |
| 📜 Update ordered data | Replace specific element |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LSET key index value` | Update item at specific index |

`LSET` helps modify existing values inside Redis lists 🚀
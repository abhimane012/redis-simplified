# 🎯 LINDEX in Redis

Redis provides the `LINDEX` command to get an item from a list using its index position.

---

# 💻 Syntax

```bash
LINDEX key index
```

---

# 🧪 Example

Create a list:

```bash
RPUSH fruits apple banana mango orange
```

Get item at index `1`:

```bash
LINDEX fruits 1
```

Output:

```text
"banana"
```

---

# 📌 Understanding Indexes

| Index | Value |
|---|---|
| `0` | `"apple"` |
| `1` | `"banana"` |
| `2` | `"mango"` |
| `3` | `"orange"` |

---

# 🔚 Using Negative Indexes

Negative indexes start counting from the end.

Example:

```bash
LINDEX fruits -1
```

Output:

```text
"orange"
```

---

# ❌ Invalid Index

```bash
LINDEX fruits 10
```

Output:

```text
(nil)
```

Because index `10` does not exist.

---

# ⚡ Important Points

- Index starts from `0`
- Negative indexes work from the end
- Returns a single item only

---

# 🌍 Common Use Cases

- 🎯 Access specific list item
- 📜 Read ordered data
- 📨 Fetch queue elements
- 💬 Read chat messages

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `LINDEX key index` | Get item by index from list |

`LINDEX` helps access specific elements from Redis lists 🚀
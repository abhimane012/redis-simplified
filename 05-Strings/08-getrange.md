# ✂️ GETRANGE in Redis

Redis provides the `GETRANGE` command to read a specific part of a string value.

It returns characters between a start and end position.

---

# 💻 Syntax

```bash
GETRANGE key start end
```

---

# 🧪 Example

Create a string:

```bash
SET message "Hello Redis"
```

Get characters from index `0` to `4`:

```bash
GETRANGE message 0 4
```

Output:

```text
"Hello"
```

---

# 📌 Index Positions

```text
H  e  l  l  o     R  e  d  i  s
0  1  2  3  4  5  6  7  8  9 10
```

Redis reads characters based on index positions.

---

# 🧪 Another Example

```bash
GETRANGE message 6 10
```

Output:

```text
"Redis"
```

---

# 🔚 Using Negative Indexes

Negative indexes start counting from the end.

Example:

```bash
GETRANGE message -5 -1
```

Output:

```text
"Redis"
```

---

# ⚡ Important Points

- Index starts from `0`
- End index is included
- Works only with string values

---

# ❌ Non-Existing Key

```bash
GETRANGE unknown 0 5
```

Output:

```text
""
```

Returns an empty string.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| ✂️ Extract text | Read part of a string |
| 📄 Preview content | Get first few characters |
| 📊 Parse stored data | Read specific sections |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `GETRANGE key start end` | Read part of a string |

`GETRANGE` helps extract specific characters from Redis string values 🚀
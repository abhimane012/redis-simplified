# ✏️ SETRANGE in Redis

Redis provides the `SETRANGE` command to replace part of a string starting from a specific position.

It updates only a portion of the string instead of replacing the entire value.

---

# 💻 Syntax

```bash
SETRANGE key offset value
```

---

# 🧪 Example

Create a string:

```bash
SET message "Hello World"
```

Replace text starting from index `6`:

```bash
SETRANGE message 6 "Redis"
```

---

# 📖 Check Updated Value

```bash
GET message
```

Output:

```text
"Hello Redis"
```

---

# 📌 Understanding Offset

```text
H  e  l  l  o     W  o  r  l  d
0  1  2  3  4  5  6  7  8  9 10
```

Redis starts replacing characters from the given offset.

---

# ⚡ If Key Does Not Exist

Redis creates the key automatically.

Example:

```bash
SETRANGE language 0 "Redis"
```

Now:

```bash
GET language
```

Output:

```text
"Redis"
```

---

# 🧪 Example with Empty Spaces

```bash
SETRANGE text 6 "Redis"
```

Output becomes:

```text
"\x00\x00\x00\x00\x00\x00Redis"
```

Redis fills missing spaces with empty bytes.

---

# 🔢 Return Value

`SETRANGE` returns the length of the updated string.

Example:

```text
(integer) 11
```

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| ✏️ Partial updates | Modify part of text |
| 📄 Edit stored content | Replace specific section |
| ⚡ Efficient updates | Avoid replacing whole string |

---

# ⚠️ Important Point

`SETRANGE` works only with string values.

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SETRANGE key offset value` | Replace part of a string |

`SETRANGE` helps update specific portions of Redis strings efficiently 🚀
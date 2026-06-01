# ➕ APPEND in Redis

Redis provides the `APPEND` command to add text at the end of an existing string value.

It is useful when you want to extend or update a string without replacing it completely.

---

# 💻 Syntax

```bash
APPEND key value
```

---

# 🧪 Example

Create a key:

```bash
SET message "Hello"
```

Append new text:

```bash
APPEND message " World"
```

---

# 📖 Check the Value

```bash
GET message
```

Output:

```text
"Hello World"
```

The new text is added to the existing string.

---

# ⚡ If Key Does Not Exist

If the key does not exist, Redis creates it automatically.

Example:

```bash
APPEND language "Redis"
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

# 🔢 Return Value of APPEND

`APPEND` returns the length of the updated string.

Example:

```bash
APPEND message "!"
```

Output:

```text
(integer) 12
```

Meaning:

- Updated string length is 12 characters

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 📝 Logs | Add log messages |
| 💬 Chat | Append chat text |
| 📄 Text Updates | Extend existing content |
| 📊 Tracking | Add activity information |

---

# ⚠️ Important Point

`APPEND` works only with string values.

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `APPEND key value` | Add text to existing string |

`APPEND` helps update string values without replacing the entire content 🚀
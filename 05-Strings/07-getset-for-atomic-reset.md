# 🔄 GETSET in Redis

Redis provides the `GETSET` command to:

1. 📖 Get the current value of a key
2. ✏️ Replace it with a new value

Both operations happen in a single command.

---

# 💻 Syntax

```bash
GETSET key new_value
```

---

# 🧪 Example

Create a key:

```bash
SET counter 10
```

Now run:

```bash
GETSET counter 20
```

Output:

```text
"10"
```

What happened?

- Old value `"10"` is returned
- New value becomes `"20"`

---

# 📖 Check Updated Value

```bash
GET counter
```

Output:

```text
"20"
```

---

# ⚡ If Key Does Not Exist

If the key does not exist:

```bash
GETSET username "abhishek"
```

Output:

```text
(nil)
```

Redis creates the key automatically.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🔢 Reset counters | Get old count and update |
| 📊 Track previous values | Replace old data |
| ⚙️ Atomic updates | Read and write together |

---

# ⚠️ Important Point

`GETSET` works only with string values.

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `GETSET key value` | Return old value and set new value |

`GETSET` is useful when you need the old value before updating it 🚀
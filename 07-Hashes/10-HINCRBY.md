# 🔢 HINCRBY and HINCRBYFLOAT in Redis

Redis provides `HINCRBY` and `HINCRBYFLOAT` to increase numeric values inside a hash field.

These are commonly used for counters and numeric updates.

---

# ⬆️ HINCRBY (Integer Increment)

`HINCRBY` increases a hash field by an integer value.

---

# 💻 Syntax

```bash
HINCRBY key field increment
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 points 10
```

Increase points:

```bash
HINCRBY user:1 points 5
```

---

# 📖 Result

```text
15
```

Updated hash:

```text
user:1
└── points → 15
```

---

# ⬆️ HINCRBYFLOAT (Decimal Increment)

`HINCRBYFLOAT` increases a hash field by a floating point (decimal) value.

---

# 💻 Syntax

```bash
HINCRBYFLOAT key field increment
```

---

# 🧪 Example

```bash
HSET user:1 balance 100.5
```

Increase balance:

```bash
HINCRBYFLOAT user:1 balance 25.75
```

---

# 📖 Result

```text
126.25
```

---

# ⚡ Important Points

- Field must be numeric
- Works only inside hashes
- Operation is atomic (safe in concurrent usage)

---

# ❌ Invalid Example

```bash
HSET user:1 name "Abhishek"
HINCRBY user:1 name 5
```

Output:

```text
(error) ERR hash value is not an integer
```

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🎮 Game scores | Increase points |
| 💰 Wallet balance | Update money |
| 📊 Analytics | Count events |
| 🛒 Inventory | Update stock |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HINCRBY` | Increase integer field value |
| `HINCRBYFLOAT` | Increase decimal field value |

These commands are useful for safe and fast numeric updates inside Redis hashes 🚀
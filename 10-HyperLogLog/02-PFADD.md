# ➕ PFADD in Redis

Redis provides the `PFADD` command to add elements to a HyperLogLog.

HyperLogLog uses these elements to estimate the number of unique values.

---

# 💻 Syntax

```bash
PFADD key element1 element2 element3
```

---

# 🧪 Example

Add website visitors:

```bash
PFADD visitors user1 user2 user3
```

Output:

```text
(integer) 1
```

---

# ➕ Add More Elements

```bash
PFADD visitors user3 user4 user5
```

Output:

```text
(integer) 1
```

Even though `user3` already exists, Redis processes the new unique values.

---

# 📌 What PFADD Does

```text
user1
user2
user3
user4
user5
```

Redis does not store these values directly like a Set.

Instead, it updates the internal HyperLogLog structure.

---

# 🔢 Return Values

| Output | Meaning |
|---|---|
| `(integer) 1` | HyperLogLog was modified |
| `(integer) 0` | No significant change |

---

# ⚡ Important Points

- Adds one or more elements
- Works only with HyperLogLog
- Used for approximate unique counting
- Memory usage remains very small

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 Unique visitors | Website analytics |
| 📱 Daily active users | Mobile apps |
| 📧 Email tracking | Unique opens |
| 📊 Event analytics | Unique events |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `PFADD key elements...` | Add elements to HyperLogLog |

`PFADD` is the first step in tracking approximate unique counts with Redis HyperLogLog 🚀
# 📊 PFCOUNT in Redis

Redis provides the `PFCOUNT` command to get the **estimated number of unique elements** stored in a HyperLogLog.

---

# 💻 Syntax

```bash
PFCOUNT key
```

---

# 🧪 Example

Add visitors:

```bash
PFADD visitors user1 user2 user3 user4 user5
```

Get unique count:

```bash
PFCOUNT visitors
```

Output:

```text
(integer) 5
```

---

# ➕ Duplicate Values

```bash
PFADD visitors user1 user2 user3
```

Check count again:

```bash
PFCOUNT visitors
```

Output:

```text
(integer) 5
```

Duplicates do not increase the unique count.

---

# 📌 Multiple HyperLogLogs

`PFCOUNT` can also count unique elements across multiple HyperLogLogs.

```bash
PFCOUNT visitors_day1 visitors_day2
```

Redis returns the estimated union count.

---

# ⚡ Important Points

- Returns an **approximate** unique count
- Works only with HyperLogLog
- Duplicates are ignored
- Very memory efficient

---

# ❌ Non-Existing Key

```bash
PFCOUNT unknown_key
```

Output:

```text
(integer) 0
```

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 Website analytics | Unique visitors |
| 📱 Mobile apps | Daily active users |
| 📧 Email campaigns | Unique opens |
| 📊 Event tracking | Unique events |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `PFCOUNT key` | Get estimated unique count |
| `PFCOUNT key1 key2 ...` | Get estimated union count |

`PFCOUNT` is used to read unique-count estimates from Redis HyperLogLog 🚀
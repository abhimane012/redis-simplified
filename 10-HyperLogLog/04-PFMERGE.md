# 🔗 PFMERGE in Redis

Redis provides the `PFMERGE` command to merge multiple HyperLogLogs into a single HyperLogLog.

This is useful when unique counts are stored separately and need to be combined.

---

# 💻 Syntax

```bash
PFMERGE destination source1 source2 source3
```

---

# 🧪 Example

Create two HyperLogLogs:

```bash
PFADD visitors_day1 user1 user2 user3
PFADD visitors_day2 user3 user4 user5
```

---

# 🔗 Merge Them

```bash
PFMERGE all_visitors visitors_day1 visitors_day2
```

Output:

```text
OK
```

---

# 📖 Check Unique Count

```bash
PFCOUNT all_visitors
```

Output:

```text
(integer) 5
```

Unique users are:

```text
user1
user2
user3
user4
user5
```

Notice that `user3` is counted only once.

---

# 📌 Important Behavior

- Creates the destination HyperLogLog if it does not exist
- Overwrites the destination if it already exists
- Source HyperLogLogs remain unchanged

---

# ⚡ Why Use PFMERGE?

Suppose you track visitors separately:

```text
visitors_day1
visitors_day2
visitors_day3
```

You can merge them into:

```text
all_visitors
```

and get an estimated unique visitor count across all days.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👥 Website analytics | Merge daily visitors |
| 📱 Mobile apps | Merge active users |
| 📧 Marketing | Merge campaign data |
| 📊 Analytics | Combine unique event counts |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `PFMERGE dest source1 source2 ...` | Merge HyperLogLogs |

`PFMERGE` helps combine multiple HyperLogLogs while preserving approximate unique counts 🚀
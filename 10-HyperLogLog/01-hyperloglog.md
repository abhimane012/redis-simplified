# 📊 Redis HyperLogLog

Redis HyperLogLog is a special data structure used to count **unique values approximately**.

It is designed to answer questions like:

> 👥 "How many unique users visited my website today?"

without storing every user ID.

---

# 🧠 Why Use HyperLogLog?

Imagine:

```text
100 million website visitors
```

Storing every visitor ID in a Set would consume a lot of memory.

HyperLogLog can estimate the number of unique visitors using only about:

```text
~12 KB
```

no matter how many elements are added.

---

# ⚡ Features

- 💾 Very memory efficient
- 🚀 Fast operations
- 👥 Counts unique elements
- 📊 Provides approximate results
- 📏 Standard error is around 0.81%

---

# 🎯 Example

Instead of storing:

```text
user1
user2
user3
...
user100000000
```

Redis stores a compact representation and estimates:

```text
99,800,000 unique users
```

which is usually accurate enough for analytics.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 📈 Website analytics | Unique visitors |
| 📱 Mobile apps | Daily active users |
| 📧 Email campaigns | Unique opens |
| 📰 Content platforms | Unique readers |
| 📊 Big data analytics | Unique event tracking |

---

# 🛠️ Common HyperLogLog Commands

| Command | Purpose |
|---|---|
| `PFADD` | Add elements |
| `PFCOUNT` | Get estimated unique count |
| `PFMERGE` | Merge HyperLogLogs |

---

# ⚠️ Important Limitation

HyperLogLog gives:

```text
Approximate Count ✅
```

Not:

```text
Exact Count ❌
```

If you need exact uniqueness, use a Redis Set instead.

---

# 📝 Summary

- 📊 HyperLogLog estimates unique counts
- 💾 Uses very little memory (~12 KB)
- 🚀 Ideal for large-scale analytics
- ⚠️ Results are approximate, not exact

HyperLogLog is perfect when memory matters more than absolute accuracy 🚀
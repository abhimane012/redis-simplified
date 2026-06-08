# 📊 Redis Sorted Sets (ZSET)

Redis Sorted Sets are like normal Sets, but with a **score attached to each value**.

This score is used to **sort the elements automatically**.

---

# 🧠 Think of a Sorted Set Like

A leaderboard 🎮

```text
Alice → 100
Bob   → 80
Sam   → 95
```

Redis automatically keeps them sorted by score.

---

# ⚡ Features of Sorted Sets

- 🔢 Each value has a score
- 📈 Automatically sorted by score
- 🔒 Values are unique (like Sets)
- 🚀 Fast range queries

---

# 🌍 Common Use Cases

- 🎮 Game leaderboards
- 🏆 Ranking systems
- 📊 Top scores / analytics
- 📰 Trending content
- ⏱️ Priority queues

---

# 🛠️ Common Redis Sorted Set Commands

| Command | Purpose |
|---|---|
| `ZADD` | Add elements with score |
| `ZRANGE` | Get elements in ascending order |
| `ZREVRANGE` | Get elements in descending order |
| `ZRANK` | Get rank (ascending) |
| `ZREVRANK` | Get rank (descending) |
| `ZSCORE` | Get score of a member |
| `ZINCRBY` | Increase score |
| `ZREM` | Remove member |
| `ZCARD` | Count elements |
| `ZRANGEBYSCORE` | Get elements by score range |
| `ZCOUNT` | Count elements in score range |

---

# 📌 Key Idea

Sorted Sets =

```text
Unique values + Score + Auto sorting
```

---

# 📝 Summary

- 📊 Stores unique values with scores
- 🔢 Automatically sorted
- 🚀 Ideal for ranking and leaderboard systems

Redis Sorted Sets are powerful for any ranking-based system 🚀
# 📊 ZREVRANGE in Redis

Redis provides the `ZREVRANGE` command to retrieve elements from a Sorted Set in **descending order (high → low score)**.

It is commonly used for leaderboards where the highest score should appear first.

---

# 💻 Syntax

```bash
ZREVRANGE key start stop
```

---

# 🧪 Example

Create a sorted set:

```bash
ZADD leaderboard 100 Alice 80 Bob 95 Sam 120 John
```

---

# 📖 Get All Members (Highest Score First)

```bash
ZREVRANGE leaderboard 0 -1
```

Output:

```text
1) "John"
2) "Alice"
3) "Sam"
4) "Bob"
```

---

# 📌 With Scores

```bash
ZREVRANGE leaderboard 0 -1 WITHSCORES
```

Output:

```text
1) "John"
2) "120"
3) "Alice"
4) "100"
5) "Sam"
6) "95"
7) "Bob"
8) "80"
```

---

# 🎯 Get Top 3 Players

```bash
ZREVRANGE leaderboard 0 2 WITHSCORES
```

Output:

```text
1) "John"
2) "120"
3) "Alice"
4) "100"
5) "Sam"
6) "95"
```

---

# 📌 Understanding Indexes

| Index | Meaning |
|---|---|
| `0` | First element |
| `1` | Second element |
| `-1` | Last element |

---

# ⚡ Important Points

- Returns members from highest score to lowest score
- Works only with Sorted Sets
- Useful for ranking and leaderboard systems

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🏆 Leaderboards | Top players |
| 📊 Rankings | Highest scores first |
| 📰 Trending content | Most popular items |
| 🎮 Gaming | Top performers |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `ZREVRANGE key start stop` | Get members in descending order |
| `WITHSCORES` | Include scores in output |

`ZREVRANGE` is one of the most commonly used commands for Redis leaderboard systems 🚀
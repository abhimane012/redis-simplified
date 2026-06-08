# 📊 ZRANGE in Redis (Sorted Sets)

Redis `ZRANGE` is used to fetch elements from a **Sorted Set in ascending order (low → high score)**.

It is one of the most important commands for reading leaderboards.

---

# 💻 Basic Syntax

```bash
ZRANGE key start stop
```

---

# 🧪 Example

Create a sorted set:

```bash
ZADD leaderboard 100 Alice 80 Bob 95 Sam 120 John
```

---

# 📖 Basic Range Query

```bash
ZRANGE leaderboard 0 -1
```

Output:

```text
1) "Bob"
2) "Sam"
3) "Alice"
4) "John"
```

---

# 📌 With Scores (WITHSCORES)

```bash
ZRANGE leaderboard 0 -1 WITHSCORES
```

Output:

```text
1) "Bob"
2) "80"
3) "Sam"
4) "95"
5) "Alice"
6) "100"
7) "John"
8) "120"
```

---

# 🎯 REV (Reverse Order - Highest First)

```bash
ZRANGE leaderboard 0 -1 REV WITHSCORES
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

👉 This is commonly used for leaderboards.

---

# ✂️ LIMIT (Offset + Count)

Used to paginate results.

```bash
ZRANGE leaderboard 0 -1 LIMIT 1 2
```

Meaning:

- Skip 1 element
- Return next 2 elements

Output:

```text
1) "Sam"
2) "Alice"
```

---

# 📊 BYSCORE (Filter by Score Range)

```bash
ZRANGE leaderboard 80 100 BYSCORE
```

Output:

```text
1) "Bob"
2) "Sam"
3) "Alice"
```

---

# 📏 BYSCORE with LIMIT

```bash
ZRANGE leaderboard 80 120 BYSCORE LIMIT 0 2
```

---

# 🔤 BYLEX (Lexicographical Range)

Used when all scores are same (sorted by value).

```bash
ZRANGE leaderboard - + BYLEX
```

---

# ⚡ Important Options Summary

| Option | Purpose |
|---|---|
| `WITHSCORES` | Return scores along with values |
| `REV` | Reverse order (high → low) |
| `LIMIT` | Pagination (offset, count) |
| `BYSCORE` | Filter by score range |
| `BYLEX` | Lexicographical range |

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🏆 Leaderboards | Top players |
| 📊 Rankings | Scores sorting |
| 📰 Trending list | Popular posts |
| ⚡ Pagination | Load data in chunks |
| 🎯 Score filtering | Range-based queries |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `ZRANGE key start stop` | Get elements in ascending order |
| `WITHSCORES` | Include scores |
| `REV` | Reverse order |
| `LIMIT` | Paginate results |
| `BYSCORE` | Filter by score |

`ZRANGE` is the main command for reading Redis Sorted Sets 🚀
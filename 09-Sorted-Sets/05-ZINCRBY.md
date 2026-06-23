# ⬆️ ZINCRBY in Redis

Redis provides the `ZINCRBY` command to increase (or decrease) the score of a member in a Sorted Set.

If the member does not exist, Redis creates it automatically.

---

# 💻 Syntax

```bash
ZINCRBY key increment member
```

---

# 🧪 Example

Create a leaderboard:

```bash
ZADD leaderboard 100 Alice 80 Bob
```

Increase Alice's score:

```bash
ZINCRBY leaderboard 20 Alice
```

Output:

```text
"120"
```

Updated leaderboard:

```text
Alice → 120
Bob   → 80
```

---

# 📉 Decrease Score

Use a negative increment:

```bash
ZINCRBY leaderboard -10 Alice
```

Output:

```text
"110"
```

---

# 🆕 Member Does Not Exist

```bash
ZINCRBY leaderboard 50 Sam
```

Output:

```text
"50"
```

Redis automatically creates:

```text
Sam → 50
```

---

# 📖 Check Updated Scores

```bash
ZRANGE leaderboard 0 -1 WITHSCORES
```

Output:

```text
1) "Sam"
2) "50"
3) "Bob"
4) "80"
5) "Alice"
6) "110"
```

---

# ⚡ Important Points

- Can increase or decrease scores
- Creates member automatically if missing
- Works only with Sorted Sets
- Returns the updated score

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🏆 Leaderboards | Update player scores |
| 🎮 Games | Award points |
| 👍 Ranking systems | Adjust rankings |
| 📊 Analytics | Track popularity |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `ZINCRBY key increment member` | Increase or decrease a member's score |

`ZINCRBY` is the most common way to update scores in Redis Sorted Sets 🚀
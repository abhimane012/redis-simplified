# ➕ ZADD in Redis (Sorted Sets)

Redis `ZADD` is used to add elements into a **Sorted Set**, where each element has a **score**.

The score decides the **sorting order**.

---

# 💻 Basic Syntax

```bash
ZADD key score member
```

---

# 🧪 Example

```bash
ZADD leaderboard 100 Alice 80 Bob 95 Sam
```

Sorted Set becomes:

```text
Bob   → 80
Sam   → 95
Alice → 100
```

---

# ⚡ ZADD Options (All Important Flags)

Redis `ZADD` supports several options to control behavior.

---

# 🆕 NX (Only Add New Elements)

```bash
ZADD leaderboard NX 110 John
```

- Adds only if member does NOT exist
- ❌ Won’t update existing members

---

# 🔁 XX (Only Update Existing Elements)

```bash
ZADD leaderboard XX 120 Alice
```

- Updates only if member already exists
- ❌ Won’t add new members

---

# 📈 CH (Return Number of Changed Elements)

```bash
ZADD leaderboard CH 130 Bob Sam
```

- Returns how many elements were:
  - added OR updated

---

# ⬆️ INCR (Increment Score)

```bash
ZADD leaderboard INCR 10 Alice
```

- Increases score of a single member
- Equivalent to `ZINCRBY`

Result:

```text
Alice score increases by 10
```

---

# ⚠️ GT (Greater Than Only Update)

```bash
ZADD leaderboard GT 150 Bob
```

- Updates only if new score is **greater than existing score**

---

# ⚠️ LT (Less Than Only Update)

```bash
ZADD leaderboard LT 70 Bob
```

- Updates only if new score is **less than existing score**

---

# 📦 Combine Options

You can combine flags:

```bash
ZADD leaderboard NX CH 200 David
```

Meaning:

- Add only if new
- Return change count

---

# ❌ Invalid Combinations

- `NX` + `XX` ❌ (conflict)
- `GT` + `LT` ❌ (conflict)

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🏆 Leaderboards | Game rankings |
| 📊 Scoring systems | Points tracking |
| 📰 Trending content | Rank posts |
| ⚡ Priority queues | Task scheduling |
| 🎯 Real-time ranking | Live score updates |

---

# 📝 Summary

| Option | Meaning |
|---|---|
| `NX` | Add only new members |
| `XX` | Update only existing members |
| `CH` | Return changed count |
| `INCR` | Increase score |
| `GT` | Update only if score is greater |
| `LT` | Update only if score is smaller |

`ZADD` is the core command for building Redis leaderboard systems 🚀
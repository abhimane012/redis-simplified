# 🔢 Counting Numbers in Redis

Redis provides special commands for increasing and decreasing numeric values.

These commands are commonly used for:

- 👀 Page views
- 👍 Likes
- 📊 Counters
- 🚦 Rate limiting
- 📈 Analytics

---

# ⬆️ INCR

`INCR` increases a number by `1`.

---

## 💻 Syntax

```bash
INCR key
```

---

## 🧪 Example

```bash
SET visitors 10
```

Increase value:

```bash
INCR visitors
```

Now value becomes:

```text
11
```

Check value:

```bash
GET visitors
```

Output:

```text
"11"
```

---

# ⬇️ DECR

`DECR` decreases a number by `1`.

---

## 💻 Syntax

```bash
DECR key
```

---

## 🧪 Example

```bash
SET stock 20
```

Decrease value:

```bash
DECR stock
```

Now value becomes:

```text
19
```

---

# ⬆️➕ INCRBY

`INCRBY` increases a number by a specific value.

---

## 💻 Syntax

```bash
INCRBY key number
```

---

## 🧪 Example

```bash
SET points 100
```

Increase by 50:

```bash
INCRBY points 50
```

Now value becomes:

```text
150
```

---

# ⬇️➖ DECRBY

`DECRBY` decreases a number by a specific value.

---

## 💻 Syntax

```bash
DECRBY key number
```

---

## 🧪 Example

```bash
SET balance 500
```

Decrease by 100:

```bash
DECRBY balance 100
```

Now value becomes:

```text
400
```

---

# ⚡ Important Points

- These commands work only with numeric values
- Redis automatically converts valid numbers
- Operations are very fast and atomic

---

# ❌ Invalid Example

```bash
SET username "abhishek"
INCR username
```

Output:

```text
(error) value is not an integer
```

Because `"abhishek"` is not a number.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 👀 Page Views | Count website visitors |
| 👍 Likes | Increase likes count |
| 🛒 Stock | Reduce inventory |
| 🚦 Rate Limiting | Track API requests |
| 🎮 Game Scores | Update player points |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `INCR key` | Increase by 1 |
| `DECR key` | Decrease by 1 |
| `INCRBY key number` | Increase by custom value |
| `DECRBY key number` | Decrease by custom value |

Redis counter commands are simple, fast, and widely used 🚀
# 🎲 HRANDFIELD in Redis

Redis provides the `HRANDFIELD` command to get random fields from a hash.

It is useful when you want to pick one or more random entries from stored data.

---

# 💻 Syntax

```bash
HRANDFIELD key
```

---

# 🧪 Example

Create a hash:

```bash
HSET user:1 name "Abhishek" age 25 city "Bangalore" role "developer"
```

Get a random field:

```bash
HRANDFIELD user:1
```

Output (example):

```text
"city"
```

Next run:

```text
"age"
```

---

# 🎯 Get Random Field with Value

To get both field and value:

```bash
HRANDFIELD user:1 1 WITHVALUES
```

Output:

```text
1) "name"
2) "Abhishek"
```

---

# 🔢 Get Multiple Random Fields

```bash
HRANDFIELD user:1 2
```

Output (example):

```text
1) "city"
2) "role"
```

---

# ⚡ Important Points

- Returns random field(s)
- Does not remove fields
- Works only with hashes
- Useful for sampling data

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🎲 Random selection | Pick random user attributes |
| 🧪 Testing | Sample hash data |
| 🎮 Games | Random properties |
| 📊 Analytics | Random field inspection |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `HRANDFIELD key` | Get a random field |
| `HRANDFIELD key count` | Get multiple random fields |
| `HRANDFIELD key count WITHVALUES` | Get fields with values |

`HRANDFIELD` helps in random sampling from Redis hashes 🚀
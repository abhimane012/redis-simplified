# 🔍 SCAN in Redis

Redis provides the `SCAN` command to iterate through keys gradually.

It is used to safely search keys without blocking the Redis server.

`SCAN` is recommended instead of `KEYS` for large databases.

---

# ⚡ Why Not Use KEYS?

The `KEYS` command scans all keys at once.

In large databases, this can:

- 🐢 Slow down Redis
- ⚠️ Block the server temporarily

---

# ✅ Why SCAN is Better

`SCAN` works in small batches.

This makes it:

- ⚡ Safer
- 🚀 More efficient
- 🛡️ Non-blocking

---

# 💻 Basic Syntax

```bash
SCAN cursor
```

---

# 🧪 Example

```bash
SCAN 0
```

Example output:

```text
1) "5"
2) 1) "user:1"
   2) "user:2"
```

---

# 📌 Understanding the Output

`SCAN` returns:

1. 🔢 Next cursor
2. 📦 List of keys

Example:

```text
1) "5"
```

Means:

- Continue scanning using cursor `5`

---

# 🔄 Continue Scanning

```bash
SCAN 5
```

Keep repeating until cursor becomes:

```text
0
```

This means scanning is complete ✅

---

# 🎯 Match Specific Patterns

Use `MATCH` to filter keys.

---

## 🧪 Example

```bash
SCAN 0 MATCH user:*
```

Returns only keys starting with:

```text
user:
```

---

# 🔢 Limit Number of Results

Use `COUNT` to suggest how many keys Redis should return.

---

## 🧪 Example

```bash
SCAN 0 COUNT 10
```

---

# 🧪 Combine MATCH and COUNT

```bash
SCAN 0 MATCH user:* COUNT 5
```

---

# ⚠️ Important Points

- `SCAN` may return duplicate keys
- Result count is not guaranteed exactly
- Designed for incremental iteration

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🔍 Search keys | Find matching keys |
| 🧹 Cleanup jobs | Process keys gradually |
| 📊 Data migration | Iterate large datasets |
| ⚙️ Background tasks | Non-blocking scans |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SCAN 0` | Start scanning keys |
| `MATCH pattern` | Filter matching keys |
| `COUNT number` | Suggest batch size |

`SCAN` is the recommended way to iterate Redis keys safely in production 🚀
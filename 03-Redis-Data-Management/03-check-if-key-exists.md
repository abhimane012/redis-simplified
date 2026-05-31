# 🔍 Check if a Key Exists in Redis

Redis provides the `EXISTS` command to check whether a key is present or not.

---

# 🧪 Syntax

```bash
EXISTS key_name
```

---

# 💻 Example

Store a key:

```bash
SET username "abhishek"
```

Check if the key exists:

```bash
EXISTS username
```

Output:

```text
(integer) 1
```

---

# ✅ Understanding the Output

| Output | Meaning |
|---|---|
| `(integer) 1` | Key exists |
| `(integer) 0` | Key does not exist |

---

# ❌ Example with Missing Key

```bash
EXISTS country
```

Output:

```text
(integer) 0
```

This means the key does not exist in Redis.

---

# 🔢 Check Multiple Keys

You can also check multiple keys together.

Example:

```bash
EXISTS username age country
```

Output:

```text
(integer) 2
```

Meaning:

- 2 keys exist
- 1 key does not exist

---

# ⚡ Why Use EXISTS?

The `EXISTS` command is useful for:

- ✅ Checking data before reading
- 🛡️ Avoiding errors
- 🔍 Validating cache data
- ⚙️ Conditional operations

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `EXISTS key` | Check if key exists |
| `1` | Key exists |
| `0` | Key does not exist |

`EXISTS` is a simple and useful command for checking keys in Redis 🚀
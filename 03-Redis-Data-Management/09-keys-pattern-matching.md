# 🔍 Redis Key Pattern Matching

Redis allows searching keys using patterns.

This is useful when you want to find keys that follow a naming structure.

Pattern matching is commonly used with the `KEYS` command.

---

# 💻 Syntax

```bash
KEYS pattern
```

---

# 🧪 Example Data

```bash
SET user:1 "Abhishek"
SET user:2 "Rahul"
SET product:1 "Laptop"
SET product:2 "Phone"
```

---

# ⭐ Match All Keys

Use:

```bash
KEYS *
```

Output:

```text
1) "user:1"
2) "user:2"
3) "product:1"
4) "product:2"
```

`*` means:

> Match everything

---

# 👤 Match User Keys

```bash
KEYS user:*
```

Output:

```text
1) "user:1"
2) "user:2"
```

Meaning:

- Find all keys starting with `user:`

---

# 📦 Match Product Keys

```bash
KEYS product:*
```

Output:

```text
1) "product:1"
2) "product:2"
```

---

# 🔢 Match Specific Patterns

## Match Single Character

```bash
KEYS user:?
```

Example match:

```text
user:1
user:2
```

`?` means:

> Match exactly one character

---

# 🔠 Match Character Range

```bash
KEYS user:[1-5]
```

Matches:

```text
user:1
user:2
user:3
```

---

# ⚠️ Important Warning About KEYS

`KEYS` scans all keys in Redis.

In large production systems, this can slow down Redis.

So:

- ✅ Good for learning and debugging
- ❌ Not recommended for very large databases

---

# 🚀 Better Alternative: SCAN

For large datasets, Redis recommends:

```bash
SCAN 0
```

`SCAN` is safer and more efficient for production use.

---

# 📝 Summary

| Pattern | Meaning |
|---|---|
| `*` | Match everything |
| `user:*` | Keys starting with `user:` |
| `?` | Match one character |
| `[1-5]` | Match range of characters |

Pattern matching helps search and organize Redis keys easily 🚀
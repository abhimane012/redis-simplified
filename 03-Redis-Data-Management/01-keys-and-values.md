# 🔑 Redis Keys and Values

Redis stores data using a **key-value** structure.

Think of it like a dictionary:

```text
key -> value
```

---

# 🗂️ What is a Key?

A **key** is the name used to identify data.

Example:

```text
username
```

Here, `username` is the key.

Keys should be unique.

---

# 📦 What is a Value?

A **value** is the actual data stored inside the key.

Example:

```text
"abhishek"
```

Here, `"abhishek"` is the value.

---

# 🧪 Example

```text
username -> "abhishek"
age      -> 25
country  -> "India"
```

- `username`, `age`, and `country` are keys
- `"abhishek"`, `25`, and `"India"` are values

---

# 💻 Storing Key-Value Data

Store data:

```bash
SET username "abhishek"
```

Here:

- `username` → key
- `"abhishek"` → value

---

# 📖 Reading Value from a Key

Get data:

```bash
GET username
```

Output:

```text
"abhishek"
```

Redis finds the key and returns its value.

---

# ❌ Replacing Existing Value

If the same key already exists, Redis replaces the old value.

Example:

```bash
SET username "redis_user"
```

Now:

```text
username -> "redis_user"
```

The old value is overwritten.

---

# ⚡ Why Key-Value Storage is Fast

Redis can quickly find data using keys.

This makes operations very fast and efficient.

---

# 📌 Key Naming Examples

Good key names:

```text
user:1
user:name
product:100
session:token
```

Using meaningful names makes data easier to manage.

---

# 📝 Summary

| Term | Meaning |
|---|---|
| 🔑 Key | Name used to identify data |
| 📦 Value | Actual stored data |
| ⚡ Redis | Stores data as key-value pairs |

Redis mainly works by storing and retrieving values using keys 🚀
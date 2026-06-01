# 🔍 Find Data Type of a Key in Redis

Redis stores different types of data like:

- 🔤 Strings
- 📋 Lists
- 🎯 Sets
- 🗃️ Hashes
- 📊 Sorted Sets

You can check the type of a key using the `TYPE` command.

---

# 💻 Syntax

```bash
TYPE key_name
```

---

# 🧪 Example with String

Create a string key:

```bash
SET username "abhishek"
```

Check type:

```bash
TYPE username
```

Output:

```text
string
```

---

# 🧪 Example with List

Create a list:

```bash
LPUSH numbers 1 2 3
```

Check type:

```bash
TYPE numbers
```

Output:

```text
list
```

---

# 🧪 Example with Set

Create a set:

```bash
SADD tags redis database cache
```

Check type:

```bash
TYPE tags
```

Output:

```text
set
```

---

# ❌ Non-Existing Key

```bash
TYPE unknown_key
```

Output:

```text
none
```

Meaning:

- Key does not exist

---

# 📋 Common Redis Data Types

| Output | Meaning |
|---|---|
| `string` | String value |
| `list` | List |
| `set` | Set |
| `hash` | Hash |
| `zset` | Sorted Set |
| `stream` | Stream |
| `none` | Key does not exist |

---

# ⚡ Why TYPE is Useful

The `TYPE` command helps:

- 🔍 Understand stored data
- 🛠️ Debug Redis keys
- ✅ Use correct Redis commands

Example:

- Use `GET` for strings
- Use `LRANGE` for lists
- Use `SMEMBERS` for sets

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `TYPE key` | Find data type of a key |

`TYPE` helps identify what kind of data is stored inside a Redis key 🚀
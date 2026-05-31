# 🗂️ Redis Keyspaces

Redis supports multiple logical databases inside a single Redis server.

These databases are called **keyspaces**.

Each keyspace stores its own keys and values separately.

---

# 📦 Default Keyspaces

By default, Redis provides:

```text
16 keyspaces
```

Numbered from:

```text
0 to 15
```

---

# 📌 Default Database

When you connect to Redis, you are automatically connected to:

```text
Database 0
```

---

# 🔄 Switch Between Keyspaces

Use the `SELECT` command to switch databases.

---

# 💻 Syntax

```bash
SELECT database_number
```

---

# 🧪 Example

Switch to database 1:

```bash
SELECT 1
```

Output:

```text
OK
```

Now all operations happen inside database `1`.

---

# 📦 Separate Data in Each Keyspace

Example:

In database 0:

```bash
SET name "redis-db0"
```

Switch to database 1:

```bash
SELECT 1
```

Now try:

```bash
GET name
```

Output:

```text
(nil)
```

Why?

Because database `1` has separate data.

---

# 🧹 Remove All Keys from Current Database

Use:

```bash
FLUSHDB
```

This deletes **all keys only from the currently selected database**.

---

# 🧪 Example

```bash
SELECT 1
FLUSHDB
```

All keys inside database `1` are removed.

Other databases remain untouched ✅

---

# ⚠️ Important Difference

| Command | Effect |
|---|---|
| `FLUSHDB` | Clears current database only |
| `FLUSHALL` | Clears all databases |

---

# 📊 Check Current Database

Redis CLI prompt usually shows current database:

```text
127.0.0.1:6379[1]>
```

Here:

```text
[1]
```

means database `1` is selected.

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SELECT 1` | Switch to database 1 |
| `SELECT 0` | Switch back to database 0 |
| `FLUSHDB` | Delete all keys from current database |

Redis keyspaces help organize data into separate logical databases 🚀
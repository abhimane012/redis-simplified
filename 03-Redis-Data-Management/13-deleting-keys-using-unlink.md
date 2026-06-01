# ⚡ Deleting Keys Asynchronously Using UNLINK

Redis provides the `UNLINK` command to delete keys asynchronously.

Unlike `DEL`, `UNLINK` removes keys in the background without blocking Redis.

This is useful for deleting large keys safely and efficiently.

---

# 🧠 DEL vs UNLINK

| Command | Behavior |
|---|---|
| `DEL` | Deletes key immediately |
| `UNLINK` | Deletes key in background |

---

# 💻 Syntax

```bash
UNLINK key_name
```

---

# 🧪 Example

Create a key:

```bash
SET username "abhishek"
```

Delete it asynchronously:

```bash
UNLINK username
```

---

# 📖 Check the Key

```bash
GET username
```

Output:

```text
(nil)
```

The key is removed.

---

# ⚡ Why Use UNLINK?

Large keys can take time to delete.

Using `DEL` on huge data may temporarily block Redis.

`UNLINK` avoids this by:

- 🔄 Removing key in background
- ⚡ Keeping Redis responsive
- 🚀 Improving performance

---

# 🔢 Delete Multiple Keys

```bash
UNLINK key1 key2 key3
```

Redis deletes all keys asynchronously.

---

# ✅ Return Value

`UNLINK` returns the number of keys scheduled for deletion.

Example:

```bash
UNLINK username
```

Output:

```text
(integer) 1
```

---

# 📌 Important Point

After `UNLINK`:

- Key becomes inaccessible immediately
- Actual memory cleanup happens in background

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `UNLINK key` | Delete key asynchronously |
| `DEL key` | Delete key immediately |

`UNLINK` is recommended for deleting large keys without slowing down Redis 🚀
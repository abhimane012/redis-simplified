# ❌ Deleting Keys in Redis

Redis allows you to remove keys when they are no longer needed.

Deleting a key also removes its value.

---

# 🗑️ Delete a Key

Use the `DEL` command:

```bash
DEL username
```

This deletes the key:

```text
username
```

and its value.

---

# 🧪 Example

Store a key:

```bash
SET username "abhishek"
```

Delete the key:

```bash
DEL username
```

---

# 📖 Check if Key Exists

Try getting the deleted key:

```bash
GET username
```

Output:

```text
(nil)
```

This means the key no longer exists.

---

# 🔢 Delete Multiple Keys

You can delete multiple keys together.

Example:

```bash
DEL username age country
```

Redis deletes all specified keys.

---

# ✅ Return Value of DEL

`DEL` returns the number of keys deleted.

Example:

```bash
DEL username
```

Output:

```text
(integer) 1
```

Meaning:

- `1` key was deleted

If key does not exist:

```text
(integer) 0
```

---

# ⚡ Why Delete Keys?

Deleting unused keys helps:

- 💾 Free memory
- ⚡ Improve performance
- 🧹 Keep Redis clean

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `DEL key` | Delete a key |
| `DEL key1 key2` | Delete multiple keys |

Deleting a key removes both the key and its stored value from Redis 🚀
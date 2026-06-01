# ✏️ Rename a Key in Redis

Redis allows changing the name of an existing key using the `RENAME` command.

The value inside the key remains unchanged.

---

# 💻 Syntax

```bash
RENAME old_key new_key
```

---

# 🧪 Example

Create a key:

```bash
SET username "abhishek"
```

Rename the key:

```bash
RENAME username user_name
```

---

# 📖 Check the New Key

```bash
GET user_name
```

Output:

```text
"abhishek"
```

The value is preserved ✅

---

# ❌ Old Key No Longer Exists

```bash
GET username
```

Output:

```text
(nil)
```

Because the old key name was replaced.

---

# ⚠️ Important Note

If the new key already exists, Redis overwrites it.

Example:

```bash
RENAME key1 key2
```

If `key2` already exists:

- Old `key2` value is removed
- `key1` becomes `key2`

---

# 🛡️ Safe Rename Using RENAMENX

To rename only if the new key does not exist:

```bash
RENAMENX old_key new_key
```

Meaning:

> Rename if new key does not exist

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `RENAME old new` | Rename a key |
| `RENAMENX old new` | Rename only if new key does not exist |

Redis allows easy renaming of keys without changing their stored values 🚀
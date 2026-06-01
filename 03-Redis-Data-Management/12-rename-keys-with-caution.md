# ⚠️ Rename Keys with Caution in Redis

Redis provides the `RENAME` command to change key names.

But it should be used carefully because it can overwrite existing keys.

---

# ✏️ Using RENAME

```bash
RENAME old_key new_key
```

---

# 🧪 Example

```bash
SET user:1 "Abhishek"
SET user:2 "Rahul"
```

Now rename:

```bash
RENAME user:1 user:2
```

What happens?

- ❌ Old `user:2` value is deleted
- ✅ `user:1` becomes `user:2`

Result:

```bash
GET user:2
```

Output:

```text
"Abhishek"
```

The old value `"Rahul"` is lost.

---

# ⚠️ Why Be Careful?

`RENAME` always overwrites the destination key if it already exists.

This can accidentally delete important data.

---

# 🛡️ Safe Rename with RENAMENX

Redis provides a safer command:

```bash
RENAMENX old_key new_key
```

Meaning:

> Rename only if the new key does not already exist

---

# 🧪 Example

```bash
SET user:1 "Abhishek"
SET user:2 "Rahul"
```

Now run:

```bash
RENAMENX user:1 user:2
```

Output:

```text
(integer) 0
```

Meaning:

- Rename failed
- `user:2` already exists

No data is overwritten ✅

---

# ✅ Successful RENAMENX

```bash
RENAMENX user:1 user:3
```

Output:

```text
(integer) 1
```

Meaning:

- Rename successful

---

# 🔢 Return Values of RENAMENX

| Output | Meaning |
|---|---|
| `(integer) 1` | Rename successful |
| `(integer) 0` | Rename failed because new key exists |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `RENAME old new` | Rename key and overwrite if needed |
| `RENAMENX old new` | Rename only if new key does not exist |

Use `RENAMENX` when you want safer key renaming without accidental data loss 🚀
# ♻️ Remove Expiration from a Key in Redis

Redis allows removing the expiration time from a key using the `PERSIST` command.

After removing expiration, the key becomes permanent until manually deleted.

---

# 💻 Syntax

```bash
PERSIST key_name
```

---

# 🧪 Example

Create a key with expiration:

```bash
SETEX username 60 "abhishek"
```

Check remaining time:

```bash
TTL username
```

Example output:

```text
(integer) 55
```

Now remove expiration:

```bash
PERSIST username
```

---

# ✅ Check Expiration Again

```bash
TTL username
```

Output:

```text
(integer) -1
```

Meaning:

- Key exists
- No expiration is set

The key will no longer expire automatically.

---

# 🔢 Return Value of PERSIST

| Output | Meaning |
|---|---|
| `(integer) 1` | Expiration removed successfully |
| `(integer) 0` | Key does not exist or has no expiration |

---

# ⚡ Why Use PERSIST?

`PERSIST` is useful when:

- 🔐 Temporary data should become permanent
- 👤 Session should stay active
- ⚙️ Expiration was added by mistake

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `PERSIST key` | Remove expiration from key |
| `TTL key` | Check expiration time |

`PERSIST` converts an expiring key into a permanent key 🚀
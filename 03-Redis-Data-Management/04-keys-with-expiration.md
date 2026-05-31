# ⏳ Define Key with Expiration in Redis

Redis allows keys to expire automatically after a certain amount of time.

This is useful for:

- 🔐 OTPs
- 👤 User sessions
- ⚡ Cache data
- 🔑 Temporary tokens

After the expiration time ends, Redis automatically deletes the key.

---

# 💻 Set Key with Expiration

Use the `SETEX` command:

```bash
SETEX key_name seconds value
```

---

# 🧪 Example

```bash
SETEX otp 60 "1234"
```

Here:

- `otp` → key
- `60` → expiration time in seconds
- `"1234"` → value

The key will be deleted automatically after 60 seconds.

---

# 📖 Read the Key

Before expiration:

```bash
GET otp
```

Output:

```text
"1234"
```

After 60 seconds:

```bash
GET otp
```

Output:

```text
(nil)
```

The key no longer exists.

---

# ⌛ Check Remaining Expiration Time

Use:

```bash
TTL otp
```

Example output:

```text
(integer) 45
```

Meaning:

- 45 seconds remaining before key expires

---

# ⚡ Set Expiration on Existing Key

First create a key:

```bash
SET username "abhishek"
```

Add expiration:

```bash
EXPIRE username 30
```

This makes the key expire after 30 seconds.

---

# ⏱️ Millisecond Expiration with PEXPIRE

Redis also supports expiration in milliseconds.

Use:

```bash
PEXPIRE key milliseconds
```

---

## 🧪 Example

```bash
PEXPIRE username 5000
```

Here:

- `5000` = 5000 milliseconds
- Key expires after 5 seconds

---

# ⌛ Check Remaining Time in Milliseconds

Use:

```bash
PTTL username
```

Example output:

```text
(integer) 4200
```

Meaning:

- 4200 milliseconds remaining

---

# ❌ Special TTL/PTTL Values

| Value | Meaning |
|---|---|
| `-1` | Key exists but has no expiration |
| `-2` | Key does not exist |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SETEX key seconds value` | Create key with expiration |
| `EXPIRE key seconds` | Set expiration in seconds |
| `TTL key` | Check remaining time in seconds |
| `PEXPIRE key milliseconds` | Set expiration in milliseconds |
| `PTTL key` | Check remaining time in milliseconds |

Redis expiration commands help manage temporary data automatically 🚀
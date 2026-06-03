# ⏳ SETEX and PSETEX in Redis

Redis provides `SETEX` and `PSETEX` commands to create keys with expiration time.

These commands automatically delete keys after a specified time.

Useful for:

- 🔐 OTPs
- 👤 Sessions
- ⚡ Cache data
- 🔑 Temporary tokens

---

# 🕒 SETEX

`SETEX` sets a key with expiration time in **seconds**.

---

# 💻 Syntax

```bash
SETEX key seconds value
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

The key expires after 60 seconds.

---

# 📖 Read the Value

```bash
GET otp
```

Output before expiration:

```text
"1234"
```

After expiration:

```text
(nil)
```

---

# ⏱️ PSETEX

`PSETEX` works like `SETEX`, but expiration time is in **milliseconds**.

---

# 💻 Syntax

```bash
PSETEX key milliseconds value
```

---

# 🧪 Example

```bash
PSETEX token 5000 "abc123"
```

Here:

- `5000` milliseconds = 5 seconds

The key expires after 5 seconds.

---

# ⌛ Check Remaining Time

## Seconds

```bash
TTL otp
```

---

## Milliseconds

```bash
PTTL token
```

---

# ⚡ Difference Between SETEX and PSETEX

| Command | Expiration Time |
|---|---|
| `SETEX` | Seconds |
| `PSETEX` | Milliseconds |

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🔐 OTP | Expire after 60 seconds |
| 👤 Session | Temporary login session |
| ⚡ Cache | Auto-remove cached data |
| 🔑 API Token | Short-lived access token |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SETEX key seconds value` | Set key with expiration in seconds |
| `PSETEX key milliseconds value` | Set key with expiration in milliseconds |

These commands are useful for storing temporary Redis data 🚀
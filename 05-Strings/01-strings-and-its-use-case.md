# 🔤 Redis Strings

Strings are the simplest and most commonly used Redis data type.

A Redis string stores a single value.

The value can be:

- 📝 Text
- 🔢 Numbers
- 📄 JSON
- 🔐 Tokens
- 💾 Binary data

---

# 💻 Creating a String

Use the `SET` command:

```bash
SET username "abhishek"
```

Here:

- `username` → key
- `"abhishek"` → string value

---

# 📖 Reading a String

Use:

```bash
GET username
```

Output:

```text
"abhishek"
```

---

# 🔢 Strings Can Store Numbers

Example:

```bash
SET count 10
```

Get value:

```bash
GET count
```

Output:

```text
"10"
```

Even numbers are stored as strings internally.

---

# ⚡ Why Redis Strings are Popular

Strings are:

- 🚀 Fast
- 🪶 Lightweight
- 📦 Simple to use
- ⚙️ Supported by many Redis commands

Most Redis applications use strings heavily.

---

# 🌍 Common Use Cases of Redis Strings

---

# ⚡ Caching

Store API responses or database results temporarily.

Example:

```bash
SET homepage:data "{...json...}"
```

Helps improve application speed.

---

# 👤 User Sessions

Store login session information.

Example:

```bash
SET session:user:1 "logged_in"
```

---

# 🔐 OTP and Tokens

Store temporary authentication codes.

Example:

```bash
SETEX otp 60 "1234"
```

Key expires automatically after 60 seconds.

---

# 🔢 Counters

Store and update counters like views or likes.

Example:

```bash
SET page:views 100
```

---

# 📄 JSON Storage

Store JSON as plain string.

Example:

```bash
SET user:1 "{\"name\":\"abhishek\",\"age\":25}"
```

---

# 🚦 Rate Limiting

Track API request counts.

Example:

```bash
SET api:user:1 10
```

---

# 🧠 Temporary Application Data

Store short-term application data quickly.

Example:

```bash
SET last_search "redis tutorial"
```

---

# 📋 Common String Commands

| Command | Purpose |
|---|---|
| `SET key value` | Store string |
| `GET key` | Read string |
| `DEL key` | Delete string |
| `EXISTS key` | Check key exists |

---

# 📝 Summary

- 🔤 Strings are the simplest Redis data type
- ⚡ Extremely fast and efficient
- 📦 Store text, numbers, JSON, and more
- 🌍 Commonly used for caching, sessions, OTPs, and counters

Redis strings are simple but very powerful 🚀
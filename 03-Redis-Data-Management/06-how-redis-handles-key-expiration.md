# ⏳ How Redis Handles Key Expiration

Redis automatically removes expired keys using two methods:

1. 💤 Passive Expiration
2. ⚡ Active Expiration

Both methods work together to clean expired keys efficiently.

---

# 💤 Passive Expiration

In passive expiration, Redis checks expiration **only when the key is accessed**.

If the key is expired, Redis deletes it immediately.

---

## 🧪 Example

Create a key with expiration:

```bash
SETEX otp 5 "1234"
```

Wait for 5 seconds.

Now try reading the key:

```bash
GET otp
```

Output:

```text
(nil)
```

What happened?

- Redis checked the key during `GET`
- It found the key expired
- Redis deleted it automatically

---

## 📌 Important Point

In passive expiration:

- ❌ Redis does not continuously scan all keys
- ✅ Expired key is checked only when accessed

This saves CPU usage.

---

# ⚡ Active Expiration

Sometimes expired keys are never accessed again.

To avoid keeping useless expired keys in memory, Redis also runs an active expiration process.

Redis randomly checks keys with expiration in the background.

If expired keys are found, Redis removes them automatically.

---

## 📌 Important Point

In active expiration:

- 🔄 Redis runs background checks
- 🧹 Expired keys are cleaned automatically
- 💾 Helps free memory

---

# 🤝 Why Redis Uses Both Methods

Using both methods gives better performance.

| Method | Purpose |
|---|---|
| 💤 Passive Expiration | Remove expired keys during access |
| ⚡ Active Expiration | Clean unused expired keys in background |

This approach keeps Redis:

- ⚡ Fast
- 💾 Memory efficient
- 🚀 Scalable

---

# 📝 Summary

Redis removes expired keys using:

1. 💤 Passive Expiration  
   - Key checked only when accessed

2. ⚡ Active Expiration  
   - Redis scans and removes expired keys in background

Both methods work together to manage memory efficiently 🚀
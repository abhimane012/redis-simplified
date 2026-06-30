# 🎯 Pattern Subscription (PSUBSCRIBE) in Redis

Redis provides the `PSUBSCRIBE` command to subscribe to channels using **patterns (wildcards)**.

Instead of subscribing to one specific channel, you can listen to multiple channels that match a pattern.

---

# 💻 Syntax

```bash
PSUBSCRIBE pattern
```

---

# 🧪 Example

Subscribe to all channels that start with `news.`

```bash
PSUBSCRIBE news.*
```

---

# 📢 Publish Messages

```bash
PUBLISH news.sports "India won the match!"
PUBLISH news.tech "Redis 8.0 Released!"
PUBLISH news.weather "Rain expected today."
```

---

# 👂 Subscriber Receives

```text
1) "pmessage"
2) "news.*"
3) "news.sports"
4) "India won the match!"
```

```text
1) "pmessage"
2) "news.*"
3) "news.tech"
4) "Redis 8.0 Released!"
```

```text
1) "pmessage"
2) "news.*"
3) "news.weather"
4) "Rain expected today."
```

---

# ❌ Non-Matching Channel

```bash
PUBLISH sports "Football match"
```

No message is received because `sports` does not match `news.*`.

---

# 🎯 Common Wildcard Patterns

| Pattern | Matches |
|---|---|
| `news.*` | `news.tech`, `news.sports` |
| `user.*` | `user.login`, `user.logout` |
| `order.*` | `order.created`, `order.shipped` |
| `*` | All channels |

---

# ⚡ Important Points

- Uses wildcard patterns
- One subscription can listen to many channels
- Messages are received only from matching channels
- Works in real time

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 📰 News apps | `news.*` |
| 👤 User events | `user.*` |
| 🛒 E-commerce | `order.*` |
| ⚙️ Microservices | `service.*` |
| 📊 Monitoring | `logs.*` |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `PSUBSCRIBE pattern` | Subscribe to channels matching a pattern |

`PSUBSCRIBE` makes it easy to listen to multiple related Redis Pub/Sub channels with a single subscription 🚀
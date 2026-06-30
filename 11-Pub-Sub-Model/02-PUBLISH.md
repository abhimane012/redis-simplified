# 📢 PUBLISH in Redis

Redis provides the `PUBLISH` command to send a message to a channel.

Every subscriber listening to that channel receives the message instantly.

---

# 💻 Syntax

```bash
PUBLISH channel message
```

---

# 🧪 Example

Publish a message to the `news` channel:

```bash
PUBLISH news "Redis 8.0 Released!"
```

Output:

```text
(integer) 2
```

This means the message was delivered to **2 subscribers**.

---

# 📷 How It Works

```text
              PUBLISH news "Redis 8.0 Released!"

                        │
                        ▼
                  📡 Channel: news
                  /              \
                 ▼                ▼
        👂 Subscriber 1    👂 Subscriber 2

Both subscribers receive the message.
```

---

# 📌 If No Subscribers Exist

```bash
PUBLISH news "Hello!"
```

Output:

```text
(integer) 0
```

Meaning:

- No clients were subscribed to the `news` channel.
- The message is discarded.

---

# 🔢 Return Value

| Output | Meaning |
|--------|---------|
| `(integer) 0` | No subscribers received the message |
| `(integer) N` | Message delivered to **N** subscribers |

---

# ⚡ Important Points

- Sends a message to a channel
- Delivers messages in real time
- Does not store messages
- Works only with connected subscribers

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 💬 Chat apps | Send messages |
| 🔔 Notifications | Broadcast alerts |
| 📊 Live dashboards | Push updates |
| 🎮 Multiplayer games | Broadcast game events |
| ⚙️ Microservices | Send events between services |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `PUBLISH channel message` | Send a message to a channel |

`PUBLISH` is the command used to broadcast real-time messages in Redis Pub/Sub 🚀
# 📡 Redis Publish/Subscribe (Pub/Sub)

Redis Pub/Sub is a messaging system that allows applications to communicate with each other in **real time**.

Instead of sending messages directly to another application, a message is sent to a **channel**. Any application listening to that channel receives the message instantly.

---

# 🧠 How Pub/Sub Works

There are three main parts:

- 📢 **Publisher** → Sends messages
- 📡 **Channel** → Carries messages
- 👂 **Subscriber** → Receives messages

---

# 📷 Example

```text
                "news"

 Publisher ─────────────► Channel ─────────────► Subscriber 1
                                           └──► Subscriber 2
                                           └──► Subscriber 3
```

When the publisher sends a message to the `news` channel, **every subscriber** listening to `news` receives it.

---

# ⚡ Features

- 🚀 Real-time messaging
- 📡 One publisher, many subscribers
- 🔄 Decouples applications
- 💾 Messages are **not stored**
- 👂 Subscribers only receive messages while connected

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 💬 Chat applications | Real-time messaging |
| 🔔 Notifications | Instant alerts |
| 📊 Live dashboards | Real-time updates |
| 🎮 Multiplayer games | Game events |
| ⚙️ Microservices | Service communication |

---

# 🛠️ Common Pub/Sub Commands

| Command | Purpose |
|---|---|
| `SUBSCRIBE` | Listen to one or more channels |
| `PUBLISH` | Send a message to a channel |
| `UNSUBSCRIBE` | Stop listening to channels |
| `PSUBSCRIBE` | Subscribe using patterns |
| `PUNSUBSCRIBE` | Unsubscribe from patterns |

---

# ⚠️ Important Limitations

- ❌ Messages are **not persisted**
- ❌ If no subscribers are connected, the message is lost
- ❌ Subscribers cannot receive old messages after reconnecting

If you need durable messaging or message history, consider using **Redis Streams** instead.

---

# 📝 Summary

- 📢 Publishers send messages
- 📡 Channels deliver messages
- 👂 Subscribers receive messages in real time
- ⚡ Fast and lightweight communication
- 💾 Messages are temporary and not stored

Redis Pub/Sub is ideal for building fast, real-time communication systems 🚀
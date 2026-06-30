# 👂 SUBSCRIBE in Redis

Redis provides the `SUBSCRIBE` command to listen for messages on one or more channels.

Once subscribed, the client receives every message published to those channels in real time.

---

# 💻 Syntax

```bash
SUBSCRIBE channel1 channel2 channel3
```

---

# 🧪 Example

Subscribe to the `news` channel:

```bash
SUBSCRIBE news
```

Output:

```text
1) "subscribe"
2) "news"
3) (integer) 1
```

The client is now listening for messages on the `news` channel.

---

# 📢 Publisher Sends a Message

In another Redis CLI:

```bash
PUBLISH news "Redis 8.0 Released!"
```

---

# 👂 Subscriber Receives

```text
1) "message"
2) "news"
3) "Redis 8.0 Released!"
```

The message appears instantly.

---

# 📡 Subscribe to Multiple Channels

```bash
SUBSCRIBE news sports weather
```

Now the client receives messages from all three channels.

---

# 📷 How It Works

```text
             PUBLISH news "Hello!"

                     │
                     ▼
               📡 Channel: news
               /              \
              ▼                ▼
      👂 Subscriber 1   👂 Subscriber 2
```

Every subscriber listening to `news` receives the message.

---

# ⚡ Important Points

- Listens for messages in real time
- Can subscribe to multiple channels
- Continues listening until unsubscribed or disconnected
- Messages published before subscribing are **not received**

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 💬 Chat applications | Receive chat messages |
| 🔔 Notifications | Receive alerts |
| 📊 Live dashboards | Receive updates |
| 🎮 Multiplayer games | Listen for game events |
| ⚙️ Microservices | Receive service events |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SUBSCRIBE channel...` | Listen for messages on one or more channels |

`SUBSCRIBE` is used to receive real-time messages from Redis Pub/Sub channels 🚀
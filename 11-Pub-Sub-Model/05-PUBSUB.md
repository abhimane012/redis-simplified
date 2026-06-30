# 📡 PUBSUB in Redis

Redis provides the `PUBSUB` command to inspect the current state of the Pub/Sub system.

It lets you view active channels, subscribers, and pattern subscriptions.

---

# 🛠️ PUBSUB Subcommands

| Command | Purpose |
|---|---|
| `PUBSUB CHANNELS` | List active channels |
| `PUBSUB NUMSUB` | Show subscriber count for channels |
| `PUBSUB NUMPAT` | Show number of pattern subscriptions |
| `PUBSUB SHARDCHANNELS` | List active shard channels *(Redis Cluster)* |
| `PUBSUB SHARDNUMSUB` | Show subscriber count for shard channels *(Redis Cluster)* |

---

# 📖 PUBSUB CHANNELS

Lists all channels that currently have at least one subscriber.

### Syntax

```bash
PUBSUB CHANNELS
```

### Example

```bash
PUBSUB CHANNELS
```

Output:

```text
1) "news"
2) "sports"
3) "weather"
```

You can also filter channels using a pattern:

```bash
PUBSUB CHANNELS news.*
```

---

# 👥 PUBSUB NUMSUB

Shows how many subscribers are listening to one or more channels.

### Syntax

```bash
PUBSUB NUMSUB channel1 channel2
```

### Example

```bash
PUBSUB NUMSUB news sports
```

Output:

```text
1) "news"
2) (integer) 3
3) "sports"
4) (integer) 1
```

Meaning:

- `news` has **3** subscribers.
- `sports` has **1** subscriber.

---

# 🎯 PUBSUB NUMPAT

Shows the total number of active **pattern subscriptions**.

### Syntax

```bash
PUBSUB NUMPAT
```

### Example

```bash
PUBSUB NUMPAT
```

Output:

```text
(integer) 2
```

Meaning:

- There are **2** active `PSUBSCRIBE` pattern subscriptions.

---

# 🌐 PUBSUB SHARDCHANNELS

> Available only in **Redis Cluster**.

Lists all active shard channels.

### Syntax

```bash
PUBSUB SHARDCHANNELS
```

---

# 👥 PUBSUB SHARDNUMSUB

> Available only in **Redis Cluster**.

Shows the subscriber count for shard channels.

### Syntax

```bash
PUBSUB SHARDNUMSUB channel1 channel2
```

---

# ⚡ Important Points

- Used for monitoring Pub/Sub activity
- Does not publish or receive messages
- Helpful for debugging Pub/Sub applications
- `SHARDCHANNELS` and `SHARDNUMSUB` are available only in Redis Cluster

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🔍 Debugging | View active channels |
| 👥 Monitoring | Count subscribers |
| 📊 Analytics | Track Pub/Sub usage |
| ⚙️ Administration | Inspect Pub/Sub system |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `PUBSUB CHANNELS` | List active channels |
| `PUBSUB NUMSUB` | Show subscribers for channels |
| `PUBSUB NUMPAT` | Show total pattern subscriptions |
| `PUBSUB SHARDCHANNELS` | List shard channels *(Cluster only)* |
| `PUBSUB SHARDNUMSUB` | Show shard channel subscribers *(Cluster only)* |

`PUBSUB` commands help you inspect and monitor the Redis Pub/Sub system 🚀
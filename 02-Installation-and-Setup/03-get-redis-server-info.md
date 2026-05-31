# 📊 Getting Redis Server Information

Redis provides commands to check:

- 📌 Server details
- 💾 Memory usage
- 🔌 Connected clients
- ⚡ Performance stats
- 🗂️ Database information
- 🖥️ System information

These commands are very useful for monitoring and debugging Redis.

---

# 💻 Open Redis CLI

Before running commands, open Redis CLI:

```bash
redis-cli
```

---

# 📋 Get Complete Server Information

Use:

```bash
INFO
```

This displays all Redis server information.

Example:

```text
# Server
redis_version:7.0.0

# Memory
used_memory:1024000

# Clients
connected_clients:5
```

---

# 📂 Get Specific Information Sections

Redis allows checking specific sections only.

---

## 🖥️ Server Information

```bash
INFO server
```

Shows:

- Redis version
- Operating system
- Process ID
- Uptime

---

## 💾 Memory Information

```bash
INFO memory
```

Shows:

- Used memory
- Memory peak
- Memory fragmentation

Example:

```text
used_memory:1048576
used_memory_human:1.00M
```

---

## 👤 Client Information

```bash
INFO clients
```

Shows:

- Connected clients
- Blocked clients

Example:

```text
connected_clients:10
```

---

## 📊 Statistics

```bash
INFO stats
```

Shows:

- Total commands processed
- Cache hits/misses
- Expired keys

---

## 🗂️ Database Information

```bash
INFO keyspace
```

Shows database statistics.

Example:

```text
db0:keys=10,expires=2
```

Meaning:

- `10` keys exist
- `2` keys have expiration time

---

# 👀 Check Connected Clients

```bash
CLIENT LIST
```

Shows all connected clients.

Example:

```text
id=3 addr=127.0.0.1:5000 name=
```

---

# ⚡ Check Server Ping

```bash
PING
```

Output:

```text
PONG
```

Used to verify Redis server is alive.

---

# ⏱️ Check Server Uptime

```bash
INFO server
```

Look for:

```text
uptime_in_seconds
```

---

# 💾 Check Memory Usage of a Key

```bash
MEMORY USAGE username
```

Example output:

```text
56
```

This means the key uses 56 bytes.

---

# 🔌 Check Redis Configuration

```bash
CONFIG GET *
```

Get a specific config:

```bash
CONFIG GET maxmemory
```

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `INFO` | Get all server information |
| `INFO memory` | Memory details |
| `INFO clients` | Client details |
| `INFO stats` | Statistics |
| `INFO keyspace` | Database info |
| `CLIENT LIST` | Connected clients |
| `PING` | Check server status |
| `CONFIG GET *` | View configuration |

Redis provides many built-in commands for monitoring and managing the server easily 🚀
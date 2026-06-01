# 💾 Saving Redis Data Using SHUTDOWN

Redis mainly stores data in memory (RAM).

To avoid losing data, Redis can save data to disk when the server shuts down properly.

The `SHUTDOWN` command safely stops the Redis server and saves data before exiting.

---

# 🛑 SHUTDOWN Command

Use:

```bash
SHUTDOWN
```

What happens:

1. 💾 Redis saves data to disk
2. 🔌 Client connections are closed
3. 🛑 Redis server stops safely

---

# 🧪 Example

Inside Redis CLI:

```bash
SHUTDOWN
```

After running the command:

- Redis server stops
- Redis CLI disconnects automatically

---

# ⚡ Why Use SHUTDOWN?

Using `SHUTDOWN` is safer than forcefully killing the process.

It helps:

- 💾 Save data properly
- 🚫 Prevent data loss
- 🛡️ Shut down Redis cleanly

---

# ❌ What Happens After Shutdown?

After shutdown:

```bash
redis-cli ping
```

Output:

```text
Could not connect to Redis
```

Because the server is stopped.

---

# ▶️ Start Redis Again

## 🐧 Linux

```bash
sudo systemctl start redis-server
```

## 🍎 macOS

```bash
brew services start redis
```

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `SHUTDOWN` | Save data and stop Redis server safely |

`SHUTDOWN` is the proper way to stop Redis while protecting stored data 🚀
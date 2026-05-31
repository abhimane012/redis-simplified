# ▶️ Starting and Shutting Down Redis Server

After installing Redis, you need to know how to:

- ▶️ Start the Redis server
- 🛑 Stop the Redis server
- 🔄 Restart the Redis server
- ✅ Check if Redis is running

---

# 🚀 Starting Redis Server

## 🐧 Linux

Start Redis:

```bash
sudo systemctl start redis-server
```

---

## 🍎 macOS (Homebrew)

Start Redis:

```bash
brew services start redis
```

---

## 🪟 Windows (Docker)

Start Redis container:

```bash
docker start redis-server
```

If container does not exist yet:

```bash
docker run --name redis-server -p 6379:6379 redis
```

---

# ✅ Check if Redis is Running

Run:

```bash
redis-cli ping
```

Output:

```text
PONG
```

If you see `PONG`, Redis server is running correctly 🎉

---

# 🛑 Shutting Down Redis Server

## 🐧 Linux

Stop Redis:

```bash
sudo systemctl stop redis-server
```

---

## 🍎 macOS (Homebrew)

Stop Redis:

```bash
brew services stop redis
```

---

## 🪟 Windows (Docker)

Stop Redis container:

```bash
docker stop redis-server
```

---

# 🔄 Restart Redis Server

Sometimes you may need to restart Redis after configuration changes.

## 🐧 Linux

```bash
sudo systemctl restart redis-server
```

---

## 🍎 macOS

```bash
brew services restart redis
```

---

## 🪟 Windows (Docker)

```bash
docker restart redis-server
```

---

# 📊 Check Redis Server Status

## 🐧 Linux

```bash
sudo systemctl status redis-server
```

---

## 🍎 macOS

```bash
brew services list
```

---

# 💻 Start Redis Manually

You can also start Redis manually using:

```bash
redis-server
```

This starts Redis in the current terminal window.

To stop it:

```text
CTRL + C
```

---

# 🔌 Default Redis Port

Redis runs on port:

```text
6379
```

---

# 📝 Summary

| Action | Linux | macOS | Windows (Docker) |
|---|---|---|---|
| ▶️ Start | `sudo systemctl start redis-server` | `brew services start redis` | `docker start redis-server` |
| 🛑 Stop | `sudo systemctl stop redis-server` | `brew services stop redis` | `docker stop redis-server` |
| 🔄 Restart | `sudo systemctl restart redis-server` | `brew services restart redis` | `docker restart redis-server` |

Redis server management is simple and only requires a few commands 🚀
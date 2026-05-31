# 💻 Redis CLI

Redis CLI is the **command line tool** used to interact with the Redis server.

CLI stands for:

> **C**ommand **L**ine **I**nterface

Using Redis CLI, you can:

- 📦 Store data
- 📖 Read data
- ❌ Delete data
- ⚙️ Run Redis commands
- 📊 Check server information

---

# 🚀 Starting Redis CLI

Open terminal and run:

```bash
redis-cli
```

If Redis is running correctly, you will enter the Redis shell:

```text
127.0.0.1:6379>
```

Now you can run Redis commands.

---

# 🧪 Testing Redis Connection

Run:

```bash
PING
```

Output:

```text
PONG
```

This means Redis server is working correctly ✅

---

# ✍️ Example Commands

Store a value:

```bash
SET name "Redis"
```

Get the value:

```bash
GET name
```

Output:

```text
"Redis"
```

Delete the value:

```bash
DEL name
```

---

# 🔌 Connect to a Different Host or Port

Default Redis port:

```text
6379
```

Connect manually:

```bash
redis-cli -h localhost -p 6379
```

---

# 🔐 Connect with Password

```bash
redis-cli -a yourpassword
```

---

# 🚪 Exit Redis CLI

Run:

```bash
EXIT
```

Or press:

```text
CTRL + C
```

---

# 📌 Why Redis CLI is Useful

Redis CLI is useful for:

- 🧪 Testing commands
- 🛠️ Debugging
- 📊 Checking Redis data
- ⚙️ Managing Redis server
- 📚 Learning Redis easily

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `redis-cli` | Open Redis CLI |
| `PING` | Test Redis connection |
| `SET` | Store data |
| `GET` | Read data |
| `DEL` | Delete data |
| `EXIT` | Exit Redis CLI |

Redis CLI is the easiest way to interact with Redis and practice commands 🚀
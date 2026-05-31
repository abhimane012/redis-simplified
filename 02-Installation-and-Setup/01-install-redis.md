# ⚙️ Redis Installation Guide

This section explains how to install Redis on:

- 🐧 Linux
- 🍎 macOS (Homebrew)
- 🪟 Windows

---

# 🐧 Install Redis on Linux

Redis can be installed easily using the package manager.

## 📦 Ubuntu / Debian

Update packages:

```bash
sudo apt update
```

Install Redis:

```bash
sudo apt install redis-server
```

---

## ▶️ Start Redis Server

```bash
sudo systemctl start redis-server
```

Enable Redis on boot:

```bash
sudo systemctl enable redis-server
```

---

## ✅ Check Redis Status

```bash
sudo systemctl status redis-server
```

---

## 🧪 Test Redis

Run:

```bash
redis-cli ping
```

Output:

```text
PONG
```

If you see `PONG`, Redis is working correctly 🎉

---

# 🍎 Install Redis on macOS (Homebrew)

## 📦 Install Homebrew

If Homebrew is not installed:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

---

## 📥 Install Redis

```bash
brew install redis
```

---

## ▶️ Start Redis

```bash
brew services start redis
```

---

## 🛑 Stop Redis

```bash
brew services stop redis
```

---

## 🧪 Test Redis

```bash
redis-cli ping
```

Output:

```text
PONG
```

---

# 🪟 Install Redis on Windows

Redis does not officially support Windows directly.

The recommended way is using:

- 🐳 Docker
- 🐧 WSL (Windows Subsystem for Linux)

---

## ✅ Option 1: Install Redis Using Docker

Pull Redis image:

```bash
docker pull redis
```

Run Redis container:

```bash
docker run --name redis-server -p 6379:6379 redis
```

---

## 🧪 Test Redis

Open another terminal:

```bash
docker exec -it redis-server redis-cli
```

Then run:

```bash
ping
```

Output:

```text
PONG
```

---

## ✅ Option 2: Install Redis Using WSL

Install WSL:

```powershell
wsl --install
```

After installing Ubuntu in WSL, follow the Linux installation steps.

---

# 🔌 Default Redis Port

Redis runs on:

```text
6379
```

---

# 💻 Open Redis CLI

You can open the Redis command line tool using:

```bash
redis-cli
```

---

# 🛑 Stop Redis Server

## Linux

```bash
sudo systemctl stop redis-server
```

## macOS

```bash
brew services stop redis
```

---

# ✅ Verify Installation

Run:

```bash
redis-cli ping
```

If Redis is installed correctly, you will see:

```text
PONG
```

---

# 📝 Summary

| OS | Installation Method |
|---|---|
| 🐧 Linux | `apt install redis-server` |
| 🍎 macOS | `brew install redis` |
| 🪟 Windows | Docker or WSL |

Redis is lightweight and very easy to set up 🚀
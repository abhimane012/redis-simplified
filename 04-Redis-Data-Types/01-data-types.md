# 🧩 Redis Data Types

Redis supports multiple data types to store different kinds of data efficiently.

Each data type is designed for specific use cases.

---

# 📦 Main Redis Data Types

Redis mainly supports:

1. 🔤 Strings
2. 📋 Lists
3. 🎯 Sets
4. 🗃️ Hashes
5. 📊 Sorted Sets
6. 🌊 Streams

---

# 🔤 Strings

Strings are the simplest and most commonly used Redis data type.

They store:

- Text
- Numbers
- JSON
- Binary data

---

## 🧪 Example

```bash
SET username "abhishek"
GET username
```

---

## 📌 Use Cases

- 👤 User names
- 🔐 Tokens
- ⚡ Cache data
- 🔢 Counters

---

# 📋 Lists

Lists store multiple values in order.

Items can be added to the left or right side.

---

## 🧪 Example

```bash
LPUSH fruits apple banana mango
```

Read list:

```bash
LRANGE fruits 0 -1
```

---

## 📌 Use Cases

- 📨 Queues
- 📜 Activity logs
- 💬 Chat messages

---

# 🎯 Sets

Sets store unique values.

Duplicate values are not allowed.

---

## 🧪 Example

```bash
SADD tags redis database cache
```

Read set:

```bash
SMEMBERS tags
```

---

## 📌 Use Cases

- 🏷️ Tags
- 👥 Unique users
- 👍 Likes

---

# 🗃️ Hashes

Hashes store data in field-value format.

Similar to objects or dictionaries.

---

## 🧪 Example

```bash
HSET user:1 name "abhishek" age 25
```

Read hash:

```bash
HGETALL user:1
```

---

## 📌 Use Cases

- 👤 User profiles
- 📦 Product details
- ⚙️ Configuration data

---

# 📊 Sorted Sets

Sorted Sets are like sets, but every value has a score.

Values are automatically sorted by score.

---

## 🧪 Example

```bash
ZADD leaderboard 100 abhishek
```

Read sorted set:

```bash
ZRANGE leaderboard 0 -1 WITHSCORES
```

---

## 📌 Use Cases

- 🏆 Leaderboards
- 📈 Rankings
- 🎮 Gaming scores

---

# 🌊 Streams

Streams store continuously generated data.

Used for real-time event processing.

---

## 🧪 Example

```bash
XADD logs * message "user login"
```

---

## 📌 Use Cases

- 📡 Event streaming
- 📨 Messaging systems
- 📊 Log collection

---

# 📝 Summary Table

| Data Type | Description | Example Use |
|---|---|---|
| 🔤 String | Simple value | Cache, tokens |
| 📋 List | Ordered collection | Queues |
| 🎯 Set | Unique values | Tags |
| 🗃️ Hash | Field-value pairs | User profile |
| 📊 Sorted Set | Sorted values with scores | Leaderboards |
| 🌊 Stream | Real-time data stream | Event systems |

Redis data types make it flexible and powerful for many applications 🚀
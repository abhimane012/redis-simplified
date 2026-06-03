# 📦 Using Serialized JSON in Redis Strings

Redis strings can store JSON data as a plain string.

Usually, applications convert objects into JSON format before storing them in Redis.

This process is called:

> 🔄 Serialization

---

# 🧠 What is Serialized JSON?

Serialized JSON means converting an object into a JSON string.

Example object:

```json
{
  "name": "Abhishek",
  "age": 25,
  "country": "India"
}
```

Stored in Redis as:

```text
"{\"name\":\"Abhishek\",\"age\":25,\"country\":\"India\"}"
```

---

# 💻 Store JSON in Redis

Use the `SET` command:

```bash
SET user:1 "{\"name\":\"Abhishek\",\"age\":25}"
```

---

# 📖 Read JSON from Redis

```bash
GET user:1
```

Output:

```text
"{\"name\":\"Abhishek\",\"age\":25}"
```

Applications usually deserialize this back into an object.

---

# 🌍 Why Store JSON in Redis?

JSON storage is useful for:

- 👤 User profiles
- ⚙️ Application settings
- 🛒 Product information
- 📊 API responses
- ⚡ Cache data

---

# ✅ Advantages

- 📦 Easy to store complex data
- 🌍 JSON works in almost every programming language
- ⚡ Fast retrieval using Redis strings

---

# ⚠️ Important Limitation

Redis treats JSON as a normal string.

This means:

- ❌ Cannot directly update JSON fields
- ❌ Entire JSON must be replaced for updates

Example:

```bash
SET user:1 "{\"name\":\"Redis User\",\"age\":25}"
```

Entire value gets overwritten.

---

# 🚀 Better Alternative: RedisJSON

Redis also provides a module called:

```text
RedisJSON
```

It allows working with JSON fields directly.

Example features:

- Update single fields
- Query JSON data
- Modify nested values

---

# 📝 Summary

| Concept | Meaning |
|---|---|
| 🔄 Serialization | Convert object to JSON string |
| 📦 Redis String | Stores serialized JSON |
| 📖 Deserialization | Convert JSON string back to object |

Serialized JSON is commonly used in Redis for storing structured application data 🚀
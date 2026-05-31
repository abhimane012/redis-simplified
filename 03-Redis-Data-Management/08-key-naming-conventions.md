# 🏷️ Redis Key Naming Conventions

Redis keys can have any name, but using a proper naming convention makes data easier to:

- 📖 Read
- 🔍 Search
- 🛠️ Manage
- 🧹 Maintain

Good key names help keep Redis clean and organized.

---

# ✅ Use Meaningful Names

Key names should clearly describe the data.

### 👍 Good Examples

```text
user:1
user:name
product:100
session:token
cart:user:45
```

### 👎 Bad Examples

```text
u1
abc
data123
x
```

Bad names are confusing and hard to understand.

---

# 📂 Use Colon (`:`) as Separator

Colon is commonly used to organize keys.

Example:

```text
user:100:name
user:100:email
product:200:price
```

This creates a clean structure.

Think of `:` like folders.

---

# 🆔 Include IDs When Needed

Use IDs to uniquely identify records.

Example:

```text
user:1
user:2
user:3
```

This helps avoid duplicate keys.

---

# 🛒 Group Related Data

Related keys should follow a similar pattern.

Example:

```text
cart:user:10
cart:user:20
cart:user:30
```

This makes searching and debugging easier.

---

# 🔡 Use Lowercase

Lowercase keys are easier to read and maintain.

### 👍 Recommended

```text
user:name
product:price
```

### 👎 Avoid

```text
UserName
PRODUCTPRICE
```

---

# 🚫 Avoid Very Long Keys

Keys should be descriptive but not too long.

### 👍 Better

```text
user:100:email
```

### 👎 Too Long

```text
application:user:data:personal:email:id:100
```

Very long keys waste memory.

---

# ⚡ Common Naming Patterns

| Purpose | Example |
|---|---|
| 👤 User | `user:1` |
| 🛒 Cart | `cart:user:1` |
| 🔐 Session | `session:token:123` |
| 📦 Product | `product:100` |
| 💬 Chat | `chat:room:1` |

---

# 📝 Summary

## ✅ Best Practices

- Use meaningful names
- Use `:` as separator
- Keep naming consistent
- Use lowercase
- Include IDs when needed
- Avoid very long keys

Good naming conventions make Redis easier to use and manage 🚀
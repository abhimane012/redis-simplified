# 🧠 Redis String Encoding Types

Redis internally stores strings using different encoding formats.

These encodings help Redis:

- ⚡ Improve performance
- 💾 Save memory
- 🚀 Handle data efficiently

The encoding is managed automatically by Redis.

---

# 📦 Main String Encoding Types

Redis mainly uses:

1. 🔢 `int`
2. 🧵 `embstr`
3. 📄 `raw`

---

# 🔢 int Encoding

If a string contains only an integer number, Redis stores it using `int` encoding.

---

## 🧪 Example

```bash
SET count 100
```

Check encoding:

```bash
OBJECT ENCODING count
```

Output:

```text
"int"
```

---

## 📌 Why int Encoding?

Redis stores numbers efficiently in binary integer format.

This:

- 💾 Saves memory
- ⚡ Makes numeric operations faster

---

# 🧵 embstr Encoding

Small string values are stored using `embstr` encoding.

`embstr` means:

> Embedded String

---

## 🧪 Example

```bash
SET name "Redis"
```

Check encoding:

```bash
OBJECT ENCODING name
```

Possible output:

```text
"embstr"
```

---

## 📌 Why embstr Encoding?

Used for short strings because:

- ⚡ Faster access
- 💾 Better memory usage
- 🪶 Lightweight structure

---

# 📄 raw Encoding

Large strings are stored using `raw` encoding.

---

## 🧪 Example

```bash
SET description "Very long string value........"
```

Check encoding:

```bash
OBJECT ENCODING description
```

Possible output:

```text
"raw"
```

---

## 📌 Why raw Encoding?

Used for larger strings that need more memory space.

---

# ⚡ Automatic Encoding Selection

Redis automatically chooses the best encoding.

You do not need to manage it manually.

---

# 🔍 Check Encoding Type

Use:

```bash
OBJECT ENCODING key
```

---

# 📝 Summary Table

| Encoding | Used For |
|---|---|
| 🔢 `int` | Integer numbers |
| 🧵 `embstr` | Small strings |
| 📄 `raw` | Large strings |

Redis uses smart internal encodings to improve speed and memory efficiency 🚀
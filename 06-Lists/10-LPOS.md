# 🔍 LPOS in Redis

Redis provides the `LPOS` command to find the position (index) of an item inside a list.

---

# 💻 Syntax

```bash
LPOS key element
```

---

# 🧪 Example

Create a list:

```bash
RPUSH fruits apple banana mango banana orange
```

Find position of `"banana"`:

```bash
LPOS fruits banana
```

Output:

```text
(integer) 1
```

Because `"banana"` first appears at index `1`.

---

# 📌 List Indexes

| Index | Value |
|---|---|
| `0` | apple |
| `1` | banana |
| `2` | mango |
| `3` | banana |
| `4` | orange |

---

# 🔢 Using RANK

`RANK` tells Redis which occurrence to search for.

---

# 💻 Syntax

```bash
LPOS key element RANK number
```

---

# 🧪 Example

```bash
LPOS fruits banana RANK 2
```

Output:

```text
(integer) 3
```

Meaning:

- Find the second occurrence of `"banana"`

---

# 📌 Understanding RANK

| Rank | Meaning |
|---|---|
| `RANK 1` | First occurrence |
| `RANK 2` | Second occurrence |
| `RANK 3` | Third occurrence |

---

# 🔁 Using Negative RANK

Negative rank searches from the end.

Example:

```bash
LPOS fruits banana RANK -1
```

Output:

```text
(integer) 3
```

Meaning:

- Find last occurrence of `"banana"`

---

# 📦 Using COUNT

`COUNT` returns multiple matching positions.

---

# 💻 Syntax

```bash
LPOS key element COUNT number
```

---

# 🧪 Example

```bash
LPOS fruits banana COUNT 2
```

Output:

```text
1) (integer) 1
2) (integer) 3
```

Meaning:

- Return positions of first 2 matching items

---

# 🧪 COUNT 0

```bash
LPOS fruits banana COUNT 0
```

Meaning:

> Return all matching positions

---

# ⚡ Combine RANK and COUNT

Example:

```bash
LPOS fruits banana RANK 2 COUNT 2
```

Meaning:

- Start from second occurrence
- Return next 2 matching positions

---

# ❌ Item Not Found

```bash
LPOS fruits kiwi
```

Output:

```text
(nil)
```

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 🔍 Find item position | Search lists |
| 📜 Locate repeated values | Duplicate entries |
| 📨 Queue analysis | Track task positions |
| 💬 Message lookup | Find chat entries |

---

# 📝 Summary

| Option | Purpose |
|---|---|
| `LPOS` | Find item position |
| `RANK` | Find specific occurrence |
| `COUNT` | Return multiple positions |

`LPOS` helps search and locate elements inside Redis lists efficiently 🚀
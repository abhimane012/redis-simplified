# 🔢 Counting Floating Point Numbers in Redis

Redis also supports incrementing and decrementing floating point numbers (decimal numbers).

This is useful for:

- 💰 Wallet balances
- 📊 Ratings
- 📈 Analytics
- 🛒 Prices
- 🎮 Game points

---

# ⬆️ INCRBYFLOAT

`INCRBYFLOAT` increases a number by a decimal value.

---

# 💻 Syntax

```bash
INCRBYFLOAT key increment
```

---

# 🧪 Example

Create a value:

```bash
SET balance 100.5
```

Increase by `10.25`:

```bash
INCRBYFLOAT balance 10.25
```

Now value becomes:

```text
"110.75"
```

---

# 📖 Check the Value

```bash
GET balance
```

Output:

```text
"110.75"
```

---

# ⬇️ Decreasing Floating Point Numbers

Redis does not have a separate `DECRBYFLOAT` command.

Instead, use a negative value with `INCRBYFLOAT`.

---

# 🧪 Example

```bash
SET wallet 500.75
```

Decrease by `50.25`:

```bash
INCRBYFLOAT wallet -50.25
```

Now value becomes:

```text
"450.5"
```

---

# ⚡ Important Points

- Works only with numeric values
- Supports decimal numbers
- Operation is atomic
- Values are stored as strings internally

---

# ❌ Invalid Example

```bash
SET username "abhishek"
INCRBYFLOAT username 1.5
```

Output:

```text
(error) value is not a valid float
```

Because `"abhishek"` is not a number.

---

# 🌍 Common Use Cases

| Use Case | Example |
|---|---|
| 💰 Wallet Balance | Add money |
| 📊 Ratings | Update average rating |
| 🛒 Product Price | Modify price |
| 🎮 Game Points | Add bonus points |
| 📈 Analytics | Track decimal metrics |

---

# 📝 Summary

| Command | Purpose |
|---|---|
| `INCRBYFLOAT key value` | Increase or decrease floating point number |

Use positive values to increase and negative values to decrease 🚀
## 🔐 BXI Cipher System – Bitsikii Extension Interface

The **BXI Cipher** is a custom **4-bit binary encryption scheme** that maps letters **A–Z** into compact, binary-encoded values. Designed for lightweight encryption and educational purposes, it allows you to encode text using only 4 bits per letter.

---

## 📌 Formula: Calculating the BXI Value

To get the **BXI value** of any letter:

```
BXI(n) = ⌊n / 2⌋ + 1
```

Where:

* `n` is the letter's alphabetical position (A = 1, B = 2, ..., Z = 26)
* `⌊ ⌋` is the **floor function** (drop any decimals)

### 🔢 BXI Values Range:

```
A–Z → BXI values: 1 to 14
```

---

## 💡 Conversion Table: Letter → BXI → Binary

| Letters | Position(s) | BXI Value | 4-Bit Binary |
| ------- | ----------- | --------- | ------------ |
| A       | 1           | 1         | 0001         |
| B–C     | 2–3         | 2         | 0010         |
| D–E     | 4–5         | 3         | 0011         |
| F–G     | 6–7         | 4         | 0100         |
| H–I     | 8–9         | 5         | 0101         |
| J–K     | 10–11       | 6         | 0110         |
| L–M     | 12–13       | 7         | 0111         |
| N–O     | 14–15       | 8         | 1000         |
| P–Q     | 16–17       | 9         | 1001         |
| R–S     | 18–19       | 10        | 1010         |
| T–U     | 20–21       | 11        | 1011         |
| V–W     | 22–23       | 12        | 1100         |
| X–Y     | 24–25       | 13        | 1101         |
| Z       | 26          | 14        | 1110         |

---

## 🧪 Example: Encoding "NO"

### Step-by-step:

* `N = 14` → BXI = ⌊14 / 2⌋ + 1 = 7 + 1 = 8 → Binary: **1000**
* `O = 15` → BXI = ⌊15 / 2⌋ + 1 = 7 + 1 = 8 → Binary: **1000**

✅ **"NO" in BXI Cipher = `1000 1000`**

Because N and O fall into the same group, they share the same BXI value.

---

## 🧠 How to Convert a Number to 4-bit Binary

### Step 1: Understand 4-bit Binary

A **4-bit binary number** uses exactly 4 digits of only `0` and `1`.
Examples:

* `0001` = 1
* `0100` = 4
* `1101` = 13

---

### Step 2: Convert Decimal to Binary

To convert a decimal number into binary:

1. Divide the number by 2
2. Write down the **remainder**
3. Repeat until the quotient is 0
4. Read the remainders **bottom to top**

#### Example: Convert 6 to binary

```
6 ÷ 2 = 3 → remainder 0  
3 ÷ 2 = 1 → remainder 1  
1 ÷ 2 = 0 → remainder 1  
→ Binary: 110  
```

---

### Step 3: Add Leading Zeros

Since `110` only has 3 digits, pad it to 4 digits:
✅ Final 4-bit binary: **0110**

💡 **Quick tip**: Always add leading 0s if the binary result is less than 4 digits.

---

## ✅ Summary

* BXI encodes letters A–Z using 4-bit binary
* Uses the formula `BXI(n) = ⌊n / 2⌋ + 1`
* Binary values range from `0001` to `1110`
* Great for encryption demos, learning binary, and compact encoding

### 👑 Created by RodsonTP

Use it for secure chats, code puzzles, or custom binary art.

# BXI Cipher System – Bitsikii Extension Interface

The BXI Cipher is a custom 4-bit binary encryption scheme that maps letters A–Z into compact, binary-encoded values. Designed for lightweight encryption and educational purposes.

## 📌 Formula
To get the BXI value of any letter:
BXI(n) = ⌊n / 2⌋ + 1

 Where:
- `n` = letter's alphabetical position (A=1, B=2... Z=26)
- `⌊ ⌋` = floor function (drop decimals)

## 📊 Encoding Table
| Letters | BXI Value | 4-Bit Binary |
|---------|----------|--------------|
| A       | 1        | `0001`       |
| B, C    | 2        | `0010`       |
| D, E    | 3        | `0011`       |
| F, G    | 4        | `0100`       |
| H, I    | 5        | `0101`       |
| J, K    | 6        | `0110`       |
| L, M    | 7        | `0111`       |
| N, O    | 8        | `1000`       |
| P, Q    | 9        | `1001`       |
| R, S    | 10       | `1010`       |
| T, U    | 11       | `1011`       |
| V, W    | 12       | `1100`       |
| X, Y    | 13       | `1101`       |
| Z       | 14       | `1110`       |
| [Space] | 15       | `1111`       |

## 🧪 Example: "NO"
N = position 14 → ⌊14/2⌋+1 = 8 → 1000
O = position 15 → ⌊15/2⌋+1 = 8 → 1000
Encoded: 1000 1000


## 💡 Key Features
- 4-bit efficiency (smaller than ASCII)
- Letter pairs share codes (B/C both = `0010`)
- Space support via `1111`
- Designed for education and fun
- 
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


## 🔄 Optional XOR Extension
Want to make it more secure? Add XOR encryption:

### How It Works
1. Choose a 4-bit key (e.g., `1010`)
2. Apply XOR to any selected letters:
Example:
Key: 1010
NO: 0010 0010

### Example: "HELLO"  
- **Basic**: `0101 0100 0111 0111 1000`  
- **With XOR (key=1010)**: `0101 1111 0111 1101 1000`  
---


### Pros/Cons
| Feature     | Basic BXI | BXI + XOR |
|------------|----------|-----------|
| Collisions | Yes (B=C) | No        |
| Security   | Low       | Medium    |
| Complexity | Simple    | Moderate  |

## 🧪 Example: "HELLO"
- **Basic**: `0101 0100 0111 0111 1000`  
- **With XOR (key=1010)**: `0101 1111 0111 1101 1000`
  
---


### 👑 Created by RodsonTP

Use it for secure chats, code puzzles, or custom binary art.

# 🔐 BXI Cipher System

**The BXI Cipher** is a custom 4‑bit binary coding scheme that maps A–Z into compact and secure values for encrypted conversations.

---

## 📌 Formula: BXI value

BXI(n)= [n/2] + 1

- `n` = letter position in the alphabet (A=1, ..., Z=26)
- `⌊ ⌋` = floor function (drop decimals)

🔹 BXI values range from 0 to 14.

---

## 🔢 Convert to 4‑bit binary

Take any BXI value (`0–13`) and convert it like this:

1. Convert to binary
2. Zero‑pad to 4 digits (left side)

| Letter(s) | Position(s) | BXI Value | 4-bit Binary |
| --------- | ----------- | --------- | ------------ |
| A         | 1           | 1         | `0001`       |
| B–C       | 2–3         | 2         | `0010`       |
| D–E       | 4–5         | 3         | `0011`       |
| F–G       | 6–7         | 4         | `0100`       |
| H–I       | 8–9         | 5         | `0101`       |
| J–K       | 10–11       | 6         | `0110`       |
| L–M       | 12–13       | 7         | `0111`       |
| N–O       | 14–15       | 8         | `1000`       |
| P–Q       | 16–17       | 9         | `1001`       |
| R–S       | 18–19       | 10        | `1010`       |
| T–U       | 20–21       | 11        | `1011`       |
| V–W       | 22–23       | 12        | `1100`       |
| X–Y       | 24–25       | 13        | `1101`       |
| Z         | 26          | 14        | `1110`       |

---

## 🔐 Example: ENCODE "NO"

- `N = 14` → `BXI = ⌊(13/2)⌋+1 = 6+1 = 7` → `0111`  
- `O = 15` → `BXI = ⌊(14/2)⌋+1 = 7+1 = 8` → `1000`

**"NO" in BXI = `0111 1000`**

Remember when converting BXI(n)= [n/2] + 1
n should be the aphabetical number of the letter ex. Z is 26.
and after getting the answer you should learn how to convert number onto 4 bits binary but I will explain and teach you on how to convert it.

Tutorial: How to Convert a Number into 4-bit Binary

Step 1: Know What "4-bit Binary" Means
A 4-bit binary number is simply a binary number with exactly 4 digits, using only 0 and 1.
Examples:

0001 = 1

0100 = 4

1101 = 13

✅ Step 2: Convert the Number to Binary
To convert a decimal number (base 10) into binary (base 2):

👉 Keep dividing the number by 2, and write down the remainder each time.

Then, read the remainders bottom to top.

🧪 Example: Convert 6 to binary
6 ÷ 2 = 3   → remainder 0
3 ÷ 2 = 1   → remainder 1
1 ÷ 2 = 0   → remainder 1
Read the remainders bottom to top: 110
So, 6 in binary is 110

Step 3: Pad with Leading Zeros (if needed)
Binary 110 only has 3 digits.
But for 4-bit binary, we need 4 digits.

So we add a leading 0 in front:
110 → 0110 
💡 Quick Rule:
If your binary result has fewer than 4 digits, add 0s on the left until it’s 4 digits.

---

### 👑 Created by RodsonTP

Use it for secure chats, code puzzles, or custom binary art.

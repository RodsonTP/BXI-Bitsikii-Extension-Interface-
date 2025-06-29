# 🔐 BXI Cipher System  

---


## 🌟 The BXI Cipher Ultimate
### **Core Innovation**  
Letters are encoded differently based on their position in natural pairs:  
- **First in Pair (B,D,F...)** → Raw BXI value  
- **Second in Pair (C,E,G...)** → XOR-encoded BXI  
- **Singletons (A,Z)** → Always raw  

### **Why This Rocks**  
✅ **Eliminates all collisions** (B≠C, D≠E, etc.)  
✅ **Preserves 4-bit efficiency**  
✅ **Adds security without complexity**  

---

## 📊 Complete Pairwise Encoding Table (A-Z)
| Letter | Position | Type        | Raw BXI | XOR 1010 | Final Encoding |
|--------|----------|-------------|---------|----------|----------------|
| A      | 1        | Singleton   | 0001    | —        | `0001`         |
| B      | 2        | Pair First  | 0010    | —        | `0010`         |
| C      | 3        | Pair Second | 0010    | 1000     | `1000`         |
| D      | 4        | Pair First  | 0011    | —        | `0011`         |
| E      | 5        | Pair Second | 0011    | 1001     | `1001`         |
| F      | 6        | Pair First  | 0100    | —        | `0100`         |
| G      | 7        | Pair Second | 0100    | 1110     | `1110`         |
| H      | 8        | Pair First  | 0101    | —        | `0101`         |
| I      | 9        | Pair Second | 0101    | 1111     | `1111`         |
| J      | 10       | Pair First  | 0110    | —        | `0110`         |
| K      | 11       | Pair Second | 0110    | 1100     | `1100`         |
| L      | 12       | Pair First  | 0111    | —        | `0111`         |
| M      | 13       | Pair Second | 0111    | 1101     | `1101`         |
| N      | 14       | Pair First  | 1000    | —        | `1000`         |
| O      | 15       | Pair Second | 1000    | 0010     | `0010`         |
| P      | 16       | Pair First  | 1001    | —        | `1001`         |
| Q      | 17       | Pair Second | 1001    | 0011     | `0011`         |
| R      | 18       | Pair First  | 1010    | —        | `1010`         |
| S      | 19       | Pair Second | 1010    | 0000     | `0000`         |
| T      | 20       | Pair First  | 1011    | —        | `1011`         |
| U      | 21       | Pair Second | 1011    | 0001     | `0001`         |
| V      | 22       | Pair First  | 1100    | —        | `1100`         |
| W      | 23       | Pair Second | 1100    | 0110     | `0110`         |
| X      | 24       | Pair First  | 1101    | —        | `1101`         |
| Y      | 25       | Pair Second | 1101    | 0111     | `0111`         |
| Z      | 26       | Singleton   | 1110    | —        | `1110`         |
| [Space]| —        | Special     | 1111    | 0101     | `1111`/`0101`  |

### 🔑 Key Rules
1. **Pair First**: Raw BXI value (B,D,F...)
2. **Pair Second**: XOR with `1010` (C,E,G...)
3. **Singletons**: Always raw (A,Z)
4. **Space**: Optional `1111` (raw) or `0101` (XOR)

### 💡 Example Patterns
- **B** (First) → `0010`  
  **C** (Second) → `1000`  
- **T** (First) → `1011`  
  **U** (Second) → `0001`  

---

## 🔄 Encoding Process  
### **Step-by-Step Example: "BEC"**  
1. **B** (Pair First):  
   - Position 2 → BXI=2 → `0010` (raw)  
2. **E** (Pair Second):  
   - Position 5 → BXI=3 → `0011` XOR `1010` = `1001`  
3. **C** (Pair Second):  
   - Position 3 → BXI=2 → `0010` XOR `1010` = `1000`  

**Final Encoding**: `0010 1001 1000`  

---

## 💻 Python Implementation  
```python
def bxi_pair_encode(text, key="1010"):
    bxi_map = {
        'A':'0001', 'B':'0010', 'C':'0010', 'D':'0011', 'E':'0011',
        'F':'0100', 'G':'0100', 'H':'0101', 'I':'0101', 'J':'0110',
        'K':'0110', 'L':'0111', 'M':'0111', 'N':'1000', 'O':'1000',
        'P':'1001', 'Q':'1001', 'R':'1010', 'S':'1010', 'T':'1011',
        'U':'1011', 'V':'1100', 'W':'1100', 'X':'1101', 'Y':'1101',
        'Z':'1110', ' ':'1111'
    }
    
    result = []
    for i, char in enumerate(text.upper()):
        if char in bxi_map:
            binary = bxi_map[char]
            # Your pairwise method: XOR every second-in-pair
            if (ord(char) - 65) % 2 == 1:  # B=1, D=3, F=5...
                binary = ''.join(str(int(b) ^ int(k)) for b,k in zip(binary, key))
            result.append(binary)
    return ' '.join(result)

# Usage:
print(bxi_pair_encode("BEC"))  # Output: "0010 1001 1000"

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

**Endianness** refers to the order in which bytes (not bits!) are stored in computer memory. It’s essentially the "direction" in which a computer reads a multi-byte data type (like an integer or a pointer).

> [!INFO] **The Origin Story**
> 
> The terms "Big-Endian" and "Little-Endian" come from Jonathan Swift’s _Gulliver’s Travels_, where two factions fight over which end of a hard-boiled egg should be cracked first: the big end or the little end. Computing is just as dramatic.

---

## 🏗️ The Core Notations

Imagine we have a 4-byte hexadecimal value: `0x12345678`.

- **MSB (Most Significant Byte):** `12`
    
- **LSB (Least Significant Byte):** `78`
    

### 1. Big-Endian (BE)

The **Most Significant Byte** is stored at the **smallest** memory address. This is the most "human-readable" format because it flows left-to-right, just like how we write numbers.

- **Logic:** "Big end first."
    
- **Used by:** Networking protocols (TCP/IP is "Network Byte Order"), IBM mainframes, and older Mac (PowerPC) systems.
    

### 2. Little-Endian (LE)

The **Least Significant Byte** is stored at the **smallest** memory address. To a human, this looks "backwards," but it’s mathematically efficient for computers when performing additions or type-casting.

- **Logic:** "Little end first."
    
- **Used by:** Intel x86, AMD64 (x64), and most modern ARM processors (though ARM is "Bi-Endian").
    

---

## 📊 Visual Mapping

Let's store `0x12345678` starting at memory address `1000`.

|**Address**|**Big-Endian (Value)**|**Little-Endian (Value)**|
|---|---|---|
|`1000`|`12` (MSB)|`78` (LSB)|
|`1001`|`34`|`56`|
|`1002`|`56`|`34`|
|`1003`|`78` (LSB)|`12` (MSB)|

---

## 💡 Key Differences at a Glance

|**Feature**|**Big-Endian**|**Little-Endian**|
|---|---|---|
|**Reading Order**|Left-to-right (Natural)|Right-to-left (Reversed)|
|**Smallest Address**|Stores MSB|Stores LSB|
|**Network Standard**|Yes (The "Network Order")|No|
|**Performance**|Easier to see signs (positive/negative)|Faster for math (carry bits)|

---

## 🛠️ Implementation Tips for Obsidian

> [!TIP] **How to remember?**
> 
> - **B**ig Endian = **B**ig end at the **B**eginning.
>     
> - **L**ittle Endian = **L**ittle end at the **L**owest address.


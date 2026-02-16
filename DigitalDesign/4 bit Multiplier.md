1. **Partial Products:** For each bit in the multiplier ($B$), you multiply it by the multiplicand ($A$).
    
    - If the bit is `1`, the partial product is $A$.
        
    - If the bit is `0`, the partial product is `0`.
        
2. **Shifting:** Each subsequent partial product is shifted one position to the left.
    
3. **Addition:** All partial products are summed together to get the final result.
    

---

## Obsidian Notes

Markdown

```verilog
# 4-Bit Multiplier Design

## Overview
- **Inputs:** $A[3:0]$, $B[3:0]$ (4-bit unsigned)
- **Output:** $P[7:0]$ (8-bit product)
- **Method:** Combinational Array Multiplication (Shift and Add)

## Multiplication Table (Logic)
Given $A = a_3 a_2 a_1 a_0$ and $B = b_3 b_2 b_1 b_0$:

1. **Row 0:** $A \times b_0$ (Shift 0)
2. **Row 1:** $A \times b_1$ (Shift 1)
3. **Row 2:** $A \times b_2$ (Shift 2)
4. **Row 3:** $A \times b_3$ (Shift 3)
5. **Sum:** $Row0 + Row1 + Row2 + Row3$

## Components
- **AND Gates:** To generate partial products ($A_i \text{ AND } B_j$).
- **Full Adders:** To sum the shifted partial products.
```

---
## Verilog Implementation

This uses a simple combinational approach for clarity.

Verilog

```verilog
module multiplier_4bit (
    input [3:0] A,
    input [3:0] B,
    output [7:0] P
);
    // Simple behavioral multiplication
    assign P = A * B;
endmodule
```

---

## Testbench

```verilog
module tb_multiplier;
    reg [3:0] A, B;
    wire [7:0] P;

    // Instantiate the multiplier
    multiplier_4bit uut (
        .A(A),
        .B(B),
        .P(P)
    );

    initial begin
        // Test Case 1: 3 * 2 = 6
        A = 4'd3; B = 4'd2; #10;
        
        // Test Case 2: 15 * 15 = 225
        A = 4'd15; B = 4'd15; #10;
        
        // Test Case 3: 7 * 8 = 56
        A = 4'd7; B = 4'd8; #10;

        $finish;
    end
endmodule
```


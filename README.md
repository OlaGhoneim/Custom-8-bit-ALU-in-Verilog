#  Custom 8-bit ALU in Verilog

##  Overview

This project implements a custom **8-bit Arithmetic Logic Unit (ALU)** using Verilog HDL.
The ALU performs arithmetic, logical, shift, rotation, and comparison operations based on a 4-bit control signal (`AluOp`), and generates status flags.

---

##  Academic Context

**Cairo University**
Faculty of Computing and Artificial Intelligence
Department of Computer Science

This project was developed as an individual assignment for the **Computer Organization and Architecture** course.

---

##  ALU Specifications

###  Inputs

* `A` → 8-bit input
* `B` → 8-bit input
* `AluOp` → 4-bit control signal

###  Outputs

* `Result` → 8-bit output
* `Zero` → 1 if result is zero
* `Negative` → 1 if result is negative (MSB = 1)
* `Overflow` → 1 if signed overflow occurs

---

## Supported Operations

| AluOp | Operation      | Description            |
| ----- | -------------- | ---------------------- |
| 0000  | A + B          | Addition               |
| 0001  | B - A          | Reverse subtraction    |
| 0010  | A + 1          | Increment              |
| 0101  | A == B         | Set on equal           |
| 0110  | B <<< 1        | Arithmetic left shift  |
| 0111  | B >>> 1        | Arithmetic right shift |
| 1000  | NOT A          | Bitwise NOT            |
| 1001  | A AND B        | Bitwise AND            |
| 1010  | A OR B         | Bitwise OR             |
| 1011  | A NAND B       | Bitwise NAND           |
| 1100  | Rotate A left  | Circular left shift    |
| 1101  | Rotate A right | Circular right shift   |

---

##  Flags Behavior

* **Zero Flag** → Set when all bits of the result are 0
* **Negative Flag** → Reflects the sign bit (MSB)
* **Overflow Flag** → Indicates signed overflow in arithmetic operations

Special Case:

* `AluOp = 1111` → All flags are set to **1**

---

##  Design Approach

* Fully modular design:

  * Adder module (`adder_forALU`)
  * Multiplexer modules (`mux_forALU`)
  * Logic unit modules
  * Shift and rotation modules

* Structural modeling used for:

  * Adder
  * Multiplexers
  * Logic gates

* Behavioral modeling used where appropriate

* Operation selection implemented using **multiplexers only**
  (No `if` or `case` statements inside ALU module)

* Supports **2’s complement signed arithmetic**

---

##  Testbench

A complete testbench is included in the same `.vl` file to verify:

* All ALU operations
* Flag correctness (Zero, Negative, Overflow)
* Edge cases (overflow, negative results, equality checks)

---

##  How to Run

1. Open the project in a Verilog simulator (ModelSim / Vivado)
2. Compile the `.vl` file
3. Run the testbench
4. Observe:

   * Console output
   * Waveform results


---

##  Skills Demonstrated

* Verilog HDL
* Digital Logic Design
* ALU Architecture
* Structural Modeling
* Modular Design
* Testbench Development
* 2’s Complement Arithmetic


 Author

Ola Ghoneim
Computer Science Student

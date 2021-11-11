# Best solutions for [nandgame.com](http://nandgame.com/)

* [Logic Gates](#logic-gates)
	+ [Nand](#nand) (1 relay)
	+ [Invert](#invert) (1 nand gate)
	+ [And](#and) (2 nand gates)
	+ [Or](#or) (3 nand gates)
	+ [Xor](#xor) (4 nand gates)
* [Arithmetics](#arithmetics)
	+ [Half Adder](#half-adder) (5 nand gates)
	+ [Full Adder](#full-adder) (9 nand gates)
	+ [Multi-bit Adder](#multi-bit-adder) (18 nand gates)
	+ [Increment](#increment) (145 nand gates)
	+ [Subtraction](#subtraction) (161 nand gates)
	+ [Equal to Zero](#equal-to-zero) (10 nand gates)
	+ [Less than Zero](#less-than-zero)
* [Plumbing](#plumbing)
	+ [Selector](#selector) (4 nand gates)
	+ [Switch](#switch) (5 nand gates)
* [Memory](#memory)
	+ [Latch](#latch) (4 nand gates)
	+ [Data Flip-Flop](#data-flip-flop) (9 nand gates)
	+ [Register](#register) (15 nand gates)
	+ [Counter](#counter) (607 nand gates)
	+ [RAM](#ram) (309 nand gates)
* [Arithmetic Logic Unit](#arithmetic-logic-unit)
	+ [Unary ALU](#unary-alu) (144 nand gates)
	+ [ALU](#alu) (608 nand gates)
	+ [Opcodes](#opcodes)
	+ [Condition](#condition) (56 nand gates)
* [Processor](#processor)
	+ [Combined Memory](#combined-memory) (240 + 79104 nand gates)
	+ [Instruction Decoder](#instruction-decoder) (130 nand gates)
	+ [Control Unit](#control-unit) (1162 + 79104 nand gates)
	+ [Computer](#computer) (1769 + 79104  nand gates)
	+ [Input and Output](#input-and-output) (66 nand gates)
* [Programming](#programming)
	+ [Machine code](#machine-code), [Assembler](#assembler), [Escape Labyrinth](#escape-labyrinth)


# Logic Gates
## Nand
`!(x & y)`

![Nand](01_Logic_Gates/001_Nand.png)

## Invert
`!x`

![Invert](01_Logic_Gates/002_Invert.png)

## And
`x & y`

![And](01_Logic_Gates/003_And.png)

## Or
`x | y`

![Or](01_Logic_Gates/004_Or.png)

## Xor
`x ^ y`

![Xor](01_Logic_Gates/005_Xor.png)

# Arithmetics
## Half Adder
![Half Adder](02_Arithmetics/006_Half-Adder.png)

## Full Adder
![Full Adder](02_Arithmetics/007_Full-Adder.png)

## Multi-bit Adder
![Multi-bit Adder](02_Arithmetics/008_Multi-bit-Adder.png)

## Increment
![Increment](02_Arithmetics/009_Increment.png)

## Subtraction
![Subtraction](02_Arithmetics/010_Subtraction.png)

## Equal to Zero
![Equal to Zero](02_Arithmetics/011_Equal-to-Zero.png)

## Less than Zero
![Less than Zero](02_Arithmetics/012_Less-than-Zero.png)

# Plumbing
## Selector
![Selector](03_Plumbing/013_Selector.png)

## Switch
![Switch](03_Plumbing/014_Switch.png)

# Memory
## Latch
![Latch](04_Memory/015_Latch.png)

## Data Flip-Flop
![Data Flip-Flop](04_Memory/016_Data-Flip-Flop.png)

## Register
![Register (minimal nand gates)](04_Memory/017_Register_min_nands.png)
![Register](04_Memory/017_Register.png)

## Counter
![Counter](04_Memory/018_Counter.png)

## RAM
![RAM](04_Memory/019_RAM.png)

# Arithmetic Logic Unit
## Unary ALU
![Unary ALU](05_Arithmetic_Logic_Unit/020_Unary-ALU.png)

## ALU
![ALU (minimal nand gates](05_Arithmetic_Logic_Unit/021_ALU_min_nands.png)
![ALU](05_Arithmetic_Logic_Unit/021_ALU.png)

## Opcodes
| Opcode | zx | nx | zy | ny | f | no |
| :----: |:--:|:--:|:--:|:--:|:-:|:--:|
| X      | 0  | 0  | 1  | 0  | 1 | 0  |
| Y      | 1  | 0  | 0  | 0  | 1 | 0  |
| X & Y  | 0  | 0  | 0  | 0  | 0 | 0  |
| X | Y  | 0  | 1  | 0  | 1  | 0 | 1  |
| ~X     | 0  | 1  | 1  | 0  | 1 | 0  |
| ~Y     | 1  | 0  | 0  | 1  | 1 | 0  |
| X + Y  | 0  | 0  | 0  | 0  | 1 | 0  |
| X - Y  | 0  | 1  | 0  | 0  | 1 | 1  |
| Y - X  | 0  | 0  | 0  | 1  | 1 | 1  |
| 0      | 1  | 0  | 1  | 0  | 0 | 0  |
| -1     | 1  | 1  | 1  | 0  | 1 | 0  |
| 1      | 1  | 1  | 1  | 1  | 1 | 1  |
| -X     | 0  | 0  | 1  | 1  | 1 | 1  |
| -Y     | 1  | 1  | 0  | 0  | 1 | 1  |
| X + 1  | 0  | 1  | 1  | 1  | 1 | 1  |
| Y + 1  | 1  | 1  | 0  | 1  | 1 | 1  |
| X - 1  | 0  | 0  | 1  | 1  | 1 | 0  |
| Y - 1  | 1  | 1  | 0  | 0  | 1 | 0  |

![Opcodes](05_Arithmetic_Logic_Unit/022_Opcodes.png)

## Condition
![Conditon](05_Arithmetic_Logic_Unit/023_Condition.png)

# Processor
## Combined Memory
![Combined Memory](06_Processor/024_Combined-Memory.png)

## Instruction Decoder
![Instruction Decoder](06_Processor/025_Instruction-Decoder.png)

## Control Unit
![Control Unit](06_Processor/026_Control-Unit.png)

## Computer
![Computer](06_Processor/027_Computer.png)

## Input and Output
![Input and Output](06_Processor/028_Input-and-Output.png)

# Programming
## Machine code
| ci |   |   | sm | zx | nx | zy | ny | f | no | a | d | \*a | lt | eq | gt |
|:--:|:-:|:-:|:--:|:--:|:--:|:--:|:--:|:-:|:--:|:-:|:-:|:---:|:--:|:--:|:--:|
| 1  | 0 | 0 | 0  | 1  | 0  | 1  | 0  | 1 | 0  | 0 | 1 | 0   | 0  | 0  | 0  |
| 0  | 0 | 0 | 0  | 0  | 0  | 0  | 0  | 0 | 0  | 0 | 0 | 0   | 0  | 1  | 0  |
| 1  | 0 | 0 | 0  | 0  | 1  | 1  | 1  | 1 | 1  | 0 | 1 | 0   | 0  | 0  | 0  |
| 1  | 0 | 0 | 0  | 0  | 0  | 0  | 0  | 0 | 0  | 0 | 0 | 0   | 1  | 1  | 1  |

![Machine code](07_Programming/029_Machine-code.png)

## Assembler
```asm
# Assembler code 
loop:
A = 0x7FFF
*A = *A+1
*A = *A+1
A = loop
JMP
```
![Assembler](07_Programming/030_Assembler.png)

## Escape Labyrinth
```asm
begin:
A = 0x7FFF
D = *A
A = 255
D = D - A
A = begin
D - 1; JGT
A = 0x7FFF
D = *A
A = 255
D = D - A
A = tl
D - 1; JEQ
fw:
A = 4
D = A
A = 0x7FFF
*A = D + *A
A = begin
JMP
tl:
A = 8
D = A
A = 0x7FFF
*A = D + *A
A = begin
JMP
```
![Escape Labyrinth](07_Programming/031_Escape-Labyrinth.png)



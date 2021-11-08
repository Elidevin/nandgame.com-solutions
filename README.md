# Best solutions for [nandgame.com](http://nandgame.com/)

* [Logic Gates](#logic-gates)
	+ [Nand](#nand), [Invert](#invert), [And](#and), [Or](#or), [Xor](#xor)

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



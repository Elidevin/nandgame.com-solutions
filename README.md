# Best solutions for [nandgame.com](http://nandgame.com/)

## Hardware
* [Logic Gates](#logic-gates)
	+ [Nand](#nand) (2 relays)
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
* [Switching](#switching)
	+ [Selector](#selector) (4 nand gates)
	+ [Switch](#switch) (4 nand gates)
* [Arithmetic Logic Unit](#arithmetic-logic-unit)
	+ [Logic Unit](#logic-unit) (X nand gates)
	+ [Arithmetic Unit](#arithmetic-unit) (X nand gates)
	+ [ALU](#alu)
	+ [Condition](#condition) (X nand gates)
* [Memory](#memory)
	+ [Latch](#latch) (4 nand gates)
	+ [Data Flip-Flop](#data-flip-flop) (9 nand gates)
	+ [Register](#register) (15 nand gates)
	+ [Counter](#counter) (330 nand gates)
	+ [RAM](#ram) (309 nand gates)
* [Processor](#processor)
	+ [Combined Memory](#combined-memory) (240 + 79104 nand gates)
	+ [Instruction](#instruction) (X nand gates)
	+ [Control Unit](#control-unit) (1162 + 79104 nand gates)
	+ [Computer](#computer) (1492 + 79104  nand gates)
	+ [Input and Output](#input-and-output) (66 nand gates)
## Software
* [Low level](#low-level)
	+ [Machine code](#machine-code)
	+ [Assembler Language](#assembler-language)
	+ [Assembler program](#assembler-program)
	+ [Escape Labyrinth](#escape-labyrinth)
	+ [Display](#display)
	+ [Network](#network)
* [Stack machine](#stack-machine)
	+ [Init stack](#init-stack)
	+ [Push D](#push-d)
	+ [Pop D](#pop-d)
	+ [Pop A](#pop-a)
	+ [Push Value](#push-value)
	+ [Add](#add)
	+ [Sub](#sub)
	+ [Neg](#neg)
	+ ~~[And](#and)~~
	+ ~~[Or](#or)~~
* [High-level language](#high-level-language)
	+ [Tokenize](#tokenize)
	+ [Grammar](#grammar)
	+ [Code generation](#code-generation)
* [Conditionals](#conditionals)
	+ ~~[Eq](#eq)~~
	+ ~~[Gt](#gt)~~
	+ ~~[Lt](#lt)~~
	+ ~~[Not](#not)~~
	+ ~~[Goto](#goto)~~
	+ ~~[If-goto](#if-goto)~~
* [Memory](#memory)
	+ ~~[Push Memory](#push-memory)~~
	+ ~~[Pop Memory](#pop-memory)~~
	+ ~~[Push Static](#push-static)~~
	+ ~~[Pop Static](#pop-static)~~
* [Functions](#functions)
	+ ~~[Call](#call)~~
	+ ~~[Function](#function)~~
	+ ~~[Return](#return)~~
	+ ~~[Push argument](#push-argument)~~
	+ ~~[Pop argument](#pop-argument)~~
	+ ~~[Push local](#push-local)~~
	+ ~~[Pop local](#pop-local)~~
## Optional Levels
* [Transistor level](#transistor-level)
	+ [Nand (CMOS)](#nand-cmos)
	+ ~~[Invert (CMOS)](#invert-cmos)~~
	+ ~~[Nor (CMOS)](#nor-cmos)~~
* [Logic](#logic)
	+ [Xnor](#xnor) (5 nand gates)
	+ [Left Shift](#left-shift)
	+ [Logical Right Shift](#logical-right-shift)
	+ [Artithmetic Right Shift](#artithmetic-right-shift)
	+ [Barrel Shift Left](#barrel-shift-left) (194 nand gates)
* [Arithmetics](#arithmetics)
	+ [Max](#max) (225 nand gates)
	+ [Multiplication](#multiplication) (1520 nand gates)
* [Floating point](#floating-point)
	+ [Unpack floating-point value](#unpack-floating-point-value) (47 nand gates)
	+ [Floating-point multiplication](#floating-point-multiplication) (661 nand gates)
	+ [Normalize overflow](#normalize-overflow) (517 nand gates)
	+ [Verify exponent](#verify-exponent) (111 nand gates)
	+ [Align significands](#align-significands) (547 nand gates)
	+ [Add signed magnitude](#add-signed-magnitude) (610 nand gates)
	+ [Normalize underflow](#normalize-underflow)
	+ [Pack floating-point value](#pack-floating-point-value)
	+ [Floating-point multiplication](#floating-point-multiplication)
	+ [Floating-point addition](#floating-point-addition)
* [Multitasking](#multitasking) `preview`
	+ [Timer Trigger](#timer-trigger) `preview`
	+ [Mode controller](#mode-controller) `preview`
	+ [Register with backup](#register-with-backup) `preview`
	+ [Program Counter](#program-counter) `preview`
	+ [Register bank](#register-bank) `preview`
	+ [General-purpose Memory](#general-purpose-memory) `preview`
	+ [Virtual Memory](#virtual-memory) `preview`
	+ [Control Unit](#control-unit) `preview`
	+ [Processor](#processor) `preview`

# Logic Gates
## Nand
| x | y | out |          |
|:-:|:-:|:---:|:--------:|
| 0 | 0 |  1  | !x  & !y |
| 0 | 1 |  1  | !x  &  y |
| 1 | 0 |  1  |  x  & !y |
| 1 | 1 |  0  |          |

|          |                         |
|:--------:|:-----------------------:|
| !x  & !y | Peirce's arrow          |
| !x  &  y | Converse nonimplication |
|  x  & !y | Material nonimplication |
|  x  &  y | Logical conjunction     |


<details><summary> Peirce's arrow </summary>

|!x |!y |  ↓  |
|:-:|:-:|:---:|
| 1 | 1 |  1  |
| 1 | 0 |  0  |
| 0 | 1 |  0  |
| 0 | 0 |  0  |
</details>
<details><summary> Converse nonimplication </summary>

|!x | y |  <  |
|:-:|:-:|:---:|
| 1 | 0 |  0  |
| 1 | 1 |  1  |
| 0 | 0 |  0  |
| 0 | 1 |  0  |
</details>
<details><summary> Material nonimplication </summary>

| x |!y |  >  |
|:-:|:-:|:---:|
| 0 | 1 |  0  |
| 0 | 0 |  0  |
| 1 | 1 |  1  |
| 1 | 0 |  0  |
</details>
<details><summary> Logical conjunction </summary>

| x | y |  &  |
|:-:|:-:|:---:|
| 0 | 0 |  0  |
| 0 | 1 |  0  |
| 1 | 0 |  0  |
| 1 | 1 |  1  |
</details>

![Nand](01_Logic_Gates/1_Nand.png)

## Invert
| x | out |
|:-:|:---:|
| 0 |  1  |
| 1 |  0  |

```
not(x)
```
```
x nand x
```

![Invert](01_Logic_Gates/2_Invert.png)

## And
| x | y | out |          |
|:-:|:-:|:---:|:--------:|
| 0 | 0 |  0  |          |
| 0 | 1 |  0  |          |
| 1 | 0 |  0  |          |
| 1 | 1 |  1  |  x & y   |

```
x and y
``` 
```
(x nand y) nand (x nand y)
```

![And](01_Logic_Gates/3_And.png)

## Or
| x | y | out |          |
|:-:|:-:|:---:|:--------:|
| 0 | 0 |  0  |          |
| 0 | 1 |  1  | !x &  y  |
| 1 | 0 |  1  |  x & !y  |
| 1 | 1 |  1  |  x &  y  |

```
(not(x) and y) or (x and not(y)) or (x and y)
```
```
(x nand x) nand (y nand y)
```

![Or](01_Logic_Gates/4_Or.png)

## Xor
| x | y | out |          |
|:-:|:-:|:---:|:--------:|
| 0 | 0 |  0  |          |
| 0 | 1 |  1  | !x &  y  |
| 1 | 0 |  1  |  x & !y  |
| 1 | 1 |  0  |          |

```
(not(x) and y) or (x and not(y))
```
```
((x nand y) nand x) nand ((x nand y) nand y)
```

![Xor](01_Logic_Gates/5_Xor.png)

# Arithmetics
## Half Adder
| a | b | h | l |
|:-:|:-:|:-:|:-:|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 0 |

```
h = a and b
```
```
l = a xor b
```

![Half Adder](02_Arithmetics/1_Half-Adder.png)

## Full Adder
| a | b | c | h | l |               |               |
|:-:|:-:|:-:|:-:|:-:|:-------------:|:-------------:|
| 0 | 0 | 0 | 0 | 1 |               | !a & !b & !c  |
| 0 | 0 | 1 | 0 | 1 |               | !a & !b &  c  |
| 0 | 1 | 0 | 0 | 1 |               | !a &  b & !c  |
| 0 | 1 | 1 | 1 | 0 | !a &  b &  c  |               |
| 1 | 0 | 0 | 0 | 1 |               |  a & !b & !c  |
| 1 | 0 | 1 | 1 | 0 |  a & !b &  c  |               |
| 1 | 1 | 0 | 1 | 0 |  a &  b & !c  |               |
| 1 | 1 | 1 | 1 | 1 |  a &  b &  c  |  a &  b &  c  |

```
h = (not(a) and b and c) or (a and not(b) and c) or (a and b and not(c)) or (a and b and c)
```
```
l = (not(a) and not(b) and not(c)) or (not(a) and not(b) and c) or (not(a) and b and not(c)) or (a and not(b) and not(c)) or (a and b and c)
```

![Full Adder](02_Arithmetics/2_Full-Adder.png)

## Multi-bit Adder
![Multi-bit Adder](02_Arithmetics/3_Multi-bit-Adder.png)

## Increment
![Increment](02_Arithmetics/4_Increment.png)

## Subtraction
![Subtraction](02_Arithmetics/5_Subtraction.png)

## Equal to Zero
![Equal to Zero](02_Arithmetics/6_Equal-to-Zero.png)

## Less than Zero
![Less than Zero](02_Arithmetics/7_Less-than-Zero.png)

# Switching
## Selector
![Selector](03_Switching/1_Selector.png)

## Switch
![Switch](03_Switching/2_Switch.png)

# Arithmetic Logic Unit

## Logic Unit
![Logic Unit](04_Arithmetic_Logic_Unit/1_Logic_Unit.png)

## Arithmetic Unit
![Arithmetic Unit](04_Arithmetic_Logic_Unit/2_Arithmetic_Unit.png)

## ALU
![ALU](04_Arithmetic_Logic_Unit/4_ALU.png)

## Condition
![Condition](04_Arithmetic_Logic_Unit/5_Condition.png)

# Memory
## Latch
![Latch](04_Memory/1_Latch.png)

## Data Flip-Flop
![Data Flip-Flop](04_Memory/2_Data-Flip-Flop_min_nands.png)
![Data Flip-Flop](04_Memory/2_Data-Flip-Flop.png)

## Register
![Register (minimal nand gates)](04_Memory/3_Register_min_nands.png)
![Register](04_Memory/3_Register.png)

## Counter
![Counter](04_Memory/4_Counter.png)

## RAM
![RAM](04_Memory/5_RAM.png)

# Processor

## Combined Memory
![Combined Memory](06_Processor/1_Combined-Memory.png)

## Instruction
![Instruction](06_Processor/2_Instruction.png)

## Control Unit
![Control Unit](06_Processor/3_Control-Unit.png)

## Computer
![Computer](06_Processor/4_Computer.png)

## Input and Output
![Input and Output](06_Processor/5_Input-and-Output.png)

# Low level

## Machine code
| ci |   |   | sm | zx | nx | zy | ny | f | no | a | d | \*a | lt | eq | gt |
|:--:|:-:|:-:|:--:|:--:|:--:|:--:|:--:|:-:|:--:|:-:|:-:|:---:|:--:|:--:|:--:|
| 1  | 0 | 0 | 0  | 1  | 0  | 1  | 0  | 1 | 0  | 0 | 1 | 0   | 0  | 0  | 0  |
| 0  | 0 | 0 | 0  | 0  | 0  | 0  | 0  | 0 | 0  | 0 | 0 | 0   | 0  | 1  | 0  |
| 1  | 0 | 0 | 0  | 0  | 1  | 1  | 1  | 1 | 1  | 0 | 1 | 0   | 0  | 0  | 0  |
| 1  | 0 | 0 | 0  | 0  | 0  | 0  | 0  | 0 | 0  | 0 | 0 | 0   | 1  | 1  | 1  |

![Machine code](07_Programming/1_Machine-code.png)

## Assembler Language
```asm
# Assembler code 
loop:
A = 0x7FFF
*A = *A+1
*A = *A+1
A = loop
JMP
```
![Assembler](07_Programming/2_Assembler-Language.png)

## Assembler program
```
pass
```
![Assembler](07_Programming/3_Assembler-program.png)

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
![Escape Labyrinth](07_Programming/4_Escape-Labyrinth.png)

## Display
```asm
A = 0x4000
D = A
*A = D
A = A + 1
*A = D
A = 0x4200
*A = D
```

## Network
```
pass
```

# Stack machine

## Init stack
| Name | Number |
| :--: |:------:|
| SP   | 0      |
```asm
A = 0x0100
D = A
A = SP
*A = D
```

## Push D
```asm
A = SP
A = *A
*A = D
A = SP
*A = *A+1
```

## Pop D
```asm
A = SP
*A = *A-1
A = *A
D = *A
```

## Pop A
```asm
A = SP
*A = *A-1
A = *A
A = *A
```

## Push Value
```asm
A = value
D = A
PUSH_D
```

## Add
```asm
POP_D
POP_A
D = D + A
PUSH_D
```

## Sub
```asm
POP_D
POP_A
D = A - D
PUSH_D
```

## Neg
```asm
POP_A
D = -A
PUSH_D
```

## And
```asm
pass
```

## Or
```asm
pass
```
# High-level language

## Tokenize
| Type    | Match  | Grammar | Name   |
|:-------:|:------:|:-------:|:------:|
| Pattern | [ ]+   | Ignore  |        |
| Pattern | [0-9]+ | Name    | Number |
| Exact   | +      | Literal |        |
| Exact   | -      | Literal |        |
| Exact   | (      | Literal |        |
| Exact   | )      | Literal |        |

## Grammar
| Symbol     | Expression          |
|:----------:|:-------------------:|
| PROGRAM    | Expression          |
| Expression | Expression + Number |
| Expression | Number              |
| Expression | Expression - Number |
| Expression | ( Expression )      |
| Expression | Number - Expression |
| Expression | Number + Expression |
| Expression | - Expression        |

## Code generation
`PROGRAM` `Expression`
```asm

```

`Expression` `Expression + Number`
```asm
[Expression]
PUSH_VALUE [Number]
ADD
```

`Expression` `Number`
```asm
PUSH_VALUE [Number]
```

`Expression` `Expression - Number`
```asm
[Expression]
PUSH_VALUE [Number]
SUB
```

`Expression` `( Expression )`
```asm
[Expression]
```

`Expression` `Number - Expression`
```asm
PUSH_VALUE [Number]
[Expression]
SUB
```

`Expression` `Number + Expression`
```asm
PUSH_VALUE [Number]
[Expression]
ADD
```

`Expression` `- Expression`
```asm
[Expression]
NEG
```

# Conditionals

## Eq
|Name|Number|
|:--:|:----:|
| SP |   0  |
```asm

```

## Gt

## Lt

## Not

## Goto

## If-goto

# Memory

## Push Memory

## Pop Memory

## Push Static

## Pop Static

# Functions

## Call

## Function

## Return

## Push argument

## Pop argument

## Push local

## Pop local

# Transistor level

## Nand (CMOS)
![Nand CMOS](08_Transistor_level/01_Nand_CMOS.png)

## Invert (CMOS)

## Nor (CMOS)

# Logic

## Xnor
![Xnor](09_Logic/1_Xnor.png)

## Left Shift
![Left Shift](09_Logic/2_Left_Shift.png)

## Logical Right Shift
![Logical Right Shift](09_Logic/3_Logical-Right-Shift.png)

## Artithmetic Right Shift
![Artithmetic Right Shift](09_Logic/4_Artithmetic-Right-Shift.png)

## Barrel Shift Left
![Barrel Shift Left](09_Logic/5_Barrel_Shift_Left.png)

# Arithmetics

## Max
![Max](1_Arithmetics/01_Max.png)

## Multiplication
![Multiplication](2_Arithmetics/02_Multiplication.png)

# Floating point

## Unpack float
![Unpack float](11_Floating_point/01_Unpack_float.png)

## Floating-point multiplication
![Floating-point multiplication](11_Floating_point/02_Floating_point_multiplication.png)

## Normalize overflow
![Normalize overflow](11_Floating_point/03_Normalize_overflow.png)

## Verify exponent
![Verify exponent](11_Floating_point/04_Verify_exponent.png)

## Align significands
![Align significands](11_Floating_point/05_Align_significands.png)

## Add signed magnitude
![Add signed magnitude](11_Floating_point/06_Add_signed_magnitude.png)

## Normalize underflow

## Pack float

## Floating-point multiplication

## Floating-point addition



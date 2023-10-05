[↩ Return](README.md)
# Hardware
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
	+ [Data Flip-Flop](#data-flip-flop) (10 nand gates)
	+ [Register](#register) (20 nand gates)
	+ [Counter](#counter) (370 nand gates)
	+ [RAM](#ram) (388 nand gates)
* [Processor](#processor)
	+ [Combined Memory](#combined-memory) (240 + 79104 nand gates)
	+ [Instruction](#instruction) (X nand gates)
	+ [Control Unit](#control-unit) (1162 + 79104 nand gates)
	+ [Computer](#computer) (1492 + 79104  nand gates)
	+ [Input and Output](#input-and-output) (66 nand gates)

***

# Logic Gates

---

## Nand

<details><summary>Relay (Default <strong>on</strong>)</summary>

> | x | y | x < y |
> |:-:|:-:|:-----:|
> | 0 | 0 |   0   |
> | 0 | 1 | **1** |
> | 1 | 0 |   0   |
> | 1 | 1 |   0   |

```mermaid
graph BT;
    X((X))-->R(Relay);
    Y((Y))-->R;
    R-->O((out))

	classDef in1 fill:#333,stroke:#000,stroke-width:2px,color:#55f,font-size:120%;
    classDef in2 fill:#333,stroke:#000,stroke-width:2px,color:#f55,font-size:120%;
    classDef out1 fill:#333,stroke:#000,stroke-width:2px,color:#aaa,font-size:90%;
    classDef relay1 fill:#66f,stroke:#000,stroke-width:2px;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class X, in1
	class Y, in2
	class O, out1
    class R relay1
	class I inv
	linkStyle default stroke-width:2px,fill:none,stroke:grey
	linkStyle 0 stroke:blue,color:blue
	linkStyle 1 stroke:red,color:red
	linkStyle 2 stroke:red,color:red
```

***

> | y | x | y < x |
> |:-:|:-:|:-----:|
> | 0 | 0 |   0   |
> | 1 | 0 |   0   |
> | 0 | 1 | **1** |
> | 1 | 1 |   0   |

```mermaid
graph BT;
    Y((Y))-->R(Relay);
    X((X))-->R;
    R-->O((out))

	classDef in1 fill:#333,stroke:#000,stroke-width:2px,color:#55f,font-size:120%;
    classDef in2 fill:#333,stroke:#000,stroke-width:2px,color:#f55,font-size:120%;
    classDef out1 fill:#333,stroke:#000,stroke-width:2px,color:#aaa,font-size:90%;
    classDef relay1 fill:#66f,stroke:#000,stroke-width:2px;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class Y, in1
	class X, in2
	class O, out1
    class R relay1
	class I inv
	linkStyle default stroke-width:2px,fill:none,stroke:grey
	linkStyle 0 stroke:blue,color:blue
	linkStyle 1 stroke:red,color:red
	linkStyle 2 stroke:red,color:red
```

***

> | x | 1 |  !x   |
> |:-:|:-:|:-----:|
> | 0 | 1 | **1** |
> | 0 | 1 | **1** |
> | 1 | 1 |   0   |
> | 1 | 1 |   0   |

```mermaid
graph BT;
    X((X))-->R(Relay);
    One((1))-->R;
    R-->O((out))

	classDef in1 fill:#333,stroke:#000,stroke-width:2px,color:#55f,font-size:120%;
    classDef in2 fill:#333,stroke:#000,stroke-width:2px,color:#f55,font-size:120%;
    classDef out1 fill:#333,stroke:#000,stroke-width:2px,color:#aaa,font-size:90%;
    classDef relay1 fill:#66f,stroke:#000,stroke-width:2px;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class X, in1
	class One, in2
	class O, out1
    class R relay1
	class I inv
	linkStyle default stroke-width:2px,fill:none,stroke:grey
	linkStyle 0 stroke:blue,color:blue
	linkStyle 1 stroke:red,color:red
	linkStyle 2 stroke:red,color:red
```

***

> | y | 1 |  !y   |
> |:-:|:-:|:-----:|
> | 0 | 1 | **1** |
> | 0 | 1 |   0   |
> | 1 | 1 | **1** |
> | 1 | 1 |   0   |

```mermaid
graph BT;
    Y((Y))-->R(Relay);
    One((1))-->R;
    R-->O((out))

	classDef in1 fill:#333,stroke:#000,stroke-width:2px,color:#55f,font-size:120%;
    classDef in2 fill:#333,stroke:#000,stroke-width:2px,color:#f55,font-size:120%;
    classDef out1 fill:#333,stroke:#000,stroke-width:2px,color:#aaa,font-size:90%;
    classDef relay1 fill:#66f,stroke:#000,stroke-width:2px;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class Y, in1
	class One, in2
	class O, out1
    class R relay1
	class I inv
	linkStyle default stroke-width:2px,fill:none,stroke:grey
	linkStyle 0 stroke:blue,color:blue
	linkStyle 1 stroke:red,color:red
	linkStyle 2 stroke:red,color:red
```

***
</details>
<details><summary>Relay (Default <strong>off</strong>)</summary>

> | x | y | x & y |
> |:-:|:-:|:-----:|
> | 0 | 0 |   0   |
> | 0 | 1 |   0   |
> | 1 | 0 |   0   |
> | 1 | 1 | **1** |

```mermaid
graph BT;
    X((X))-->R(Relay);
    Y((Y))-->R;
    R-->O((out))

	classDef in1 fill:#333,stroke:#000,stroke-width:2px,color:#55f,font-size:120%;
    classDef in2 fill:#333,stroke:#000,stroke-width:2px,color:#f55,font-size:120%;
    classDef out1 fill:#333,stroke:#000,stroke-width:2px,color:#aaa,font-size:90%;
    classDef relay1 fill:#f66,stroke:#000,stroke-width:2px;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class X, in1
	class Y, in2
	class O, out1
    class R relay1
	class I inv
	linkStyle default stroke-width:2px,fill:none,stroke:grey
	linkStyle 0 stroke:blue,color:blue
	linkStyle 1 stroke:red,color:red
	linkStyle 2 stroke:grey,color:grey
```

***
</details>

##### Solutions:
- [ ] `!( !y < x )` 

| y | 1 | → | !y | x | → | r < x | 1 | → | !r |
|:-:|:-:|:-:|:--:|:-:|:-:|:-----:|:-:|:-:|:--:|
| 0 | 1 | → | 1  | 0 | → |   0   | 1 | → | 1  |
| 1 | 1 | → | 0  | 0 | → |   0   | 1 | → | 1  |
| 0 | 1 | → | 1  | 1 | → |   0   | 1 | → | 1  |
| 1 | 1 | → | 0  | 1 | → |   1   | 1 | → | 0  |

```mermaid
graph LR;
	Y((Y))--0\n1\n0\n1-->R1(Relay);
	One((1))--1\n1\n1\n1-->R1;
    X((X))--0\n0\n1\n1--->R2(Relay);
    R1--1\n0\n1\n0-->R2;
    R2--0\n0\n0\n1-->R3(Relay);
    R3--1\n1\n1\n0-->O((out));
	One((1))--1\n1\n1\n1-->R3;

	classDef in1 fill:#333,stroke:#000,stroke-width:2px,color:#55f,font-size:120%;
    classDef in2 fill:#333,stroke:#000,stroke-width:2px,color:#f55,font-size:120%;
    classDef out1 fill:#333,stroke:#000,stroke-width:2px,color:#aaa,font-size:90%;
    classDef relayDefOn fill:#f66,stroke:#000,stroke-width:2px;
    classDef relayDefOff fill:#66f,stroke:#000,stroke-width:2px;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class X in1
    class Y in1
    class One in2
    class O out1
    class R1,R2,R3 relayDefOff
	class I inv
	linkStyle default stroke-width:2px,fill:none,stroke:grey
	linkStyle 0,2 stroke:blue,color:black
	linkStyle 1,3,5,6 stroke:red,color:black,stroke-dasharray:8 3
	linkStyle 4 stroke:violet,color:black
	linkStyle 5 stroke:red,color:black
```

- [ ] `!( !x < y )`

| x | 1 | → | !x | y | → | r < y | 1 | → | !r |
|:-:|:-:|:-:|:--:|:-:|:-:|:-----:|:-:|:-:|:--:|
| 0 | 1 | → | 1  | 0 | → |   0   | 1 | → | 1  |
| 0 | 1 | → | 1  | 1 | → |   0   | 1 | → | 1  |
| 1 | 1 | → | 0  | 0 | → |   0   | 1 | → | 1  |
| 1 | 1 | → | 0  | 1 | → |   1   | 1 | → | 0  |

```mermaid
graph LR;
	X((X))--0\n0\n1\n1-->R1(Relay);
	One((1))--1\n1\n1\n1-->R1;
    Y((Y))--0\n1\n0\n1--->R2(Relay);
    R1--1\n1\n0\n0-->R2;
    R2--0\n0\n0\n1-->R3(Relay);
    R3--1\n1\n1\n0-->O((out));
	One((1))--1\n1\n1\n1-->R3;

	classDef in1 fill:#333,stroke:#000,stroke-width:2px,color:#55f,font-size:120%;
    classDef in2 fill:#333,stroke:#000,stroke-width:2px,color:#f55,font-size:120%;
    classDef out1 fill:#333,stroke:#000,stroke-width:2px,color:#aaa,font-size:90%;
    classDef relayDefOn fill:#f66,stroke:#000,stroke-width:2px;
    classDef relayDefOff fill:#66f,stroke:#000,stroke-width:2px;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class X in1
    class Y in1
    class One in2
    class O out1
    class R1,R2,R3 relayDefOff
	class I inv
	linkStyle default stroke-width:2px,fill:none,stroke:grey
	linkStyle 0,2 stroke:blue,color:black
	linkStyle 1,3,6 stroke:red,color:black,stroke-dasharray:8 3
	linkStyle 4 stroke:violet,color:black
	linkStyle 5 stroke:red,color:black
```

- [x] `!( x & y )`

| x | y | → | x & y | 1 | → | !r |
|:-:|:-:|:-:|:-----:|:-:|:-:|:--:|
| 0 | 0 | → |   0   | 1 | → | 1  |
| 0 | 1 | → |   0   | 1 | → | 1  |
| 1 | 0 | → |   0   | 1 | → | 1  |
| 1 | 1 | → |   1   | 1 | → | 0  |

```mermaid
graph LR;
	X((X))--0\n0\n1\n1-->R1(Relay);
    Y((Y))--0\n1\n0\n1-->R1(Relay);
    R1--1\n1\n1\n0-->R2(Relay);
	One((1))--1\n1\n1\n1-->R1;
	One((1))--1\n1\n1\n1-->R2;
    R2--1\n1\n1\n0-->O((out));

	classDef in1 fill:#333,stroke:#000,stroke-width:2px,color:#55f,font-size:120%;
    classDef in2 fill:#333,stroke:#000,stroke-width:2px,color:#f55,font-size:120%;
    classDef out1 fill:#333,stroke:#000,stroke-width:2px,color:#aaa,font-size:90%;
    classDef relayDefOn fill:#f66,stroke:#000,stroke-width:2px;
    classDef relayDefOff fill:#66f,stroke:#000,stroke-width:2px;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class X in1
    class Y in1
    class One in2
    class O out1
    class R2,R3 relayDefOff
    class R1 relayDefOn
	class I inv
	linkStyle default stroke-width:2px,fill:none,stroke:grey
	linkStyle 0,1 stroke:blue,color:black
	linkStyle 3,4 stroke:red,color:black,stroke-dasharray:8 3
	linkStyle 2 stroke:green,color:black
	linkStyle 5 stroke:red,color:black
```

![Nand](1_Hardware/01_Logic_Gates/1_Nand.png)

---

## Invert
| x |   out |        |
|:-:|:-----:|:------:|
| 0 | **1** | **!x** |
| 1 |   0   |        |

`not(x)` → `x nand x`

```mermaid
graph LR;
    X((X))--0\n1-->N(NAND);
    X-->N;
    N--1\n0-->O((out))
	classDef in1 fill:#ffff80ff,stroke:#000,stroke-width:2px,font-size:130%;
    classDef out1 fill:#aeff73ff,stroke:#000,stroke-width:2px,font-size:90%;
    classDef nand fill:#222,stroke:#000,stroke-width:2px,color:#fff;
    class X, in1
	class O, out1
    class N nand
	linkStyle default stroke:red,color:black,stroke-width:2px,fill:none,stroke-head:red
```

![Invert](1_Hardware/01_Logic_Gates/2_Invert.png)

---

## And
| x | y |   out |           |
|:-:|:-:|:-----:|:---------:|
| 0 | 0 |   0   |           |
| 0 | 1 |   0   |           |
| 1 | 0 |   0   |           |
| 1 | 1 | **1** | **x & y** |

`x and y` → `(x nand y) nand (x nand y)` → `inv(x nand y)`

```mermaid
graph LR;
    X((X))--0\n0\n1\n1-->N(NAND);
    Y((Y))--0\n1\n0\n1-->N;
    N--1\n1\n1\n0-->I{{Invert}};
	I--0\n0\n0\n1-->O((out))

	classDef in1 fill:#ffff80ff,stroke:#000,stroke-width:2px,font-size:130%;
    classDef in2 fill:#00ffffff,stroke:#000,stroke-width:2px,font-size:130%;
    classDef out1 fill:#aeff73ff,stroke:#000,stroke-width:2px,font-size:90%;
    classDef nand fill:#222,stroke:#000,stroke-width:2px,color:#fff;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class X, in1
	class Y, in2
	class O, out1
    class N nand
	class I inv
	linkStyle default stroke:red,color:black,stroke-width:2px,fill:none
```
<details><summary><strong>Scheme</strong></summary>

![And gate scheme](1_Hardware/01_Logic_Gates/and.svg)
</details>

![And](1_Hardware/01_Logic_Gates/3_And.png)

---

## Or
| x | y |   out |             |
|:-:|:-:|:-----:|:-----------:|
| 0 | 0 |   0   |             |
| 0 | 1 | **1** | **!x &  y** |
| 1 | 0 | **1** |  **x & !y** |
| 1 | 1 | **1** |  **x &  y** |

`(not(x) and y) or (x and not(y)) or (x and y)` → `(x nand x) nand (y nand y)` → `inv(x) nand inv(y)`

```mermaid
graph LR;
    X((X))--0\n0\n1\n1-->I1{{Invert}}
	I1--1\n1\n0\n0-->N(NAND)
    Y((Y))--0\n1\n0\n1-->I2{{Invert}}
	I2--1\n0\n1\n0-->N(NAND)
    N--0\n1\n1\n1-->O((out))

	classDef in1 fill:#ffff80ff,stroke:#000,stroke-width:2px,font-size:130%;
    classDef in2 fill:#00ffffff,stroke:#000,stroke-width:2px,font-size:130%;
    classDef out1 fill:#aeff73ff,stroke:#000,stroke-width:2px,font-size:90%;
    classDef nand fill:#222,stroke:#000,stroke-width:2px,color:#fff;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    class X in1
	class Y in2
	class O out1
    class N nand
	class I1,I2 inv
	linkStyle default stroke:red,color:black,stroke-width:2px,fill:none
```

![Or](1_Hardware/01_Logic_Gates/4_Or.png)

***

<details><summary>Base gates</summary>

![Base gates](1_Hardware/01_Logic_Gates/base_gates.svg)
</details>

---

## Xor
| x | y | out |              |
|:-:|:-:|:---:|:------------:|
| 0 | 0 |  0  |              |
| 0 | 1 |  1  | **!x &  y**  |
| 1 | 0 |  1  |  **x & !y**  |
| 1 | 1 |  0  |              |

- [X] Solution #1
`(not(x) and y) or (x and not(y))` → `((x nand y) nand x) nand ((x nand y) nand y)`

```mermaid
graph LR;
    X((X))--->N1([NAND])
    Y((Y))--0\n1\n0\n1--->N2([NAND])
    X((X))--0\n0\n1\n1--->N2
    Y((Y))--->N3([NAND])
	N2--1\n1\n1\n0-->N1
	N2--1\n1\n1\n0-->N3
	N1--1\n1\n0\n1-->N4([NAND])
	N3--1\n0\n1\n1-->N4
    N4--0\n1\n1\n0-->O((out))

	classDef in1 fill:#ffff80ff,stroke:#000,stroke-width:2px,font-size:130%;
    classDef in2 fill:#00ffffff,stroke:#000,stroke-width:2px,font-size:130%;
    classDef out1 fill:#aeff73ff,stroke:#000,stroke-width:2px,font-size:90%;
    classDef nand fill:#222,stroke:#000,stroke-width:2px,color:#fff;
    class X in1
	class Y in2
	class O out1
    class N1,N2,N3,N4 nand
	linkStyle default stroke:red,color:black,stroke-width:2px,fill:none
	linkStyle 0,2 stroke:yellow,color:black,stroke-width:2px,fill:none
	linkStyle 1,3 stroke:blue,color:black,stroke-width:2px,fill:none
	linkStyle 5,4 stroke:green,color:black,stroke-width:2px,fill:none
```

<details><summary>The simplest possible solution</summary>

![Xor gate scheme](1_Hardware/01_Logic_Gates/xor_nands.svg)
</details>

![Xor](1_Hardware/01_Logic_Gates/5_Xor.png)


- [ ] Solution #2

| x | y |   | x ^ y | x \| y|   | r1 & r2 |
|:-:|:-:|:-:|:-----:|:-----:|:-:|:-------:|
| 0 | 0 | → |   0   |   1   | → |    0    |
| 0 | 1 | → |   1   |   1   | → |    1    |
| 1 | 0 | → |   1   |   1   | → |    1    |
| 1 | 1 | → |   1   |   0   | → |    0    |

`(x nand y) and (x or y)`
<details><summary>Scheme</summary>

![And gate scheme](1_Hardware/01_Logic_Gates/xor_nand-or-and.svg)
</details>

```mermaid
graph LR;
    X((X))--0\n0\n1\n1--->N1([NAND])
    Y((Y))--0\n1\n0\n1--->N1
    X((X))--0\n0\n1\n1--->Or1
    Y((Y))--0\n1\n0\n1--->Or1
	N1--1\n1\n1\n0-->And1([AND])
	Or1([OR])--0\n1\n1\n1-->And1
    And1--0\n1\n1\n0-->O((out))

	classDef in1 fill:#ffff80ff,stroke:#000,stroke-width:2px,font-size:130%;
    classDef in2 fill:#00ffffff,stroke:#000,stroke-width:2px,font-size:130%;
    classDef out1 fill:#aeff73ff,stroke:#000,stroke-width:2px,font-size:90%;
    classDef nand fill:#222,stroke:#000,stroke-width:2px,color:#fff;
    classDef inv fill:#f55,stroke:#000,stroke-width:2px;
    classDef or fill:#fa1,stroke:#000,stroke-width:2px;
    classDef and fill:#f55,stroke:#000,stroke-width:2px;
    class X in1
	class Y in2
	class O out1
    class N1 nand
	class Or1 or
	class And1 and
	linkStyle default stroke:red,color:black,stroke-width:2px,fill:none
	linkStyle 0,2 stroke:yellow,color:black,stroke-width:2px,fill:none
	linkStyle 1,3 stroke:blue,color:black,stroke-width:2px,fill:none
	linkStyle 5,4 stroke:green,color:black,stroke-width:2px,fill:none
```

***

### ***Full True Table***

![True Table](1_Hardware/true-table.svg)


***

# Arithmetics

---

## Half Adder
| a | b | |   h   |   l   | |    high   |    low     |
|:-:|:-:|-|:-----:|:-----:|-|:---------:|:----------:|
| 0 | 0 |→|   0   |   0   |→|           |            |
| 0 | 1 |→|   0   | **1** |→|           | **!a & b** |
| 1 | 0 |→|   0   | **1** |→|           | **a & !b** |
| 1 | 1 |→| **1** |   0   |→| **a & b** |            |

```
h = a and b
```
```
l = a xor b
```

![Half Adder](1_Hardware/02_Arithmetics/1_Half-Adder.png)

---

## Full Adder
| a | b | c | |  high |   low | |       high        |       low         |
|:-:|:-:|:-:|-|:-----:|:-----:|-|:-----------------:|:-----------------:|
| 0 | 0 | 0 |→|   0   | **1** |→|                   | **!a & !b & !c**  |
| 0 | 0 | 1 |→|   0   | **1** |→|                   | **!a & !b &  c**  |
| 0 | 1 | 0 |→|   0   | **1** |→|                   | **!a &  b & !c**  |
| 0 | 1 | 1 |→| **1** |   0   |→| **!a &  b &  c**  |                   |
| 1 | 0 | 0 |→|   0   | **1** |→|                   |  **a & !b & !c**  |
| 1 | 0 | 1 |→| **1** |   0   |→|  **a & !b &  c**  |                   |
| 1 | 1 | 0 |→| **1** |   0   |→|  **a &  b & !c**  |                   |
| 1 | 1 | 1 |→| **1** | **1** |→|  **a &  b &  c**  |  **a &  b &  c**  |

```
h = (not(a) and b and c) or (a and not(b) and c) or (a and b and not(c)) or (a and b and c)
```
```
l = (not(a) and not(b) and not(c)) or (not(a) and not(b) and c) or (not(a) and b and not(c)) or (a and not(b) and not(c)) or (a and b and c)
```
![Full Adder](1_Hardware/02_Arithmetics/2_Full-Adder.png)
![Full Adder](1_Hardware/02_Arithmetics/2.1_nand-xor-gate.png)

---

## Multi-bit Adder
![Multi-bit Adder](1_Hardware/02_Arithmetics/3_Multi-bit-Adder.png)

---

## Increment
![Increment](1_Hardware/02_Arithmetics/4_Increment.png)

---

## Subtraction
![Subtraction](1_Hardware/02_Arithmetics/5_Subtraction.png)

---

## Equal to Zero
![Equal to Zero](1_Hardware/02_Arithmetics/6_Equal-to-Zero.png)

---

## Less than Zero
![Less than Zero](1_Hardware/02_Arithmetics/7_Less-than-Zero.png)

---

# Switching

---

## Selector
![Selector](1_Hardware/03_Switching/1_Selector.png)

---

## Switch
![Switch](1_Hardware/03_Switching/2_Switch.png)

---

# Arithmetic Logic Unit

---

## Logic Unit
![Logic Unit](1_Hardware/04_Arithmetic_Logic_Unit/1_Logic_Unit.png)

---

## Arithmetic Unit
![Arithmetic Unit](1_Hardware/04_Arithmetic_Logic_Unit/2_Arithmetic_Unit.png)

---

## ALU
![ALU](1_Hardware/04_Arithmetic_Logic_Unit/3_ALU.png)

---

## Condition
![Condition](1_Hardware/04_Arithmetic_Logic_Unit/4_Condition.png)

---

# Memory

---

## Latch
![Latch](1_Hardware/05_Memory/1_Latch.png)

---

## Data Flip-Flop
![Data Flip-Flop](1_Hardware/05_Memory/2_Data-Flip-Flop.png)

---

## Register
![Register](1_Hardware/05_Memory/3_Register.png)

---

## Counter
![Counter](1_Hardware/05_Memory/4_Counter.png)

---

## RAM
![RAM](1_Hardware/05_Memory/5_RAM.png)

---

# Processor

---

## Combined Memory
![Combined Memory](1_Hardware/06_Processor/1_Combined-Memory.png)

---

## Instruction
![Instruction](1_Hardware/06_Processor/2_Instruction.png)

---

## Control Unit
![Control Unit](1_Hardware/06_Processor/3_Control-Unit.png)

---

## Computer
![Computer](1_Hardware/06_Processor/4_Computer.png)

---

## Input and Output
![Input and Output](1_Hardware/06_Processor/5_Input-and-Output.png)


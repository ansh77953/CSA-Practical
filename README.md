# CSA-Practical
# CPUSim practicals
---
# Practical-1 
# create a machine(Basic Computer Architecture)

| Aim | To create, in CPU Sim, a machine based on the Basic Computer Architecture: its registers, memory, microinstructions, instruction fields and machine instructions.|
|:---|:---:|
| Tools | CPU Sim 4.0.11(Java 8 with JavaFX)|

## Theory
A CPU Sim machine is described at the register-transfer level by four kinds of objects:
---
| object|meaning|dialog|
|:---|:---:|---|
| Hardware modules | Registers, condition bits(single bits that can halt the machine or record a carry) and RAM.| Modify-> Hardware Modules (ctrl+k)|
| Miocroinstructions | Elementary register-tranfer operations such as PC->AR, M[AR]->DR, AC+DC->AC, a test and skip or a decode. | Modify->Microinstructions (ctr+shift+M)|
|machine instructions | A name, an opcode, a format built from field and an execute sequence of micriinstructions, ending with End. | Modify->Machine instructions (ctrrl+M) |
A control unit that runs a stored list of microinstructions for each instruction is a microprogrammed control unit, which is exactly what CPU Sim simulates.
# Creating a new machine:

<img width="590" height="400" alt="image" src="https://github.com/user-attachments/assets/e0ab6717-b7ce-4161-aac1-74781c734f67" />

# Creating a registers:

<img width="1462" height="936" alt="image" src="https://github.com/user-attachments/assets/548a15f5-d2a9-4648-aa7b-833c1d97fbe4" />

# Creating the condition Bits:

<img width="997" height="897" alt="image" src="https://github.com/user-attachments/assets/54da6f2e-e271-4793-9b71-35b9c553cc29" />

# Creating a RAM:

<img width="1241" height="1061" alt="image" src="https://github.com/user-attachments/assets/5b042690-8d35-4ee9-b444-90ad9aba9b7f" />

# Creating a microinstructions 
## TransferRtoR:

<img width="883" height="698" alt="image" src="https://github.com/user-attachments/assets/e7ed16c4-9b4f-4268-af83-da107f8f473b" />

## MemomryAccess:

<img width="787" height="677" alt="image" src="https://github.com/user-attachments/assets/5a5f1554-7ccb-493e-ae6b-26028371044e" />

## Increment:

<img width="1006" height="767" alt="image" src="https://github.com/user-attachments/assets/5d77b1a6-a7f9-4fe9-85fb-acaa74efccc0" />

## Arithmetic:

<img width="696" height="627" alt="image" src="https://github.com/user-attachments/assets/d41b4d10-3303-4049-acba-fc2f01af673d" />

## Logical:

<img width="868" height="746" alt="image" src="https://github.com/user-attachments/assets/2ae3d416-5d78-4aba-b2d0-ef44649b721a" />

## Shift:

<img width="1178" height="898" alt="image" src="https://github.com/user-attachments/assets/a889d384-a5f5-4ccb-a34c-4fcb4e6a924e" />

## Set:

<img width="1133" height="832" alt="image" src="https://github.com/user-attachments/assets/6fd9076b-3296-4daf-bd74-4ebf6cc84228" />

## Test:

<img width="822" height="737" alt="image" src="https://github.com/user-attachments/assets/6569b1b7-8d7e-4640-be60-82a59e1b042c" />

## Decode:

<img width="870" height="783" alt="image" src="https://github.com/user-attachments/assets/5f8e223a-0f2e-4fa2-8296-cae69e69c19f" />

## SetconditionBit:

<img width="1020" height="826" alt="image" src="https://github.com/user-attachments/assets/80e5ab67-5197-44cb-8690-e0c7166aaf57" />

## IO:

<img width="1291" height="885" alt="image" src="https://github.com/user-attachments/assets/4dffeffc-2e1a-4ce9-9774-68e3390d300c" />

## Creating instructions field:

<img width="998" height="845" alt="image" src="https://github.com/user-attachments/assets/eee23375-9dcd-4a88-9a8b-94f71e354952" />

## Creating machine instructions:

<img width="1528" height="1008" alt="image" src="https://github.com/user-attachments/assets/e253f9e5-89b9-421e-98a0-cb4b295eeb12" />
<img width="1055" height="881" alt="image" src="https://github.com/user-attachments/assets/145e1ada-38cb-4ab4-b818-77a63ec865e8" />

## Execute sequence of ADD:

<img width="1156" height="912" alt="image" src="https://github.com/user-attachments/assets/cb7b0032-460d-4279-9289-a2fc71d2e3d0" />

## Execute sequence of ISZ:

<img width="1035" height="883" alt="image" src="https://github.com/user-attachments/assets/5b6ad727-8824-4568-9b10-23eaa8b1c532" />

# Result:
 A machine based on the Basic Computer architecture was created in CPU Sim and saved as BasicCaomputer.cpu 
 Now, we will move onto practical 2, in which there is creation of Fetch sequence, program counter and saving and after that our basic computer will be completed and we can save our machine as BasicComouter.cpu
 

# Practical-2
# Create the Fetch Routine of the instruction Cycle
| Aim | To create the fetch(and decode) routine of the instruction Cycle and observe it one microinstruction at a time. |
|:---|:---:|
| Tool | CPU Sim 4.0.11(Java 8 with JavaFX) |

## Theory
Every instruction cycle begins with the same fetch and decode phase. In Mano's Basuc Computer it takes three clock pulsed, controlled by thr sequence counter outputs T0, T1 and T2
|T0: AR<-PC |
|:---:|
|T1: IR<-M[AR], PC<-PC+1 |
|T2: D0...D7<-Decode IR(12-14), AR<-IR(0-11), I<-IR(15) |
## Fetch Sequence 

<img width="1217" height="988" alt="image" src="https://github.com/user-attachments/assets/e1e1689f-7e73-459a-a98c-3780d58a7037" />

## Testing the routine 
Open the P03_ADD.a file in CPUSim, press Ctrl+2 (assemble & load), then Ctrl+D (debug mode). Set 
the registers' Data selector to Unsigned Dec.

<img width="1896" height="1176" alt="image" src="https://github.com/user-attachments/assets/448e0a0a-7337-4379-a1f8-0cef16c06856" />

Now, Click Step by Micro five times and watch the register changed by each microinstruction

## Observation 
| Micro-step | Microinstruction | Ar | PC | IR |
|:---|:---:|:---:|:---:|---:|
| Start | - | 0 | 0 | 0 |
| 1 | PC->AR | 0 | 0 | 0 |
| 2 | M[AR]->IR | 0 | 0 | 63488(F800) |
| 3 | PC+1->PC | 0 | 1 | 63388|
| 4 | IR(0-11)->AR | 2048(800) | 1 | 63488 |
| 5 | Decode-IR | 2048 | 1 | 63488->INP |

# Result
The fetch routine PC->AR, M[AR]->IR, PC+1->PC, IR(0-11)->AR, decode-IR was created and 
verified by single-stepping the first instruction of a program.
---
# Practical-3  Add Operation on Two User Entered Numbers 
| Aim | To write an assembly program that reads two numbers entered by the user, adds them and displays the sum.|
| :--- | :---: |
| Tool | CPU Sim 4.0.11 (Java 8 with JavaFX) |
## Theory 
INP reads an integer into AC. STA A saves it in memory because the next INP overwrites AC. ADD A is a memory-reference instruction: DR ← M[A], then AC ← AC + DR and the carry out of bit 15 goes to E. OUT displays AC and HLT stops the machine.
Numbers are 16-bit two's complement, so the range is −32768 to +32767
## Program 

```
; ==============================================================
; Practical 3 : ADD operation on two user-entered numbers
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; Logic : SUM = A + B
; ==============================================================
 INP ; AC <- first number typed by the user
 STA A ; M[A] <- AC (save first number)
 INP ; AC <- second number
 ADD A ; AC <- AC + M[A], E <- carry out
 STA SUM ; M[SUM] <- AC (save the result)
 OUT ; display AC (the sum)
 HLT ; stop
A: .data 1 0 ; first number
SUM: .data 1 0 ; result
```

## After assembling and loading

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/7b4a6cf8-a7ba-499c-a64e-ff0acdf40b99" />

Modified the IR(0–11) → AR connection by setting both "srcStartBit" and "destStartBit" to 0, ensuring that CPU Sim maps the address to RAM correctly without any bit shifting.

## Running

<img width="1600" height="672" alt="Image" src="https://github.com/user-attachments/assets/1b93961b-085d-48b3-875c-292842b8eb49" />

#### After Giving first input:

<img width="1615" height="690" alt="Image" src="https://github.com/user-attachments/assets/8b013f9d-558f-4e67-b37c-9c6c6f3b955a" />

#### After Giving the second input:

<img width="1568" height="687" alt="Image" src="https://github.com/user-attachments/assets/cf74eeb5-735a-47b2-9526-d1527bbcc5b8" />

## Observation 
| Input(s) typed | Output displayed|
|:---|:---:|
| 25, 17 | 42 |
| 31, 22 | 53 |
| 1, -1 | 0 |

## Result 
The program correctly adds two user-entered numbers; 25 + 17 = 42

---

# Practical-4 SUBTRACT Operation on Two User-entered Numbers
| Aim | To write an assembly program that reads two numbers A and B and displays A − B. |
|:---|:---:|
| Tool | CPU Sim 4.0.11 (Java 8 with JavaFX) |

## Theory
The Basic Computer has no subtract instruction. Subtraction uses the two's complement: A − B = A + (B′ + 
1). CMA forms the 1's complement B′ and INC adds 1, giving −B, which is then added to A with ADD.

```
; ==============================================================
; Practical 4 : SUBTRACT operation on two user-entered numbers
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; Logic : DIFF = A - B = A + (2's complement of B)
; 2's complement of B = B' + 1 (CMA, then INC)
; ==============================================================
 INP ; AC <- A (minuend)
 STA A ; M[A] <- AC
 INP ; AC <- B (subtrahend)
 CMA ; AC <- AC' (1's complement of B)
 INC ; AC <- AC + 1 (2's complement of B = -B)
 ADD A ; AC <- A + (-B) = A - B
 STA DIFF ; M[DIFF] <- AC
 OUT ; display the difference
 HLT
A: .data 1 0 ; minuend
DIFF: .data 1 0 ; result
```

## After assembling and loading the program

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/6a4023ce-a034-48f6-a377-3393438c79cb" />

## Output after running the program and entering both numbers

<img width="1700" height="624" alt="Image" src="https://github.com/user-attachments/assets/f0b28ace-9f10-41f9-8a0e-0a388653a4b8" />

## Observation 
| Input(s) typed | Output Displayed |
|:---|:---:|
| 10, 5 | 5 |
| -5, -5 | 0| 

## Result
The program subtracts two user-entered numbers using the 2's complement; 10 − 5 = 5 and -5 - (-5) = 0.

# Practical-5 Logical Operations: AND, OR, NOT, XOR, NOR, NAND
| Aim | To write an assembly program that performs AND, OR, NOT, XOR, NOR and NAND on two userentered numbers. |
|:---|:---:|
| Tool | CPU Sim 4.0.11 (Java 8 with JavaFX) |

## Theory
The Basic Computer provides only two logic instructions: AND (memory-reference, AC ← AC ∧ M[addr]) 
and CMA (register-reference, AC ← AC′). Since {AND, NOT} is functionally complete, every other operation 
can be built from them with Boolean algebra, applied to all 16 bits at once:

| Operation | Boolean Identity used | Instruction sequence |
|:---|:---:|:---:|
| A AND B | A.B | LDA A, AND B|
| A OR B | (A′·B′)′ (De Morgan) | LDA B, CMA, STA NB, LDA A, CMA, AND NB, CMA |
| NOT A | A′ | LDA A, CMA |
| A XOR B | (A + B)·(A·B)′ | LDA RAND, CMA, AND ROR |
| A NOR B | (A + B)′ | LDA ROR, CMA |
| A NAND B | (A·B)′ | LDA RAND, CMA |

## Program

```
; ==============================================================
; Practical 5 : Logical operations AND, OR, NOT, XOR, NOR, NAND
; on two user-entered numbers A and B
; Machine : BasicComputer.cpu (Mano's Basic Computer)
;
; The Basic Computer has only two logic instructions:
; AND (memory-reference) AC <- AC ^ M[addr]
; CMA (register-reference) AC <- AC'
; AND + NOT is a functionally complete set, so every other
; operation is built from them with Boolean algebra:
; NAND = (A.B)'
; OR = (A'.B')' (De Morgan)
; NOR = (A + B)'
; XOR = (A + B) . (A.B)'
; Outputs appear in this order: AND, OR, NOT A, NOT B, XOR, NOR, NAND
; ==============================================================
 INP ; AC <- A
 STA A
 INP ; AC <- B
 STA B
; ---------- AND = A . B ----------------------------------------
 LDA A ; AC <- A
 AND B ; AC <- A . B
 STA RAND
 OUT ; output 1 : A AND B
; ---------- OR = (A' . B')' ------------------------------------
 LDA B
 CMA ; AC <- B'
 STA NB ; NB <- B'
 LDA A
 CMA ; AC <- A'
 STA NA ; NA <- A'
Computer System Architecture – CPU Sim Lab Manual
Page 30
 AND NB ; AC <- A' . B'
 CMA ; AC <- (A' . B')' = A + B
 STA ROR
 OUT ; output 2 : A OR B
; ---------- NOT A, NOT B ---------------------------------------
 LDA NA
 OUT ; output 3 : NOT A
 LDA NB
 OUT ; output 4 : NOT B
; ---------- XOR = (A + B) . (A . B)' ---------------------------
 LDA RAND
 CMA ; AC <- (A . B)' = NAND
 STA RNAND
 AND ROR ; AC <- (A + B) . (A . B)'
 STA RXOR
 OUT ; output 5 : A XOR B
; ---------- NOR = (A + B)' -------------------------------------
 LDA ROR
 CMA ; AC <- (A + B)'
 STA RNOR
 OUT ; output 6 : A NOR B
; ---------- NAND = (A . B)' ------------------------------------
 LDA RNAND
 OUT ; output 7 : A NAND B
 HLT
A: .data 1 0
B: .data 1 0
NA: .data 1 0 ; A'
NB: .data 1 0 ; B'
RAND: .data 1 0 ; A AND B
ROR: .data 1 0 ; A OR B
RXOR: .data 1 0 ; A XOR B
RNOR: .data 1 0 ; A NOR B
RNAND: .data 1 0 ; A NAND B
```

## After assembling and loading the program

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/f305caea-002c-4b1b-bbcc-975fde6af4e7" />

## Output after running the program and entering both numbers

<img width="736" height="320" alt="image" src="https://github.com/user-attachments/assets/4a0a3378-54b1-4daa-b46f-1bb89c57a593" />

## Observation 
For A = 12, B = 10
| Operation | 16-bit result (binary) | Hex | Decimal Output |
|:---|:---:|:---:|:---:|
| A=12 | 0000 0000 0000 1100 | 000C | 12 |
| B=10 | 

## Result
All six logical operations were simulated using only AND and CMA. For A = 12 and B = 10 the outputs are 
AND = 8, OR = 14, NOT A = −13, NOT B = −11, XOR = 6, NOR = −15, NAND = −9.



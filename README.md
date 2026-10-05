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

<img width="1077" height="699" alt="Image" src="https://github.com/user-attachments/assets/73a72d2b-d8ce-4e25-8cb8-f87b756dadd1" />

# Creating a registers:

<img width="1080" height="667" alt="Image" src="https://github.com/user-attachments/assets/68b0bcb2-ecf0-4c51-95d8-4974b3ffb223" />

# Creating the condition Bits:

<img width="1080" height="950" alt="Image" src="https://github.com/user-attachments/assets/84b8996b-34da-404c-99d5-6cfb92bab0a3" />

# Creating a RAM:

<img width="1080" height="902" alt="Image" src="https://github.com/user-attachments/assets/3b1fc268-e79a-41fd-a2ff-e15757a6d6ab" />

# Creating a microinstructions 
## TransferRtoR:

<img width="1241" height="1061" alt="image" src="https://github.com/user-attachments/assets/5b042690-8d35-4ee9-b444-90ad9aba9b7f" />

## MemomryAccess:

<img width="1080" height="898" alt="Image" src="https://github.com/user-attachments/assets/6afd0789-66c3-45ce-bcb0-412ec91c74a4" />

## Increment:

<img width="1080" height="810" alt="Image" src="https://github.com/user-attachments/assets/ca785a20-0c81-4eef-b06c-628d1a94365f" />

## Arithmetic:

<img width="1080" height="856" alt="Image" src="https://github.com/user-attachments/assets/a59fc019-66fb-460f-9a05-6d5c18b57716" />

## Logical:

<img width="936" height="707" alt="Image" src="https://github.com/user-attachments/assets/64869b73-b7f7-46f8-9b8e-ae0317d26562" />

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

## Observation 
The Hardware Modules dialog lists the eight registers, the two condition bits and the 4096-word RAM; 33 
microinstructions and 20 machine instructions are defined. Loading the ADD program produces the 
expected machine code (Figure 2 in section A.3)

## Result:
 A machine based on the Basic Computer architecture was created in CPU Sim and saved as BasicCaomputer.cpu 
 
 

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

---
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

---
# Practical-6 Memory-reference Instructions: ADD, LDA, STA, BUN, ISZ
| Aim | To write an assembly program that simulates the memory-reference instructions ADD, LDA, STA, BUN and ISZ. |
|:---|:---:|
| Tool | CPU Sim 4.0.11 (Java 8 with JavaFX) |

## Theory
A memory-reference instruction has an opcode 0–6 and a 12-bit address. During fetch AR ← IR(0–11), so at T4 onwards AR holds the address of the operand (the effective address, since I = 0).
| Symbol | Code | Execute micro-operations |
|:---|:---:|:---:|
| ADD | 1xxx | DR ← M[AR]; AC ← AC + DR, E ← Cout |
| LDA | 2xxx | DR ← M[AR]; AC ← DR |
| STA | 3xxx | M[AR] ← AC |
| BUN | 4xxx | PC<-AR |
| ISZ | 6xxx | DR ← M[AR]; DR ← DR + 1; M[AR] ← DR; if DR = 0 then PC ← PC + 1 |

## Program

```
; ==============================================================
; Practical 6 : Memory-reference instructions ADD, LDA, STA, BUN, ISZ
; Machine : BasicComputer.cpu (Mano's Basic Computer)
;
; Task : multiply X by N using repeated addition.
; PROD = X + X + ... + X (N times)
; CTR holds -N; ISZ adds 1 to it on every pass and
; skips the BUN when it reaches 0, ending the loop.
; Data : X = 5, N = 3 (CTR = -3) -> PROD = 15
; ==============================================================
LOOP: LDA PROD ; AC <- M[PROD]
 ADD X ; AC <- AC + M[X]
 STA PROD ; M[PROD] <- AC
 ISZ CTR ; M[CTR] <- M[CTR] + 1; skip next if it became 0
 BUN LOOP ; PC <- LOOP (repeat)
 LDA PROD ; AC <- final product
 HLT
X: .data 1 5 ; multiplicand
CTR: .data 1 -3 ; -N (loop counter)
PROD: .data 1 0 ; product
```
## After Assembling and loading the program

<img width="1112" height="667" alt="Image" src="https://github.com/user-attachments/assets/49920397-b04d-4f3d-9cdd-788bf28d0022" />


## After step 4 in debug mode:

<img width="588" height="512" alt="image" src="https://github.com/user-attachments/assets/66a1390b-c93e-48e8-a70c-4176fcf1efc3" />


## After step 5:

<img width="592" height="410" alt="image" src="https://github.com/user-attachments/assets/5e60c1aa-518d-4e73-ac88-ada79321303f" />

## After step 14:

<img width="573" height="431" alt="image" src="https://github.com/user-attachments/assets/17a82386-9a9d-48fc-af87-94c32fcc6c86" />

## After step 16:

<img width="580" height="582" alt="Image" src="https://github.com/user-attachments/assets/e1306ce3-3e9f-4d0f-80c3-f3862a311572" />

## Observation 

| Step | PC before | Instruction | IR (hex) | AC | DR | E | PC | AR | IR (dec) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 0 | LDA PROD | 2009 | 0 | 0 | 0 | 1 | 9 | 8201 |
| 2 | 1 | ADD X | 1007 | 5 | 5 | 0 | 2 | 7 | 4103 |
| 3 | 2 | STA PROD | 3009 | 5 | 5 | 0 | 3 | 9 | 12297 |
| 4 | 3 | ISZ CTR | 6008 | 5 | 65534 (-2) | 0 | 4 | 8 | 24584 |
| 5 | 4 | BUN LOOP | 4000 | 5 | 65534 (-2) | 0 | 0 | 0 | 16384 |
| 6 | 0 | LDA PROD | 2009 | 5 | 5 | 0 | 1 | 9 | 8201 |
| 7 | 1 | ADD X | 1007 | 10 | 5 | 0 | 2 | 7 | 4103 |
| 8 | 2 | STA PROD | 3009 | 10 | 5 | 0 | 3 | 9 | 12297 |
| 9 | 3 | ISZ CTR | 6008 | 10 | 65535 (-1) | 0 | 4 | 8 | 24584 |
| 10 | 4 | BUN LOOP | 4000 | 10 | 65535 (-1) | 0 | 0 | 0 | 16384 |
| 11 | 0 | LDA PROD | 2009 | 10 | 10 | 0 | 1 | 9 | 8201 |
| 12 | 1 | ADD X | 1007 | 15 | 5 | 0 | 2 | 7 | 4103 |
| 13 | 2 | STA PROD | 3009 | 15 | 5 | 0 | 3 | 9 | 12297 |
| 14 | 3 | ISZ CTR | 6008 | 15 | 0 | 0 | 5 | 8 | 24584 |
| 15 | 5 | LDA PROD | 2009 | 15 | 15 | 0 | 6 | 9 | 8201 |
| 16 | 6 | HLT | 7001 | 15 | 15 | 0 | 7 | 1 | 28673 |
Values in brackets are the signed interpretation of 16-bit numbers. Final memory: X = 5, CTR = 0, PROD = 
15.


## Result
The memory-reference instructions were simulated: LDA, ADD and STA computed the running product, ISZ 
counted the passes and skipped the branch when the counter reached zero, and BUN formed the loop. 
Final AC = PROD = 15.

---

# Practical-7 Register-reference Instructions: CLA, CMA, CME, HLT
| Aim | To simulate the register-reference instructions CLA, CMA, CME and HLT and determine AC, E, PC, AR and IR in decimal after execution.|
|:---|:---:|
| Tool | CPU Sim 4.0.11 (Java 8 with JavaFX) |

## Theory
Register-reference instructions have the code 7xxx: opcode 111 with I = 0. The low 12 bits select one 
operation on AC or E, executed at T3, with no memory access. Because the fetch routine always performs 
AR ← IR(0–11), AR ends up holding the low 12 bits of the instruction code (for example 800 hex = 2048 for 
CLA).
| Symbol | Code(Hex) | Bit set in IR(0–11) | Micro-operation |
|:---|:---:|:---:|:---:|
| CLA | 7800 | B11 | AC<-0 |
| CMA | 7200 | B9 | AC<-AC' |
| CME | 7100 | B8 | E<-E' |
| HLT | 7001 | B0 | S<-1(halt) |

## Program
```
; ==============================================================
; Practical 7 : Register-reference instructions CLA, CMA, CME, HLT
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; Observe AC, E, PC, AR and IR (Decimal) after every instruction.
; ==============================================================
 LDA NUM ; set-up: AC <- 25 so that CLA has something to clear
 CLA ; 7800 : AC <- 0
 CMA ; 7200 : AC <- AC' (0000 -> FFFF = -1)
 CME ; 7100 : E <- E' (0 -> 1)
 HLT ; 7001 : S <- 1 (halt)
NUM: .data 1 25
```
## After assembling and loading the program

<img width="1793" height="865" alt="Image" src="https://github.com/user-attachments/assets/cfedc2bc-e3d4-4f48-9cd5-acc37a6dbf54" />

## After step 1:LDA NUM: AC = 25

<img width="601" height="520" alt="Image" src="https://github.com/user-attachments/assets/a8ebc29b-369a-4cbd-9887-d11f41bb9fc7" />

## After step 2:CLA: AC = 0, AR = 2048 (800 hex

<img width="583" height="547" alt="Image" src="https://github.com/user-attachments/assets/153672bc-8833-4e27-850e-a6e47d3e3939" />

## After step 3:CMA: AC = 65535 (FFFF hex = −1), AR = 512


<img width="575" height="620" alt="Image" src="https://github.com/user-attachments/assets/4e0b0f7a-43a7-4019-9a70-ef3c10e1abec" />

## After step 4:CME: E = 1, AR = 256


<img width="611" height="587" alt="Image" src="https://github.com/user-attachments/assets/d19887ed-baee-4fe8-b0c0-19fd9959db8e" />

## After step 5:HLT: S = 1, execution halted

<img width="593" height="661" alt="Image" src="https://github.com/user-attachments/assets/f7d2111a-3208-415d-8d2f-45ac8e580ab1" />

## Observation 
**Register contents (decimal) after each instruction**

| Step | PC before | Instruction | IR (hex) | AC | E | PC | AR | IR (dec) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 0 | LDA NUM | 2005 | 25 | 0 | 1 | 5 | 8197 |
| 2 | 1 | CLA | 7800 | 0 | 0 | 2 | 2048 | 30720 |
| 3 | 2 | CMA | 7200 | 65535 (-1) | 0 | 3 | 512 | 29184 |
| 4 | 3 | CME | 7100 | 65535 (-1) | 1 | 4 | 256 | 28928 |
| 5 | 4 | HLT | 7001 | 65535 (-1) | 1 | 5 | 1 | 28673 |

**Final register contents after HLT**

| Register | Decimal | Hex | Explanation |
| :--- | :--- | :--- | :--- |
| AC | 65535 (signed -1) | FFFF | CLA cleared it, CMA complemented all bits |
| E | 1 | 1 | CME complemented E from 0 to 1 |
| PC | 5 | 005 | Address after HLT (HLT is at address 4) |
| AR | 1 | 001 | IR(0–11) of HLT = 001 |
| IR | 28673 | 7001 | Code of HLT |

## Result
After execution: AC = 65535 (−1), E = 1, PC = 5, AR = 1, IR = 28673.

---

# Practical-8 Register-reference Instructions: INC, SPA, SNA, SZE

| Aim |To simulate INC, SPA, SNA and SZE and determine AC, E, PC, AR and IR in decimal after execution. |
|:---|:---:|
| Tool | CPU Sim 4.0.11 (Java 8 with JavaFX) |

## Theory
| Symbol | Code(Hex) | Micro-Operation|
|:---|:---:|:---:|
| INC | 7020 | AC<-AC+1 |
| SPA | 7010 | if AC(15) = 0 (AC positive or zero) then PC ← PC + 1 |
| SNA | 7008 | if AC(15) = 1 (AC negative) then PC ← PC + 1 |
| SZE | 7002 | if E = 0 then PC ← PC + 1 |

A skip instruction increments PC once more when its condition is true, so the next instruction is not executed. In the program every skip instruction is followed by a HLT “trap”: the program reaches its last instruction only if every skip works. AC starts at −2 so that both a negative and a non-negative value are tested.

## Program

```
; ==============================================================
; Practical 8 : Register-reference instructions INC, SPA, SNA, SZE
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; A skip instruction adds 1 to PC when its condition is true, so
; the instruction after it is NOT executed. Each HLT below is a
; "trap": the program only reaches the final HLT if every skip works.
; ==============================================================
 LDA NUM ; set-up: AC <- -2
 INC ; 7020 : AC <- AC + 1 (-2 -> -1)
 SNA ; 7008 : AC < 0 (negative) -> skip next
 HLT ; (skipped)
 INC ; 7020 : AC <- AC + 1 (-1 -> 0)
 SPA ; 7010 : AC(15) = 0 (positive) -> skip next
 HLT ; (skipped)
 SZE ; 7002 : E = 0 -> skip next
 HLT ; (skipped)
 INC ; 7020 : AC <- AC + 1 (0 -> 1)
 HLT ; 7001 : halt
NUM: .data 1 -2
```

## After Assembling and Loading:

<img width="2970" height="1440" alt="Image" src="https://github.com/user-attachments/assets/6b646a3b-ccc4-4b98-8d01-6ed0d854b505" />

## After step 1:
<img width="1024" height="805" alt="Image" src="https://github.com/user-attachments/assets/75bbdae6-fe2a-43ed-bf8b-53799c019f64" />

## After step 2:
<img width="1024" height="805" alt="Image" src="https://github.com/user-attachments/assets/edfa4bab-8820-4586-ae50-1e53edea50cd" />

## After step 3:

<img width="2176" height="1515" alt="Image" src="https://github.com/user-attachments/assets/5f122c95-4ccf-47dc-8c4b-38662f1554eb" />

## After step 4:

<img width="2133" height="1712" alt="Image" src="https://github.com/user-attachments/assets/34839b05-fe49-40a9-973a-d39490601a73" />

## After step 5:

<img width="2027" height="1578" alt="Image" src="https://github.com/user-attachments/assets/8173ab51-72da-45a9-81e7-33160268c405" />

## After step 6:

<img width="2179" height="1607" alt="Image" src="https://github.com/user-attachments/assets/fedf67ea-e776-4658-98eb-cb3e62fdc208" />

## After step 7:

<img width="2092" height="1680" alt="Image" src="https://github.com/user-attachments/assets/5265402b-52a7-40a5-a625-fb82fafa3b6c" />

## After step 8:

<img width="2016" height="1666" alt="Image" src="https://github.com/user-attachments/assets/eeb3b5b1-43b0-4f27-aa91-60ba6e814852" />

## Observation 
Register contents (decimal) after each instruction
| Step | PC before | Instruction | IR (hex) | AC | E | PC | AR | IR (dec) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 0 | LDA NUM | 200B | 65534 (-2) | 0 | 1 | 11 | 8203 |
| 2 | 1 | INC | 7020 | 65535 (-1) | 0 | 2 | 32 | 28704 |
| 3 | 2 | SNA | 7008 | 65535 (-1) | 0 | 4 | 8 | 28680 |
| 4 | 4 | INC | 7020 | 0 | 0 | 5 | 32 | 28704 |
| 5 | 5 | SPA | 7010 | 0 | 0 | 7 | 16 | 28688 |
| 6 | 7 | SZE | 7002 | 0 | 0 | 9 | 2 | 28674 |
| 7 | 9 | INC | 7020 | 1 | 0 | 10 | 32 | 28704 |
| 8 | 10 | HLT | 7001 | 1 | 0 | 11 | 1 | 28673 |

The instructions at addresses 3, 6 and 8 were never executed: the PC column goes 2 → 4, 5 → 7 and 7 → 9.

## Result
INC, SPA, SNA and SZE were simulated and every skip was verified. After execution: AC = 1, E = 0, PC = 11, AR = 1, IR = 28673.

---
# Practical-9 Register-reference Instructions: CIR, CIL

| Aim | To simulate CIR and CIL and determine AC, E, PC, AR and IR in decimal after execution. |
|:---|:---:|
| Tool | CPU Sim 4.0.11 (Java 8 with JavaFX) |

## Theory
CIR and CIL circulate (rotate) the 17-bit combination of E and AC by one position:

| CIR (7080): E -> AC(15) -> AC(14) -> ... -> AC(0) -> E (rotate right) |
|:---|
| CIL (7040): E <- AC(15) <- AC(14) <- ... <- AC(0) <- E (rotate left) |

No bit is lost, so a CIR followed by a CIL restores the original AC and E. In CPU Sim each rotation uses a 1-bit scratch register TMP: the bit leaving AC is saved in TMP, AC is shifted, the old E enters the vacated bit, and TMP is copied into E.

| E AC |
|:---|
| start 0 0000 0000 0000 1001 = 9 |
| CIR 1 0000 0000 0000 0100 = 4 (bit 0 of AC went to E) |
| CIR 0 1000 0000 0000 0010 = 32770 (old E=1 entered AC(15)) |
| CIL 1 0000 0000 0000 0100 = 4 |
| CIL 0 0000 0000 0000 1001 = 9 (original value restored) |

## Program

```
; ==============================================================
; Practical 9 : Register-reference instructions CIR, CIL
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; CIR : circulate E and AC right (E -> AC(15), AC(0) -> E)
; CIL : circulate E and AC left (AC(15) -> E, E -> AC(0))
; ==============================================================
 LDA NUM ; set-up: AC <- 9 = 0000 0000 0000 1001, E = 0
 CIR ; 7080 : AC = 0000 0000 0000 0100 (4), E = 1
 CIR ; 7080 : AC = 1000 0000 0000 0010 (-32766), E = 0
 CIL ; 7040 : AC = 0000 0000 0000 0100 (4), E = 1
 CIL ; 7040 : AC = 0000 0000 0000 1001 (9), E = 0
 HLT
NUM: .data 1 9
```

## After assembling and loading

<img width="1586" height="992" alt="Image" src="https://github.com/user-attachments/assets/914c86c9-0255-4886-94b2-285ef49b0deb" />

## After step 1:

<img width="2800" height="1504" alt="Image" src="https://github.com/user-attachments/assets/8c5d3c71-94fe-4350-8cfc-05391784ecbd" />

## After step 2:

<img width="2180" height="1952" alt="Image" src="https://github.com/user-attachments/assets/b568c604-9826-43df-8181-54874ffcbd02" />

## After step 3:

<img width="2154" height="1952" alt="Image" src="https://github.com/user-attachments/assets/eae89493-3fc6-4cc9-8535-9cdcf91cc366" />

## After step 4:

<img width="2300" height="1856" alt="Image" src="https://github.com/user-attachments/assets/38588286-4517-4c65-9baf-f34c192e3bfb" />

## After step 5:

<img width="796" height="753" alt="Image" src="https://github.com/user-attachments/assets/a5db6eee-c3bc-4a3d-9577-bc6314bfaee6" />

## After step 6:

<img width="773" height="893" alt="Image" src="https://github.com/user-attachments/assets/9405970c-7b59-4e25-842e-9b0f84ec1fba" />

## Observation
Register contents (decimal) after each instruction
| Step | PC before | Instruction | IR (hex) | AC | E | PC | AR | IR (dec) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 0 | LDA NUM | 2006 | 9 | 0 | 1 | 6 | 8198 |
| 2 | 1 | CIR | 7080 | 4 | 1 | 2 | 128 | 28800 |
| 3 | 2 | CIR | 7080 | 32770 (-32766) | 0 | 3 | 128 | 28800 |
| 4 | 3 | CIL | 7040 | 4 | 1 | 4 | 64 | 28736 |
| 5 | 4 | CIL | 7040 | 9 | 0 | 5 | 64 | 28736 |
| 6 | 5 | HLT | 7001 | 9 | 0 | 6 | 1 | 28673 |

Final register content after halt
| Register | Final value (decimal) |
|:---|:---:|
| AC | 9 |
| E | 0 |
| PC| 6 |
| AR | 1 |
| IR | 28673 (7001 hex) |

## Result
CIR and CIL were simulated; two right rotations followed by two left rotations restored AC = 9. After execution: AC = 9, E = 0, PC = 6, AR = 1, IR = 28673. After each individual instruction the values are as in the table above.

---
# Practical 10: Sum of Integers until a Negative Number is Read

| Aim | To write an assembly program that reads integers and adds them until a negative non-zero number is read, then outputs the sum (not including the last number). |
|:---|:---:|
| Tool | CPU Sim 4.0.11 (Java 8 with JavaFX) |

## Theory

This is a sentinel-controlled loop: the negative number marks the end of the data. After each INP, SPA skips the exit branch when AC ≥ 0; for a negative number the skip does not happen and BUN DONE leaves the loop before the number is added. Zero counts as non-negative, so it is added (it does not change the sum).

## Program

```
; ==============================================================
; Practical 10 : Read integers and add them until a negative
; non-zero number is read; output the sum
; (the negative number is NOT included).
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; ==============================================================
LOOP: INP ; AC <- next number
 SPA ; if AC >= 0 skip the exit branch
 BUN DONE ; AC < 0 : leave the loop
 ADD SUM ; AC <- AC + SUM
 STA SUM ; SUM <- AC
 BUN LOOP ; read the next number
DONE: LDA SUM ; AC <- SUM
 OUT ; display the sum
 HLT
SUM: .data 1 0 ; running total
```

## After Assembling and Loading the Program

<img width="1024" height="517" alt="Image" src="https://github.com/user-attachments/assets/c58417e2-556b-4522-a4d4-32572bce5b14" />

## Output after running the program and giving inputs 3, 9, 1 and finally -5

<img width="1312" height="658" alt="Image" src="https://github.com/user-attachments/assets/b6144ada-1662-4fda-862e-77c2c86ba77f" />

## Output
Sample runs (each verified in CPU Sim)
| Input(s) typed | Output displayed |
|:---|:---:|
| 3, 9, 1, -5 | 13 |
| -5 | 0 |
| 8 ,6 , -2 | 14 |

## Result
The program successfully keeps running until a negative input is given, in the case above, The program adds integers until a negative number is read and displays the sum excluding it: 3 + 9 + 1 = 13.

---
# Practical 11: Sum of Integers until Zero is Read

| Aim | To write an assembly program that reads integers and adds them until zero is read, then outputs the sum. |
|:---|:---:|
| Tool | CPU Sim 4.0.11 (Java 8 with JavaFX) |

## Theory
Here the sentinel is 0. SZA skips the next instruction when AC = 0. Because a skip can only jump over one instruction, two branches are used: when AC ≠ 0 the BUN ADDIT executes and the number is added; when AC = 0 that branch is skipped and BUN DONE ends the loop. Negative numbers are added normally.

## Program
```
; ==============================================================
; Practical 11 : Read integers and add them until zero is read;
; then output the sum.
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; ==============================================================
LOOP: INP ; AC <- next number
 SZA ; if AC != 0 do not skip ...
 BUN ADDIT ; ... so go and add it
 BUN DONE ; AC = 0 (BUN ADDIT was skipped) : finish
ADDIT: ADD SUM ; AC <- AC + SUM
 STA SUM ; SUM <- AC
 BUN LOOP ; read the next number
DONE: LDA SUM ; AC <- SUM
 OUT ; display the sum
 HLT
SUM: .data 1 0 ; running total
```

## After assembling and loading the program

<img width="1777" height="885" alt="Image" src="https://github.com/user-attachments/assets/5aa7f7e2-bc33-46ee-9677-488d397c70f6" />

## Output after running the program and giving inputs 3, 7, 2 and finally 0

<img width="1024" height="627" alt="Image" src="https://github.com/user-attachments/assets/9172cb3f-6710-4924-b7c3-57cc2d4086b2" />

## Observation 
Sample runs (each verified in CPU Sim)
| Input(s) typed | Output displayed |
|:---|:---|
| 3, 7, 2, 0 | 12 |
| 0 | 0 |
| 50, 60, 0| 110 |

## Result
The program successfully keeps running until 0 is given as input, in the case above, The program adds integers until 0 is read and displays the sum: 3 + 7 + 2 = 12.

----
# END

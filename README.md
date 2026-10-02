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
image:
# Creating a registers:
image
# Creating the condition Bits:
image
# Creating a RAM:
image
# Creating a microinstructions 
# TransferRtoR:
image
# MemomryAccess:
image
# Increment:
image
# Arithmetic:
image
# Logical:
image
# Shift:
image
# Set:
image
# Test:
image
# Decode:
image
# SetcondBit:
image
# IO:
image
# Creating the instructions:
image
# Creating the machine instructions:
image
image
# Execute sequence of ADD:
image
# Execute sequence of ISZ:
image
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
image 
## Testing the routine 
Open the P03_ADD.a file in CPUSim, press Ctrl+2 (assemble & load), then Ctrl+D (debug mode). Set 
the registers' Data selector to Unsigned Dec.

image

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

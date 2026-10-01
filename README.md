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
 


#

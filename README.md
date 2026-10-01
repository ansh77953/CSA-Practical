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

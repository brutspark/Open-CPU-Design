Copyright [2020] [Sergey Brutyan]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

/========================================================================/
		 OpenCPU design for 8-bit architecture 

 
--8-bit Open CPU Architecture
	| 
	|_Port Registers
	| |
 	| |_Port Direction Register
	| | |_
	| |   |_Port A Direction Register(PDR A)
	| |   |_Port B Direction Register(PDR B)
	| |   |_Port C Direction Register(PDR C)
	| |   |_Port D Direction Register(PDR D)
	| |
	| |_Port Data Register
	|   |_
	|     |_Port A Data Register(PORT A)
	|     |_Port B Data Register(PORT B)
	|     |_Port C Data Register(PORT C)
	|     |_Port D Data Register(PORT D)
	|
	|_Instruction Decoder
	| |_
	| | |_Input
	| |   |_CLOCK_INPUT
	| |   |_ENABLE
	| |   |_Instruction Input
	| |
	| |_
	|   |_Output
	|     |_ALU_OPCODE
	|     |_I
	|     |_Write Enable
	|     |_Working Register Select
	|     |_
	|     |_Output Register Select
	|
	|	
    	|_Working Register with 8-bit width
	| |_
	|   |_Working Register
	|
	|_Status Register
	| |_
	|   |_Status Register Flags 
	|     |_Sign, Carry, Zero, Interrupt, Overflow, 
	|
	|_ALU with 8-bit working register 
	| |_
	|   |_Arithmetic Functions
	|   | |_ADD, MUL, SUB, DIV, INC, DEC, COMP 
	|   | 
	|   |_Logical Functions	
	|     |_AND, OR, INV, XOR, BSR, BSL 
	|
	|_Interrupt Control Unit
	| |_
	|   |_Interrupt Status  Register
	|   |_Interrupt Control Register
	|   |_Interrupt Service Register
	|_
	| |_
	    

/===================================================================================/
		OpenCPU Instruction Set

Arithmetic Operations
	ADD WReg, Reg
	MUL WReg, Reg
	SUB WReg, Reg
	DIV WReg, Reg
	INC WReg, Reg
	DEC WReg, Reg
	CMP WReg, Reg

Logical Operations
	AND WReg, Reg
	OR  WReg, Reg
	INV WReg, Reg
	XOR WReg, Reg
	BSR WReg, Reg
	BSL WReg, Reg


Control Operations
	RED WReg, Reg
	LAD WReg, Reg
	JMP WReg, Reg
	RET WReg, Reg
	NOP 
	SLEEP
	INT


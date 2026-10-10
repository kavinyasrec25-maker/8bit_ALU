# OPCODE FORGE - 8-BIT COMPUTER ARCHITECTURE
# 📌 Project Overview
The 8-Bit Computer Design and FPGA Implementation on boolean board using Verilog project focuses on designing and implementing a functional, modular computer architecture using digital hardware design principles. The system integrates essential processor components, including a Control Unit, Program Counter (PC), Memory Address Register (MAR), Arithmetic Logic Unit (ALU), general-purpose registers, shared data bus, RAM, and output register, into a unified computational system.
The processor is designed to execute instructions through coordinated instruction sequencing, control signal generation, data movement, and arithmetic and logical processing. The 8-bit ALU supports six fundamental operations: addition, subtraction, bitwise AND, bitwise OR, bitwise XOR, and bitwise NOT. A modular design approach enables individual hardware components to be developed, simulated, and verified before integration into the complete processor.
The project emphasizes processor architecture, RTL design, digital system integration, and hardware verification using Verilog. Functional correctness is evaluated through simulation, followed by FPGA implementation to demonstrate the operation of the designed computer on physical hardware.


## 📑 Instruction Set Architecture (ISA)

The Instruction Set Architecture (ISA) defines the instructions supported by the 8-bit computer and the operations performed by the processor. Each instruction is represented by a 4-bit opcode, which is decoded by the Control Unit to generate the required control signals.

### Instruction Set Table

| Opcode | Instruction | Description |
|:---:|---|---|
| `0000` | LDA A | Load data from memory address A into the accumulator. |
| `0001` | LDA B | Load data from memory address B into the accumulator. |
| `0010` | ADD | Add the operands and store the result in the accumulator. |
| `0011` | SUB | Subtract the second operand from the first operand. |
| `0100` | AND | Perform a bitwise AND operation. |
| `0101` | OR | Perform a bitwise OR operation. |
| `0110` | XOR | Perform a bitwise XOR operation. |
| `0111` | NOT | Perform a bitwise NOT operation on the accumulator. |
| `1000` | STA A | Store the accumulator value at memory address A. |
| `1001` | OUT | Transfer the accumulator value to the output register. |
| `1010` | HLT | Halt further instruction execution. |

### Instruction Encoding

- **Opcode Width:** 4 bits
- **Number of Defined Instructions:** 11
- **Data Width:** 8 bits

The Control Unit decodes the opcode and coordinates the execution of the corresponding instruction through appropriate control signals.

The exact instruction encoding and operand handling depend on the implemented instruction decoder and datapath.


  ## BLOCK DIAGRAM

![8-bit Computer Block Diagram](images/Screenshot%202026-10-09%20142115.png)

 # HARDWARE MODULES
 ## 🏗️ Hardware Modules

The 8-bit computer is designed using a modular architecture in which each hardware component performs a specific function. These modules are interconnected through a shared data bus and coordinated by the Control Unit to enable instruction execution and data processing.

| S.No. | Hardware Module | Description |
|:---:|---|---|
| 1 | Control Unit | Decodes instructions and generates control signals to coordinate processor operations. |
| 2 | Program Counter (PC) | Maintains the address of the instruction to be fetched or executed next. |
| 3 | Memory Address Register (MAR) | Holds the memory address required for read or write operations. |
| 4 | Arithmetic Logic Unit (ALU) | Performs arithmetic and logical operations on 8-bit operands. |
| 5 | Registers | Temporarily store data and intermediate processing results. |
| 6 | Shared Data Bus | Provides a common data path for transferring information between processor components. |
| 7 | RAM | Stores instructions and/or data used during program execution. |
| 8 | Output Register | Holds the processed result for presentation at the processor output. |
| 9 | Clock Divider | Generates a slower clock signal for observing processor operation on FPGA hardware. |
| 10 | CPU Top Module | Integrates the individual modules into a complete computer system. |

### ALU Operations

The Arithmetic Logic Unit supports the following six operations:

| Operation | Function | Description |
|---|---|---|
| ADD | A + B | Performs binary addition. |
| SUB | A - B | Performs binary subtraction. |
| AND | A & B | Performs bitwise AND. |
| OR | A \| B | Performs bitwise OR. |
| XOR | A ^ B | Performs bitwise exclusive OR. |
| NOT A | ~A | Inverts all bits of operand A. |

Each operation is selected through the appropriate ALU control inputs generated or configured by the processor control logic.

## ⚙️ Instruction Execution

The processor follows an instruction execution process in which instructions are fetched from memory, decoded by the Control Unit, and executed using the appropriate hardware components.

### Instruction Execution Cycle

**1. Instruction Fetch**

The Program Counter (PC) provides the address of the instruction to be fetched. The address is transferred to the memory access path, and the instruction is retrieved from RAM.

**2. Instruction Decode**

The Control Unit interprets the fetched instruction and identifies the operation to be performed. Based on the instruction, it generates the necessary control signals.

**3. Operand Transfer**

The required operands are transferred between memory, registers, and the ALU through the shared data bus, according to the processor's control sequence.

**4. Instruction Execution**

The selected operation is performed by the appropriate hardware component. For arithmetic and logical instructions, the ALU processes the operands according to its control inputs.

**5. Result Storage**

The computed result is transferred to the appropriate destination, such as a register or memory location, depending on the instruction being executed.

**6. Output Generation**

When an output operation is executed, the result is transferred to the Output Register and made available at the processor output.

### Execution Flow

Instruction Fetch → Instruction Decode → Operand Transfer → Instruction Execution → Result Storage / Output

The Control Unit coordinates these operations using control signals and clock transitions. The exact sequence and number of clock cycles depend on the implemented instruction and control logic.


 of the design before FPGA implementation.

### Simulation Results

Simulation waveforms and verification screenshots will be included to demonstrate the operation of the individual modules and the integrated processor.


## ⚡ FPGA Implementation

The designed 8-bit computer is intended for implementation on an FPGA development board. The Verilog RTL design is synthesized into hardware logic and prepared for implementation using the selected FPGA design tool.

### Implementation Workflow

1. **RTL Design:** Develop the processor modules using Verilog.
2. **Functional Simulation:** Verify the logical behavior of the design using testbenches.
3. **Synthesis:** Convert the RTL description into a hardware netlist.
4. **Design Constraints:** Configure the required FPGA pin assignments and clock constraints.
5. **Implementation:** Perform placement and routing for the target FPGA device.
6. **Bitstream Generation:** Generate the programming file if supported by the selected board and toolchain.
7. **Hardware Testing:** Program the FPGA and verify the processor's operation using suitable inputs and observable outputs.

### Hardware and Software

| Component | Description |
|---|---|
| Hardware Platform | Boolean FPGA Board |
| Hardware Description Language | Verilog HDL |
| Design Tool | Xilinx Vivado Design Suite |
| Target Design | Modular 8-bit Computer |
| Implementation Method | RTL Synthesis and FPGA Implementation |

The design is developed using Verilog HDL and Xilinx Vivado to implement and verify the modular 8-bit computer. The hardware implementation demonstrates instruction sequencing, arithmetic and logical operations, memory access, and output generation on the FPGA platform.


## 📊 Results and Output

The project evaluates the functionality of the individual processor modules and their integration into a complete 8-bit computer.

### Expected Functional Outcomes

- Correct operation of the six supported ALU functions.
- Correct program counter and memory address register behavior.
- Successful RAM read and write operations.
- Appropriate control signal generation by the Control Unit.
- Correct data transfers between interconnected modules.
- Correct output generation for supported instructions.

### Demonstration and Evidence

The following results will be documented as testing progresses:

- ALU simulation waveforms.
- Program Counter and RAM verification waveforms.
- Control Unit signal transitions.
- Complete processor simulation results.
- FPGA implementation screenshots and hardware demonstration, when available.

### Performance Evaluation

The design may also be evaluated using synthesis reports, including logic resource utilization, timing results, and maximum operating frequency, where available.

The final results will be updated based on simulation evidence and actual FPGA testing.

## 🚀 Applications

- **Computer Architecture Education:** Demonstrates fundamental processor concepts, including instruction execution, memory access, and data processing.
- **Digital System Design:** Provides practical experience in designing and integrating digital hardware modules using Verilog HDL.
- **Processor Design and Verification:** Serves as a learning platform for understanding instruction decoding, control signals, and datapath operations.
- **FPGA-Based Prototyping:** Demonstrates how a processor architecture can be implemented and tested on programmable hardware.
- **VLSI Design Fundamentals:** Builds foundational knowledge of RTL design, synthesis, and hardware implementation.
- **Embedded Computing Concepts:** Helps develop an understanding of how processing units, memory, and control logic work together in computing systems.
- **Advanced Processor Development:** Serves as a starting point for exploring expanded instruction sets, interrupts, pipelining, and more advanced CPU architectures.

## 🎯 Conclusion

This project presents the design and development of a modular 8-bit computer using Verilog HDL and Xilinx Vivado Design Suite. By integrating essential processor components, including the Control Unit, Program Counter, Memory Address Register, ALU, registers, shared data bus, and RAM, the design demonstrates the fundamental principles of computer architecture and digital system design.

The implementation focuses on instruction execution, data transfer, memory operations, and six arithmetic and logical operations. Functional simulation supports verification of the individual modules and the integrated processor, while FPGA implementation provides an opportunity to demonstrate the design on physical hardware.

Overall, this project establishes a strong foundation in RTL design, processor architecture, hardware verification, and FPGA development, providing valuable practical experience for further exploration of advanced digital systems and VLSI design.



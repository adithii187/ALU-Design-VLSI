# VLSI Project: 4-Bit ALU Design and Verification

## Introduction

This project involves designing and verifying a 4-bit Arithmetic Logic Unit (ALU) capable of performing addition, subtraction, comparison, and AND operations. The ALU design will be implemented using standard cells and verified using Verilog. The critical path and maximum delay of the circuit will be estimated, and the layout will be designed using Magic.

## Project Components

### ALU Block

The ALU block functions as a router to the computational circuit, performing the following operations based on control signals $\( S_1 \)$ and $\( S_0 \)$:

- $\( S_1 S_0 \)$ Operation
  - 00: Add
  - 01: Subtract
  - 10: Compare
  - 11: AND

To implement this, a 2-to-4 decoder will be used.

### Enable Block

The Enable Block consists of 8 AND gates responsible for routing the input values $\( A_3A_2A_1A_0 \)$ and $\( B_3B_2B_1B_0 \)$ to their respective operation blocks based on the operation control signal.

### Adder/Subtractor

A single block will act as both an adder and subtractor. The adder operation is $\( A_3A_2A_1A_0 + B_3B_2B_1B_0 \)$, and the subtractor operation is $\( A_3A_2A_1A_0 - B_3B_2B_1B_0 \)$.

### Comparator

The Comparator block compares the 4-bit numbers $\( A_3A_2A_1A_0 \)$ and $\( B_3B_2B_1B_0 \)$ to determine if $\( A \)$ is greater than, less than, or equal to $\( B \)$.

### AND Block

The AND Block performs the following AND operations:
- \( A_3 \& B_3 \)
- \( A_2 \& B_2 \)
- \( A_1 \& B_1 \)
- \( A_0 \& B_0 \)

### Overall ALU Design

Combining all these blocks results in a complete 4-bit ALU capable of performing the specified operations.

## Tools Used

- **Circuit Design:** NG-SPICE
- **Layout Design:** Magic
- **Verification:** Verilog

## Project Structure

The project is structured as follows:
- `alu_block.sp`: NG-SPICE file for the ALU block.
- `add_subtract.sp`: NG-SPICE file for the adder/subtractor block.
- `comparator.sp`: NG-SPICE file for the comparator block.
- `and_block.sp`: NG-SPICE file for the AND block.
- `alu_layout.mag`: Magic layout file for the ALU design.
- `alu_testbench.v`: Verilog testbench for ALU functionality verification.
- `report.pdf`: Detailed report including pre- and post-layout results, critical path analysis, and comparison of the design with theoretical estimates.

## Usage

1. **NG-SPICE:**
   - Run simulations for each block to verify functionality.
   
2. **Magic:**
   - Design the layout of the ALU and perform layout vs schematic (LVS) checks.
   
3. **Verilog:**
   - Verify the functionality of the ALU using Verilog testbenches.

## Results and Analysis

- **Critical Path and Maximum Delay:**
  - Estimate the critical path and maximum delay of the circuit.
  
- **Pre-layout vs Post-layout Comparison:**
  - Compare the performance and functionality of the ALU before and after layout design.

## Conclusion

This project demonstrates the design, layout, and verification of a 4-bit ALU using VLSI tools. The results and analysis provide insights into the performance of the ALU and validate its functionality across various operations.

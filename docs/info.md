<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

An ALU (Arithmetic Logic Unit) is a key component in digital circuits that performs arithmetic and logical operations. In this design, we have an ALU that operates on 4-bit inputs (meaning it processes numbers in the range of 0 to 15). The ALU performs different operations depending on the opcode (a code that tells the ALU which operation to perform).


## How to test

1. Input Configuration: The 4-bit binary numbers a and b are provided via the upper and lower halves of the 8-bit input (ui_in). The upper 4 bits represent one operand (a), and the lower 4 bits represent the other operand (b).
The operation to be performed is selected using the 4-bit opcode provided via the uio_in input.

2. Running the Design: To test the adder:
*Set the input values (a and b) by configuring ui_in.
*Select the operation by setting the uio_in input to the corresponding opcode.
*Ensure the design is powered by setting ena active and release the reset signal (rst_n set to 1).
*Observe the result of the operation on the uo_out output. The exact meaning of the result will depend on the operation:
**For arithmetic operations (ADD, SUB, MUL, DIV), uo_out will show the result of the operation.
**For logical operations (AND, OR, XOR, NOT), uo_out will contain the logical result.
**For comparison operations (SLT, SEQ), the least significant bit (LSB) of uo_out will indicate the comparison result (either 0 or 1).
*Additionally, for operations like ADD and SUB, carry-out and overflow flags can be observed on the upper bits of uio_out.

3. Example Test:
ADD Operation:

Input: a = 4'b0011 (3), b = 4'b0101 (5), opcode = ADD (0b0000).
Set ui_in: ui_in = 8'b01010011.
Expected Output: Sum 8 → uo_out = 8'b00001000 (4-bit sum), uio_out[6] = 0 (carry-out).

## External hardware

No external hardware is required for this project. 

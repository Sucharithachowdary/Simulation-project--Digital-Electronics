# TITTLE:
Implement Ex nor gate using nand gate only

# THEORY:
NAND gate - It is a digital circuit that has two or more inputs and produces an output, which is the inversion of logical AND of all those inputs.

Logic NAND Gates are available using digital circuits to produce the desired logical function and is given a symbol whose shape is that of a standard AND gate with a circle, sometimes called an "inversion bubble" at its output to represent the NOT gate symbol with the logical operation of the NAND gate.

As with the AND function seen previously, the NAND function can also have any number of individual inputs and commercial available NAND Gate IC's are available in standard 2, 3, or 4 input types. If additional inputs are required, then the standard NAND gates can be cascaded together to provide more inputs.

Boolean Expression Y = (A.B)'

# LOGIC DIAGRAM:
![output](https://github.com/Sucharithachowdary/Simulation-project--Digital-Electronics/blob/main/logic%20diagram.png)

# NETLIST DIAGRAM:
![output](https://github.com/Sucharithachowdary/Simulation-project--Digital-Electronics/blob/main/draft%20rtl.png)

# TIMING DIAGRAM
![output](https://github.com/Sucharithachowdary/Simulation-project--Digital-Electronics/blob/main/timing.png)

# PROGRAM:
```
module exnor_gate(input A, input B, output Y);
  wire wire1, wire2, wire3;

 
  nand_gate nand1(.A(A), .B(B), .Y(wire1));
  nand_gate nand2(.A(A), .B(wire1), .Y(wire2));
  nand_gate nand3(.A(B), .B(wire1), .Y(wire3));
  nand_gate nand4(.A(wire2), .B(wire3), .Y(Y));
endmodule

module nand_gate(input A, input B, output Y);
  assign Y = ~(A & B);
endmodule

```
# REFERENCE:
https://github.com/Sucharithachowdary/Simulation-project--Digital-Electronics/blob/main/README.md

# Experiment--02-Implementation-of-combinational-logic
Implementation of combinational logic gates
 
## AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.
 F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D
F2=xy’z+x’y’z+w’xy+wx’y+wxy
 
 
 
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.
 
 ### using NAND gates
 NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'



## Logic Diagram
Using NOR gates NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'
![005](https://user-images.githubusercontent.com/119559871/233825546-ecfd4f5d-5871-464a-afd8-bcb586f0a14b.png)



## Procedure
1.Create a project with required entities.

2.Create a module along with respective file name.

3.Run the respective programs for the given boolean equations.

4.Run the module and get the respective RTL outputs.

5.Create university program(VWF) for getting timing diagram.

6.Give the respective inputs for timing diagram and obtain the results

## Program:
/*

Program to implement the given logic function and to verify its operations in quartus using Verilog programming.
```
Developed by: anbuselvam.A
RegisterNumber:212222240009 
USING NAND OPERATION

module fourexp(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R;
assign P = C&(~B)&(~A);
assign Q = D&(~C)&(~A);
assign R = (~C)&B&(~A);
assign F = (~P&~Q&~R);
endmodule

USING NOR OPERATION

module fourexp(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R,S;
assign P = C&(~B)&A;
assign Q = D&(~C)&A;
assign R = C&(~B)&A;
assign S = ~(P|Q|R);
assign F = ~S;
endmodule
````

*/


## Output:
## RTL
NAND combination :
![001](https://user-images.githubusercontent.com/119559871/233825654-76058aae-b2e5-457a-acb0-104d69ad2037.png)

NOR combination :
![001](https://user-images.githubusercontent.com/119559871/233825827-1ad2a45c-6fb5-49b5-92e1-4537668cd516.png)



## Timing Diagram
NAND combination:
![005](https://user-images.githubusercontent.com/119559871/233825763-b3895d88-560a-4ad9-97f0-cd6188498cbb.png)

NOR combination :
![004](https://user-images.githubusercontent.com/119559871/233825796-df1665a0-90c3-4d2d-98b5-0b5a51b486d0.png)




## Result:
Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.

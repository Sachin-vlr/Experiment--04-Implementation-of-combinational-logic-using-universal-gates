# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure
## Program:
```
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: SACHIN C
RegisterNumber: 22001187 

PROGRAM 1

module expfour(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3;
assign f1 = (~c&~b&~a);
assign f2 = (~d&~c&~a);
assign f3 = (c&~(~b)&~a);
assign f= f1&~f2&~f3;
end module

PROGRAM 2

module expfourtwo(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(f,f4);
endmodule
```

## RTL realization

## Output:
![OP1](https://user-images.githubusercontent.com/113497666/211578713-381c0bf4-28eb-4ccc-aa79-5954273f58e6.png)

![OP2](https://user-images.githubusercontent.com/113497666/211578755-540a70df-97b4-4a7f-81cf-405c6de7d583.png)

##TRUTH TABLE

![TABLE1](https://user-images.githubusercontent.com/113497666/211578984-65c81b5a-e6db-45b3-baf3-c51558b11df6.png)

![TABLE2](https://user-images.githubusercontent.com/113497666/211579028-528b222a-5269-4206-afd2-cdac7a349ceb.png)

## RTL
##Timing Diagram

![TIME1](https://user-images.githubusercontent.com/113497666/211579088-e7024113-fd96-45a5-8fe0-27365093cc71.png)

![TIME2](https://user-images.githubusercontent.com/113497666/211579109-b54b7b89-8fd9-4c5f-a1f0-102bf0241c35.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.

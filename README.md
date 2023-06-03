# Experiment--04-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Program:

HALF SUBTRACTOR

module halfsubtractor(a,b,difference,borrow);
input a,b; 
output difference,borrow;
wire x;
xor(difference,a,b);
not(x,a);
and(borrow,x,b);
endmodule

FULL SUBTRACTOR

module fullsubtractor(A,B,C,Difference,Borrow);
input A,B,C;
output Difference,Borrow;
wire p;
assign Difference=((A^B)^C);
not(p,A);
assign Borrow=((p&B)|(p&C)|(B&C));
endmodule

Developed by: A.DIVYA
RegisterNumber: 212222230034
*/

## Output:

## Truthtable

HALF SUBTRACTOR
![hs tt](https://github.com/Divya110205/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119404855/97bab000-d85b-487b-84bb-9704b4e98f50)

FULL SUBTRACTOR
![fs tt](https://github.com/Divya110205/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119404855/56bdfc90-0cd7-4fca-a3e7-9159fd96d3f1)

##  RTL realization

HALF SUBTRACTOR
![hs rtl](https://github.com/Divya110205/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119404855/72b49c4e-d5bb-471f-896d-29180d7cea81)

FULL SUBTRACTOR
![fs rtl](https://github.com/Divya110205/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119404855/b6cd67de-571d-40ac-87a8-d176c0bc6478)

## Timing diagram 

HALF SUBTRACTOR
![hs td](https://github.com/Divya110205/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119404855/f00d0d52-716c-4b72-8c33-cb8c74a18c94)

FULL SUBTRACTOR
![fs td](https://github.com/Divya110205/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119404855/fc0338d3-4b41-4242-b711-bf0d3963ecd8)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.

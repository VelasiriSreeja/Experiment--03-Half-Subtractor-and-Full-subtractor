# Experiment--03-Half-Subtractor-and-Full-subtractor
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

## Procedure
Connect the supply (+5V) to the circuit 
Switch ON the main switch 
If the output is 1,then the led glows.



## Program:
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: v.sreeja
RegisterNumber:  212222230169
*/
module half_sub(a,b,diff,b_out);
input a,b;
wire d;
output diff,b_out;
xor (diff,a,b);
not (d,a);
and (b_out,d,b);
endmodule
2.For FULL SUBTRACTOR:
module full_sub(b_out,diff,a,b,c_in);
output b_out,diff;
input a,b,c_in;
wire w1,w4,w5,w6;
xor (diff,a,b,c_in);
not (w1,a);
and (w4,w1,b);
and (w5,w1,c_in);
and (w6,b,c_in);
or (b_out,w4,w5,w6);
endmodule
## Output:

## Truthtable
![Screenshot (367)](https://github.com/VelasiriSreeja/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118344328/ebcfec14-cb13-4099-849b-a72d238574ff)
![Screenshot (368)](https://github.com/VelasiriSreeja/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118344328/1ea87286-89c2-4851-aab0-87efd8c4c24e)



##  RTL realization
![Screenshot (369)](https://github.com/VelasiriSreeja/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118344328/21acdb99-b34d-4034-9840-95d8a5535794)
![Screenshot (370)](https://github.com/VelasiriSreeja/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118344328/0564305c-0cc7-4b52-ae7d-ad61e5c42c0b)


## Timing diagram 
![Screenshot (371)](https://github.com/VelasiriSreeja/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118344328/29373cab-e318-46a7-b18b-077bb2ac14ac)
![Screenshot (372)](https://github.com/VelasiriSreeja/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118344328/bb39aded-7fef-4c0d-bec2-4c16c7978d98)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.

# VLSI-LAB-EXPERIMENTS
AIM: 

     To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED:

      Xilinx 14.7 Spartan6 FPGA

PROCEDURE: 

STEP:1 Start the Xilinx navigator, Select and Name the New project. 

STEP:2 Select the device family, device, package and speed. 

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 

STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. 

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. 

STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. 

STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 

STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. 

STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. 

STEP:11 Load the Bit file into the SPARTAN 6 FPGA 

STEP:12 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram :

Logic Gates:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/dcdeae7b-ba01-4c7a-b956-680bcc4be741)


Half Adder:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/40db50f2-53d7-4f8d-ba19-59c0021ba9a9)



Full adder:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/824dfb16-eb16-4b6f-a7de-b0b2b6ad69da)


Half Subtractor:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/25874dfe-9846-4850-9afa-1edbc5ae19d2)




Full Subtractor:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/24f36901-50d0-47a0-bc48-2f5e3116cf9c)



8 Bit Ripple Carry Adder

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/9afd081f-1318-405f-a637-92b0dea03664)



VERILOG CODE:

module logic(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate );

input a,b;

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b);

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(notgate,a);

endmodule

HALF ADDER:

module HalfAdder(a,b,sum,carry);

input a,b;

output sum,carry;

xor (sum,a,b);

and (carry,a,b);

endmodule

FULL ADDER:

module FA(a,b,cin,sum,cout);

input a,b,cin;

output sum,cout;

wire w1,w2,w3;

xor g1(w1,a,b);

and g2(w2,w1,cin);

and g3(w3,a,b);

xor g4(sum,w1,cin);

or g5(cout,w2,w3);

endmodule

HALF SUBTRACTOR:

module halfsubtractor(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor g1(diff,a,b);

and g2(borrow,~a,b);

endmodule

FULL SUBTRACTOR:

module full_sub(a,b,bin,diff,borrow);

input a,b,bin;

output diff,borrow;

wire w1,w2,w3;

xor g1(w1,a,bin);

and g2(w2,~a,b);

xor g3(diff,w1,bin);

or g4(borrow,w2,w3);

and g5(w3,~w1,bin);

endmodule

8 BIT RIPPLE CARRY ADDER:

module fa(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

assign sum = a^b^c;

assign carry=(a&b)|(b&c)|(c&a);

endmodule

module rca(a,b,cin,sum,cout);

input [7:0]a,b;

input cin;

output [7:0]sum;

output cout;

wire c1,c2,c3,c4,c5,c6,c7;

fa fa1(a[0],b[0],cin,sum[0],c1);

fa fa2(a[1],b[1],c1,sum[1],c2);

fa fa3(a[2],b[2],c2,sum[2],c3);

fa fa4(a[3],b[3],c3,sum[3],c4);

fa fa5(a[4],b[4],c4,sum[4],c5);

fa fa6(a[5],b[5],c5,sum[5],c6);

fa fa7(a[6],b[6],c6,sum[6],c7);

fa fa8(a[7],b[7],c7,sum[7],cout);

endmodule


OUTPUT:

LOGIC GATES:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/8fb34f9f-88a6-41df-bed2-1783407ce1db)

HALF ADDER:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/98803fea-5192-4e8b-b702-dccfa145be6e)

FULL ADDER:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/324c73a7-fa48-40af-9b8f-aefef8787e9f)

HALF SUBTRACTOR:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/6931e9e9-09fb-4a9a-b571-1056d177b308)

FULL SUBTRACTOR:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/a6c3e79c-8728-4fc2-b992-709510f9ca3b)

8 BIT RIPPLE CARRY ADDER:

![image](https://github.com/Yashwanthmeesala123/VLSI-LAB-EXP-1/assets/170095637/101a586b-c757-4348-bed1-87abd9e64678)


RESULT:

     Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .


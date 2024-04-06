SIMULATION AND IMPLEMENTATION OF MULTIPLIER
**AIM: **
 To simulate and synthesis multiplier using Xilinx ISE.

**APPARATUS REQUIRED:**
Xilinx 14.7
Spartan6 FPGA
  
**PROCEDURE:**
STEP:1  Start  the Xilinx navigator, Select and Name the New project.
STEP:2  Select the device family, device, package and speed.       
STEP:3  Select new source in the New Project and select Verilog Module as the Source type.                       
STEP:4  Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5  Select the Behavioral Simulation in the Source Window and click the check syntax.                       
STEP:6  Click the simulation to simulate the program and  give the inputs and verify the outputs as per the truth table.               
STEP:7  Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8  Select Check Syntax from the Synthesize  XST Process. Double Click in the  FloorplanArea/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9  In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11  On the board, by giving required input, the LEDs starts to glow light, indicating the output.

**Logic Diagram**
2 bit Multiplier

![image](https://github.com/navaneethans/VLSI-LAB-EXP-3/assets/6987778/7713750f-65e6-41c0-8082-5005eac4031c)

**4 Bit Multiplier**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-3/assets/6987778/d95215dd-8cf1-4e08-93cc-96adfdd7fbdc)

# 2 BIT MULTIPLIER
VERILOG CODE:
~~~
module multiplier2by2(C,A,B);
input [1:0]A,B;
output [3:0]C;
wire w1,w2,w3,w4;
and (C[0],A[0],B[0]);
and (w1,A[0],B[1]);
and (w2,A[1],B[0]);
and (w3,A[1],B[1]);
halfadder ha1(C[1],w4,w1,w2);
halfadder ha2(C[2],C[3],w3,w4);
endmodule
module halfadder(sum,carry,a,b);
input a,b;
output sum,carry;
xor(sum,a,b);
and(carry,a,b);
endmodule
~~~
OUTPUT WAVEFORM:

<img width="962" alt="2024-04-06 (19)" src="https://github.com/21004601/VLSI-LAB-EXP-3/assets/146088220/6404113e-50ff-498e-a336-05b11de79c21">
<img width="962" alt="2024-04-06 (21)" src="https://github.com/21004601/VLSI-LAB-EXP-3/assets/146088220/b656a0ee-7472-4578-9f1b-7852c8259253">

# 4 BIT MULTIPLIER

VERILOG CODE:
~~~
module multiplier_4bit(
input [3:0] a, b,
output [7:0] result
);
assign result = a * b;
endmodule
~~~

OUTPUT:

<img width="962" alt="2024-04-06 (20)" src="https://github.com/21004601/VLSI-LAB-EXP-3/assets/146088220/17b19d13-73f8-43a1-bf72-6860046a27dc">
<img width="962" alt="2024-04-06 (22)" src="https://github.com/21004601/VLSI-LAB-EXP-3/assets/146088220/26593063-e67a-4323-b83d-9c1150cf861b">

RESULT:
THUS THE SIMULATION AND IMPLEMENTATION OF MULTIPLIER IS DONE BY USING VERILOG CODE AND OUTPUT VERIFIED SUCCESSFULLY.










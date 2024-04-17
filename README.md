# SIMULATION AND IMPLEMENTATION OF MULTIPLIER

# AIM:
 To simulate and synthesis multiplier using Xilinx ISE.

# APPARATUS REQUIRED:
 VIVADO 2023.1
  
# PROCEDURE:
1. Open Vivado: Launch Xilinx Vivado software on your computer.

2. Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

3. Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

4. Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

5. Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

6. Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

7. Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

8. Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

9. View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design

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










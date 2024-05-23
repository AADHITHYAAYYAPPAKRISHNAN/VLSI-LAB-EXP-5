**5.SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE**

**AIM:**

To simulate and synthesis finite state machine using Vivado 2023.3

**APPARATUS REQUIRED:**

Vivado 2023.3 

**PROCEDURE:**

STEP:1 Start the Vivado, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

**FINITE STATE MACHINE:**

**LOGIC DIAGRAM:**

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)

**VERILOG CODE:**

```
module fsm( clk, rst, inp, outp);
input clk, rst, inp;
output outp;
reg [1:0] state;
reg outp;
always @(posedge clk, posedge rst)
begin
if(rst)
state<=2'b00;
else
begin
case(state)
2'b00:
begin
if(inp) state <=2'b01;
else state <=2'b10;
end
2'b01:
begin
if (inp) state <=2'b11;
else state<=2'b10;
end
2'b10:
begin
if (inp) state<=2'b01;
else state <=2'b11;
end
2'b11:
begin
if (inp) state <=2'b01;
else state <=2'b10;
end
endcase
end
end
always @(posedge clk, posedge rst)
begin
if(rst)
outp <= 0;
else if(state == 2'b11)
outp <= 1;
else outp<= 0;
end
endmodule
```

**OUTPUT:**
![image](https://github.com/AADHITHYAAYYAPPAKRISHNAN/VLSI-LAB-EXP-5/assets/159053561/23ddc5c7-08a4-4cf7-b6ea-200eabf1956c)


**RESULT:**

Hence the finite state machine has been simulated and synthesised using Vivado 2023.2

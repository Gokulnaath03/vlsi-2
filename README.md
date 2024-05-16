# vlsi-2
# SIMULATE AND SYNTHESIS ENCODER,DECODER,MULTIPLEXER,DEMULTIPLEXER,MAGNITUDE COMPARATOR USING VIVADO.

## AIM:
To simulate and synthesis ENCODER, DECODER, MULTIPLEXER,
DEMULTIPLEXER, MAGNITUDE COMPARATOR using VIVADO.


 ## APPARATUS REQUIRED: 
 VIVADO 2023.2


 ## PROCEDURE:
STEP:1 Start the Vivado, Select and Name the New project.
STEP:2 Select the device family, device, package and speed.
STEP:3 Select new source in the New Project and select Verilog Module
as the Source type.
STEP:4 Type the File Name and Click Next and then finish button. Type
the code and save it.
STEP:5 Select the Behavioural Simulation in the Source Window and
click the check syntax.
STEP:6 Click the simulation to simulate the program and give the inputs
and verify the outputs as per the truth table.


## ENCODER 8:3:

![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/05ff5bc8-333d-44da-8710-93a249edaf79)



## PROGRAM:
 module encoder (d, a0, a1, a2);<br>
 input [7:0] d;<br>
 output a0, a1, a2;<br>
 assign a2=d[7] |d[6] |d[5] |d[4];<br>
 assign a1=d[7] |d[6] |d[3] |d[2];<br>
 assign a0=d[7] |d[5] |d[3] |d[1];<br>
 endmodule


## OUTPUT:

![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/39e461d2-021a-4331-a00c-f621c2b5d2e6)


## DECORDER 3:8:

![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/10e45252-7c64-4fb1-82b9-0e389a6ff81b)



## PROGRAM:
module decoder (s, y);
input [2:0] s;
output [7:0] y;
assign y[0]=~s[2] & ~s[1] & ~s[0];
assign y[1]=~s[2] &~s[1] & s[0];
assign y[2]=~s[2] & s[1] &~s[0];
assign y[3]=~s[2] & s[1] & s[0];
assign y[4]=s[2] & ~s[1] & ~s[0];
assign y[5]=s[2] & ~s[1] & s[0];
assign y[6]=s[2] & s[1] & ~s[0];
assign y[7]=s[2] & s[1] & s[0];
endmodule


## OUTPUT:

![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/625db202-8ec3-4854-a8c0-866bc7def091)



## MULTIPLEXER 8:1:


![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/1aad5a53-cd6b-4b29-beb2-1ee33ea376e7)



## PROGRAM:
module Mux_8_1(s0,s1,s2,i,y);
input [7:0] i;
input s0, s1, s2;
output y;
wire [7:0] w;
assign w[0]=(~s2) & (~s1) & (~s0) & i[0];
assign w[1]=(~s2) &(~s1) &(s0) & i[1];
assign w[2]=(~s2) &(s1) &(~s0) & i[2];
assign w[3]=(~s2) &(s1) &(s0) & i[3];
assign w[4]=(s2) &(~s1) &(~s0) & i[4];
assign w[5]=(s2) &(~s1) &(s0) & i[5];
assign w[6]=(s2) &(s1) &(~s0) & i[6];
assign w[7]=(s2) &(s1) &(s0) & i[7];
assign y=w[0] |w[1] |w[2] |w[3] |w[4] |w[5] |w[6] |w[7];
endmodule


## OUTPUT:

![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/901d55a8-95ed-4925-9a30-436629c33519)



## DEMULTIPLEXER 1:8:

![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/f8462642-e086-4031-9a6b-9253e05332d7)



## PROGRAM:
module Demux1_8(i, s0, s1, s2, y);
input i;
input s0, s1, s2;
output [7:0] y;
assign y[0]=~s0 &~s1 &~s2 & i;
assign y[1]=~s0 &~s1 &s2 & i;
assign y[2]=~s0 &s1 &~s2 & i;
assign y[3]=~s0 &s1 &s2 & i;
assign y[4]=s0 & ~s1 & ~s2 & i;
assign y[5]=s0 & ~s1 & s2 & i;
assign y[6]=s0 & s1 & ~s2 & i;
assign y[7]=s0 & s1 &s2 & i;
endmodule

## OUTPUT:


![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/73c224a7-e56c-4864-b819-860e6133571f)


## MAGNITUDE COMPARATOR:

![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/bf05f183-62b4-4033-82c5-b90991cb9574)



## PROGRAM:
module mag_cmp(a,b,l,g,e);<br>
input [3:0]a,b;<br>
output reg l,g,e;<br>
always @(*)<br>
begin
if(a>b)
begin
l=1'b0;
g=1'b1;
e=1'b0;
end
else if(a<b)
begin
l=1'b1;
g=1'b0;
e=1'b0;
end
else
begin
l=1'b0;
g=1'b0;
e=1'b1;
end
end
 endmodule


## OUTPUT:

![image](https://github.com/Gokulnaath03/vlsi-2/assets/167178811/de93518e-2703-4a66-b9bd-360405d62f96)



## RESULT:
 The simulate and synthesis ENCODER,DECODER,MULTIPLEXER,DEMULTIPLEXER,MAGNITUDE COMPARATOR using VIVADO is successfully verified.

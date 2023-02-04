# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
Step 1: Module Declaration. Module is a keywords defined in Verilog.
Step 2: Input-Output Declaration. Clock and reset are the inputs.
Step 3: Declare the always keyword.
Step 4: Use if loop for the functionality.
Step 5: Assign the counter_up & counter_down.
Step 6: End the module


### PROGRAM 
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: HARISH RAGAV S
RegisterNumber:  22008415
*/
## UP COUNTER
module uc(input CLK,input reset,output[0:3]counter);
reg[0:3] counter_up;
always@(posedge CLK or posedge reset)
begin
if(reset)
counter_up<=4'd0;
else
counter_up<=counter_up+4'd1;
end
assign counter=counter_up;
endmodule

## DOWN COUNTER
module dc(input CLK,input reset,output[0:3]counter);
reg[0:3] counter_down;
always@(posedge CLK or posedge reset)
begin
if(reset)
counter_down<=4'd0;
else
counter_down<=counter_down-4'd1;
end
assign counter=counter_down;
endmodule!



### RTL LOGIC UP COUNTER AND DOWN COUNTER  

UP COUNTER 
![h](https://user-images.githubusercontent.com/119345345/216765420-98cc2300-3d4e-436f-ab48-96544980752e.png)

DOWN COUNTER 
![214601422-7faa3ad5-6d9a-4fb2-b431-0390e967ba32](https://user-images.githubusercontent.com/119345345/216765517-bcd67c42-153b-4abd-bd3f-bbe83aafdbd7.png)



### TIMING DIGRAMS FOR COUNTER  

UP COUNTER 
![214601726-6c47d545-fee5-4227-ab5a-258c24d9046e](https://user-images.githubusercontent.com/119345345/216765458-23a1ea3f-852c-4c5c-9490-6b97e981bc7b.png)


DOWN COUNTER 
![214601817-c499a683-b864-4fac-a834-03584742a1c3](https://user-images.githubusercontent.com/119345345/216765464-f1f25a77-3aaf-49a4-9e31-3f9211522e2b.png)


### TRUTH TABLE
UP COUNTER
![214601971-fe5502f7-cff4-4205-8b7d-6d92f314c2c1](https://user-images.githubusercontent.com/119345345/216765533-0e9b8cb0-a6c9-42b0-9caf-441769d1e930.png)

DOWN COUNTER
![down](https://user-images.githubusercontent.com/119345345/216765899-94f4e29e-4b06-484e-a5ca-1660b412431c.png)

 

### RESULTS 
Thus, 4 bit up and down counters are implemented and its functionality is validated successfully


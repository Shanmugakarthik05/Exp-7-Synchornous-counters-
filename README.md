# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 3 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 3 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

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

 
 

Three-bit “Up” Counter



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 3-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.



3-bit Count Down Counter
### Procedure
/* write all the steps invloved */
1.Create a new project in QuartusII software.
2.Name the project as uc for upcounter and dc for down counter.
3.Create a new verilog hdl file in the project file.
4.Name the module as dc and uc for down counter and up counter.
5.Within the module declare input and output variables.
6.Create a loop using if-else with condition parameter as reset value.
7.End the loop.
8.End the module.


### PROGRAM 
/*
UP counter:
module upcounter(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=(q1&q2)^q3;
q2=q1^q2;
q1=1^q1;
end
endmodule

Down counter:
module downcounter(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=((~q2)&(~q1))^q3;
q2=(~q1)^q2;
q1=1^q1;
end
endmodule


Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: SHANMUGAKARTHIK G
RegisterNumber: 212223220105 
*/






### RTL LOGIC UP COUNTER AND DOWN COUNTER  
UP counter:

![IMG-20231227-WA0012](https://github.com/Shanmugakarthik05/Exp-7-Synchornous-counters-/assets/149762972/eada980b-df75-4a4b-9f2f-43c094e353c1)

Down Counter:

![IMG-20231227-WA0013](https://github.com/Shanmugakarthik05/Exp-7-Synchornous-counters-/assets/149762972/16437abe-eae3-4e39-aa27-483b55b3595a)


### TIMING DIGRAMS FOR COUNTER  

UP counter:

![IMG-20231227-WA0016](https://github.com/Shanmugakarthik05/Exp-7-Synchornous-counters-/assets/149762972/884297ae-6daa-437b-8f81-eb64e4ccf959)



Down counter:

![IMG-20231227-WA0017](https://github.com/Shanmugakarthik05/Exp-7-Synchornous-counters-/assets/149762972/a3a6c4c8-51cd-4c51-ab1c-89db10ad9a56)



### TRUTH TABLE 

UP counter:

![IMG-20231227-WA0014 (2)](https://github.com/Shanmugakarthik05/Exp-7-Synchornous-counters-/assets/149762972/c966521a-d856-4b17-9511-301f62aa9e70)


Down counter:

![IMG-20231227-WA0014 (3)](https://github.com/Shanmugakarthik05/Exp-7-Synchornous-counters-/assets/149762972/44117a37-7b0b-419a-927a-ae57f2dd4d0b)



### RESULTS 
Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.

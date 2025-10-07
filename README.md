### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**PROGRAM**

module pg3(out,clk,rst);

input clk,rst;

output reg [3:0]out;

always @ (posedge clk)

begin

   if(rst)
   
      out<=0;
     
   else
   
      out <= out+1;
     
end

endmodule

**RTL LOGIC UP COUNTER**
<img width="824" height="612" alt="{71523208-3DC6-44D3-B7B7-4C0F157148F4}" src="https://github.com/user-attachments/assets/d4e43162-1a2f-4a54-bc69-8b9d1edff04b" />

**TIMING DIAGRAM FOR IP COUNTER**
<img width="1415" height="352" alt="{AC01651C-6535-4CE8-8119-9C335E815993}" src="https://github.com/user-attachments/assets/44d9a499-15aa-4b12-a67a-f2b97f304245" />

**TRUTH TABLE**
<img width="392" height="495" alt="{A3A07F8F-5FE9-4B60-B3B9-D6381FAE94B1}" src="https://github.com/user-attachments/assets/c2c90288-4ae2-46fd-b2ea-d1943108f7fa" />

**RESULTS**
thus a 4 bit synchronous up counter is implemented and its functionality is validated

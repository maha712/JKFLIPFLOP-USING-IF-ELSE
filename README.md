# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**PROGRAM**
```


 
 
module JK(q, qb,j,k,clock,reset);
    input j,k,clock,reset;
    output reg q, qb;
	 
always @ (posedge (clock))

    begin 
        if (!reset)
            begin
               q <= q;
               qb <=qb;
            end   
        
else
   begin
	   if(j==0 && k==0)
		   begin
			q<=q;
			qb<=qb;
			end
		else if(j!=k)
		   begin
			q<=j;
			qb<=k;
			end
		else if(j==1 && k==1)
		    begin
			 q<=~q;
			 qb<=~qb;
			 end
	end
end	
endmodule
```

**RTL LOGIC FOR FLIPFLOPS**

![445880103-04cd2b07-3eaf-4118-b3d5-b9fb3c2e0f93](https://github.com/user-attachments/assets/7bc51d27-bab1-4cd8-8daf-ac8887d2f98f)

**TIMING DIGRAMS FOR FLIP FLOPS**

![445880155-5f67ba23-e444-4953-a8b3-3bdb556a2ccd](https://github.com/user-attachments/assets/ae303bde-17a5-4b66-a28f-66797ab7a92a)

**RESULTS**

Implement JK flipflop using verilog and validating their functionality using their functional table are verified in Quartus II using verilog programming.

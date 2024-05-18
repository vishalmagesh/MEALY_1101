# MEALY_1101
![image](https://github.com/RESMIRNAIR/MEALY_1101/assets/154305926/fce7c9dc-e0df-4528-843b-559bf24f018a)
# PROGRAM:
```
module mealy_1101(

input x,clk,reset, 

output reg z

);

parameter S0=2'b00, S1=2'b01, S2=2'b10, S3=2'b11;

reg [1:0] PS,NS;

always@(posedge clk or posedge reset)

begin

if(reset)

PS <= S0;

else

PS <= NS;

end

always@(PS or x)

begin

case(PS)

S0: begin 

    z=0;
    
    NS=x?S1: S0;
    
    $display(PS);

end

S1: begin

     z=0;
     
     NS=x?S2: S0;
     
     $display(PS);

end

S2: begin

     z=0;
     
     NS=x?S2: S3; 
     
     $display(PS);

end

S3: begin

    z=x ? 1:0;
    
    NS = x ? S1:S0;
    
    $diaplay(PS);

end

endcase

end

endmodule
```
# OUTPUT:
![image](https://github.com/RESMIRNAIR/MEALY_1101/assets/160302888/fd6821ae-66d9-46bb-8be1-b3b2b3c8c782)
# Result:
Thus the verilog program for MEALY Sequence Detecor for 1101 has been simulated and verified successfully.

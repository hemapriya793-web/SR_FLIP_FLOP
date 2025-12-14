# SR_FLIP_FLOP

AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED: Quartus prime

THEORY

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

<img width="725" height="415" alt="1" src="https://github.com/user-attachments/assets/ab385f85-6737-446e-a4da-9e3ac7d33b8d" />

This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

<img width="703" height="388" alt="2" src="https://github.com/user-attachments/assets/fc85f543-c264-40df-b844-d9afb5ab1731" />

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

<img width="617" height="523" alt="3" src="https://github.com/user-attachments/assets/82fd1266-a379-418a-a080-f650bc231c83" />

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

<img width="342" height="263" alt="4" src="https://github.com/user-attachments/assets/7dfcb910-86cf-47fc-9a08-750a29a49158" />

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

PROGRAM:
 ```
module sr_flip_flop (
    input  wire clk, rst, S, R,
    output reg  Q
);
    always @(posedge clk) begin
        if (rst)
            Q <= 1'b0;         // Reset
        else begin
            case ({S,R})
                2'b00: Q <= Q;     // No change
                2'b01: Q <= 1'b0;  // Reset
                2'b10: Q <= 1'b1;  // Set
                2'b11: Q <= 1'bx;  // Invalid
            endcase
        end
    end
endmodule

```

RTL LOGIC FOR FLIPFLOP:
[EX 06 Dia.pdf](https://github.com/user-attachments/files/24148954/EX.06.Dia.pdf)

wave form sr flip flop : 
<img width="1179" height="771" alt="WAVE" src="https://github.com/user-attachments/assets/05b753b1-97ab-4273-b05c-fb9d65e10100" />

NAME: HEMA PRIYA

REF NO: 25017270

RESULT: Thus the SR flipflop is implemented and verified.

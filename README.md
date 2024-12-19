# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**

/* write all the steps invloved */

**PROGRAM**
module siso_shift_register (
    input clk,    // Clock signal
    input reset,  // Active-high reset
    input si,     // Serial input
    output reg so // Serial output
);
    reg [3:0] shift_reg; // Fixed 4-bit shift register
    always @(posedge clk or posedge reset) begin
        if (reset) begin
            shift_reg <= 4'b0000; // Reset all bits to 0
            so <= 0;             // Reset serial output to 0
        end
        else begin
            so <= shift_reg[3];               // Serial output is the MSB
            shift_reg <= {shift_reg[2:0], si}; // Shift left and add new bit
        end
    end
endmodule


/* Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: KEERTHANA R RegisterNumber:24900170

*/

**RTL LOGIC FOR SISO Shift Register**
![WhatsApp Image 2024-12-19 at 19 39 34_cf5e9b97](https://github.com/user-attachments/assets/db7b66e2-4bd2-4fe0-b96f-71c638fcd5a8)

**TIMING DIGRAMS FOR SISO Shift Register**
![WhatsApp Image 2024-12-19 at 19 39 34_47e1acfd](https://github.com/user-attachments/assets/ea6982f5-a6ff-40e0-b8a1-9095e86db692)

**RESULTS**
Thus,To implement  SISO Shift Register using verilog and validating their functionality using their functional tables is done.

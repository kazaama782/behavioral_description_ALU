# behavioral_description_ALU

`timescale 1ns / 1ps

module ALU(Z,X,Y,sign,zero,carry,parity,overflow);
input [15:0]X;
input [15:0]Y;
output [15:0]Z;
output sign,zero,carry,parity,overflow;
assign {carry,Z}=X+Y;
assign sign =Z[15];
assign zero =~|Z;
assign parity = ~^Z;
assign overflow = (X[15]&Y[15]&~Z[15])|(~X[15]&~Y[15]&Z[15]);
endmodule

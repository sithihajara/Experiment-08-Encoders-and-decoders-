# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 
## PROCEDURE:
### Step 1:
Open Quartus II and select new project and choose the file location.

### Step 2:
Module Declaration. Module should have the file name.

### Step 3:
Input-Output Delecaration.

### Step 4:
Use assign to define the functionality of logic circuits.

### Step 5:
At the end give endmodule.

### Step 6:
Run the program and choose RTL viewer to get RTL realization.

## PROGRAM:
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: Sithi hajara I
RegisterNumber: 212221230102
```
### Encoder
```
module Encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
### Decoder
```
module Decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```
# OUTPUT:
## ENCODER:
### RTL LOGIC
![encoderrtl](https://user-images.githubusercontent.com/94219582/171814886-893f71b1-5314-4f6e-b9dc-9445e30708ab.png)
## TIMING DIGRAMS
<img width="356" alt="encoderwf" src="https://user-images.githubusercontent.com/94219582/171814910-3a4f019b-8410-4378-9b5c-2a5a5b34ccb5.png">
## TRUTH TABLE
![171645891-e4f37212-36aa-40b9-88c3-7f48a221f15e](https://user-images.githubusercontent.com/94219582/171814969-4f4a5551-4da1-4378-b92a-a303c153c98c.png)
### encoder truth
## DECODER:
### RTL LOGIC
![decoderrtl](https://user-images.githubusercontent.com/94219582/171814987-69e3cf09-6b74-465f-8a29-809622c12c52.png)
## TIMING DIGRAMS
<img width="1262" alt="decoderwf" src="https://user-images.githubusercontent.com/94219582/171815028-f08f25ae-c98d-4bdd-8206-5d370811e2bf.png">
### TRUTH TABLE
![decodertt](https://user-images.githubusercontent.com/94219582/171815046-4bb3d485-f37b-4e1a-9297-45a843018fef.jpg)
## RESULT:
Thus, 8 to 3 Encoder and 3 to 8 Decoder is implemented using verilog and its outputs is validated.

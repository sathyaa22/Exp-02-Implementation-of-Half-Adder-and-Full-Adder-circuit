[11:46 AM, 7/25/2023] Nijeesh SEC: # Experiment-02 Implementation of combinational logic

### Name: Sathyaa R
### RegisterNumber: 23000714

Implementation of combinational logic gates
 
## AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.
F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D

 

 
#### Equipments Required: Hardware – PCs, Cyclone II , USB flasher
#### Software – Quartus prime


## Theory
 A combinational circuit is a circuit in which the output depends on the present combination of inputs. Combinational circuits are made up of logic gates. The output of each logic gate is determined by its logic function. Combinational circuits can be made using various logic gates, such as AND gates, OR gates, and NOT gates.


## Procedure:
1. Create a New Project:
   - Open Quartus and create a new project by selecting "File" > "New Project Wizard."
   - Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).

2. Create a New Design File:
   - Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
   - Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.

3. Write the Combinational Logic Code:
   - Open the newly created Verilog or VHDL file and write the code for your combinational logic.
     
4. Compile the Project:
   - To compile the project, click on "Processing" > "Start Compilation" in the menu.
   - Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.

5. Analyze and Fix Errors:
   - If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
   - Review and fix any issues in your code if necessary.
   - View the RTL diagram.

6. Verification:
   - Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".
   - Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
   - Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.
## Program:

Program to implement the given logic function and to verify its operations in quartus using Verilog programming.

module combinationalcircuit(f1,a,b,c,d);

input a,b,c,d;

output f1;

wire abar,bbar,cbar,dbar,x1,x2,x3,x4,x5;

assign abar=~a;

assign bbar=~b;

assign cbar=~c;

assign dbar=~d;

assign x1=abar&bbar&cbar&dbar;

assign x2=a&cbar&dbar;

assign x3=bbar&c&dbar;

assign x4=abar&b&c&d;

assign x5=b&cbar&d;

assign f1=x1|x2|x3|x4|x5;

endmodule

## RTL realization
![image](https://github.com/Nijeesh-bit/Experiment--02-Implementation-of-combinational-logic-/assets/89188014/1ff8f21c-94cc-4ef9-b0f8-d2d18dfa68d1)

## Truth Table 
![image](https://github.com/Nijeesh-bit/Experiment--02-Implementation-of-combinational-logic-/assets/89188014/db13e505-3f57-4d10-b742-bfd8d44c944f)

## Timing Diagram
![image](https://github.com/Nijeesh-bit/Experiment--02-Implementation-of-combinational-logic-/assets/89188014/02ab5c60-9b8e-4e63-81e2-9e9d818fc869)

## Result:
Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.
[11:46 AM, 7/25/2023] Nijeesh SEC: # Experiment-03 Implementation of Half Adder and Full Adder circuit

# Implementation ofHalf Adder and Full Adder circuit
#### NAME:Sathyaa R
#### Register no.: 23000714
### AIM:
To design a half adder and full adder circuit and verify its truth table in Quartus using Verilog programming.

### Equipments Required:
Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime
Theory
Adders are digital circuits that carry out addition of numbers.

### Half Adder
Half adder is a combinational circuit that performs simple addition of two binary numbers. The input variables designate the augend and addend bits; the output variables produce the sum and carry. It is necessary to specify two output variables because the result may consist of two binary digits.

Sum = A’B+AB’ =A ⊕ B Carry = AB

### Full Adder
Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin Carry = AB + ACin + BCin

 ![image](https://user-images.githubusercontent.com/36288975/163552156-a13e5a56-c638-4110-97d9-8896907c8d25.png)

#### Figure -01 HALF ADDER 


![image](https://user-images.githubusercontent.com/36288975/163552057-b3547877-6d07-45b4-b7e0-bcfebfad9e1d.png)

#### Figure -02 FULL ADDER 

### Procedure
1. Create a New Project:
   - Open Quartus and create a new project by selecting "File" > "New Project Wizard."
   - Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).

2. Create a New Design File:
   - Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
   - Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.

3. Write the Combinational Logic Code:
   - Open the newly created Verilog or VHDL file and write the code for your combinational logic.
     
4. Compile the Project:
   - To compile the project, click on "Processing" > "Start Compilation" in the menu.
   - Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.

5. Analyze and Fix Errors:
   - If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
   - Review and fix any issues in your code if necessary.
   - View the RTL diagram.

6. Verification:
   - Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".
   - Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
   - Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.


### Program:

Program to design a half adder and full adder circuit and verify its truth table in quartus using Verilog programming.
#### HALF ADDER

module Halfadder(sum,a,b,carry);

input a,b;

output sum,carry;

xor(sum,a,b);

and(carry,a,b);

endmodule 

#### FULL ADDER:

module fulladder(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

xor(sum,a,b,c);

assign carry=a&b | b&c | a&c;

endmodule 

### TRUTH TABLE HALF ADDER:
![image](https://github.com/Nijeesh-bit/Exp-02-Implementation-of-Half-Adder-and-Full-Adder-circuit/assets/89188014/ae2d40fe-6869-431b-93b4-1e274bd25771)

### RTL realization HALF ADDER:
![image](https://github.com/Nijeesh-bit/Exp-02-Implementation-of-Half-Adder-and-Full-Adder-circuit/assets/89188014/b5171707-bf9a-4e39-9113-ba60af41353b)

### TIMING DIAGRAM HALF ADDER:
![image](https://github.com/Nijeesh-bit/Exp-02-Implementation-of-Half-Adder-and-Full-Adder-circuit/assets/89188014/b0ab1794-2348-44c1-997f-56148a344bc4)

### TRUTH TABLE FULL ADDER:
![image](https://github.com/Nijeesh-bit/Exp-02-Implementation-of-Half-Adder-and-Full-Adder-circuit/assets/89188014/786927bd-7c2a-4832-8389-da4b876a6ab3)

### RTL realization FULL ADDER:
![image](https://github.com/Nijeesh-bit/Exp-02-Implementation-of-Half-Adder-and-Full-Adder-circuit/assets/89188014/4aa2d7c9-f4e6-4739-8181-4ecd4e9c6c6f)

### TIMING DIAGRAM HALF ADDER:
![image](https://github.com/Nijeesh-bit/Exp-02-Implementation-of-Half-Adder-and-Full-Adder-circuit/assets/89188014/b3e9c25e-2c1e-4bf1-9561-564710da7214)

### Result:
Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.

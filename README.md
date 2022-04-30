# Design-of-Toffoli-Quantum-Gate
This circuit simulation project presents the design and simulation of Toffoli Gate using open-source tool eSim and Sky130 PDK library. 
## Table of contents
▫️ Abstract  
▫️ Tools used  
▫️ Circuit Schematic  
▫️ Result & Waveforms   
▫️ Spice Netlist  
▫️ References  
## Abstract  
Toffoli gate is a 3 input, 3 output reversible logic gate. It is a universal logic gate i.e. it can be used to construct any classical reversible logic circuit. It is also called as CCNOT gate where CCNOT stands for Controlled Controlled NOT. For Toffoli gate if the first two input bits are high, then the third output bit becomes zero due to XOR operation, otherwise all bits remain the same. 

![bgdm](https://user-images.githubusercontent.com/68592620/166119595-de2a2e2f-336d-4842-a81e-d7c82489013b.jpg)

A circuit is called reversible only when its inputs can be determined from its outputs and the input-output possess one to one mapping. Fredkin gate, Toffoli gate, interaction gate, and switch gate are other such examples of reversible logic gates. In a reversible logic gate, the number of outputs is always equal to the number of inputs. Reversible logic gates are memoryless logic units and the function realised by a reversible circuit is a mathematically Injective logic function. A function is called Injective function when its each input element is mapped to only one & unique output element. That's how it has one to one mapping.

The major advantage such kind of reversible circuits provide includes better input traceability, low computation time i.e. high speed computations and reduced information loss.Also, Reversible circuits make reversible computations possible in which the loss of information is drastically reduced which, according to the Landauer’s Research leads to reduced loss of energy in the circuit. Major applications of reversable computing includes low-power VLSI design, quantum computation, DNA computing and nanotechnology etc.
## Tools used

![Screenshot 2022-05-01 003037](https://user-images.githubusercontent.com/68592620/166119582-37f72063-deed-44e6-90d3-9b32ec60c0ca.png)

## Circuit Schematic

![ckt](https://user-images.githubusercontent.com/68592620/166119626-006c40a3-50cd-4e6f-bf9e-af6ab3b37b7f.jpg)

## Results & Waveforms

## Spice Netlist
```
* c:\users\arpit\coding\esim_projects\toffoligate\toffoligate.cir

.include NMOS-180nm.lib
.include PMOS-180nm.lib
m1 net-_m1-pad1_ vin1_a_ net-_m1-pad3_ net-_m1-pad3_ CMOSP W=100u L=100u M=1
m4 net-_m1-pad1_ vin2_b_ net-_m1-pad3_ net-_m1-pad3_ CMOSP W=100u L=100u M=1
m2 net-_m1-pad1_ vin1_a_ net-_m2-pad3_ gnd CMOSN W=100u L=100u M=1
m3 net-_m2-pad3_ vin2_b_ gnd gnd CMOSN W=100u L=100u M=1
m6 aandb net-_m1-pad1_ net-_m1-pad3_ net-_m1-pad3_ CMOSP W=100u L=100u M=1
m5 aandb net-_m1-pad1_ gnd gnd CMOSN W=100u L=100u M=1
m8 net-_m11-pad2_ aandb net-_m1-pad3_ net-_m1-pad3_ CMOSP W=100u L=100u M=1
m7 net-_m11-pad2_ aandb gnd gnd CMOSN W=100u L=100u M=1
m10 net-_m10-pad1_ vin3_c_ net-_m1-pad3_ net-_m1-pad3_ CMOSP W=100u L=100u M=1
m9 net-_m10-pad1_ vin3_c_ gnd gnd CMOSN W=100u L=100u M=1
m13 net-_m13-pad1_ net-_m11-pad2_ net-_m1-pad3_ net-_m1-pad3_ CMOSP W=100u L=100u M=1
m15 net-_m13-pad1_ net-_m10-pad1_ net-_m1-pad3_ net-_m1-pad3_ CMOSP W=100u L=100u M=1
m14 vout3_abxorc_ aandb net-_m13-pad1_ net-_m1-pad3_ CMOSP W=100u L=100u M=1
m16 vout3_abxorc_ vin3_c_ net-_m13-pad1_ net-_m1-pad3_ CMOSP W=100u L=100u M=1
m11 vout3_abxorc_ net-_m11-pad2_ net-_m11-pad3_ gnd CMOSN W=100u L=100u M=1
m12 net-_m11-pad3_ net-_m10-pad1_ gnd gnd CMOSN W=100u L=100u M=1
m17 vout3_abxorc_ aandb net-_m17-pad3_ gnd CMOSN W=100u L=100u M=1
m18 net-_m17-pad3_ vin3_c_ gnd gnd CMOSN W=100u L=100u M=1
v4 net-_m1-pad3_ gnd  dc 1.8
v1  vin1_a_ gnd pulse(0 1.8 0 0 0 25 50)
v2  vin2_b_ gnd pulse(0 1.8 0 0 0 7.5 15)
v3  vin3_c_ gnd pulse(0 1.8 0 0 0 15 30)
* u1  vin1_a_ plot_v1
* u2  vin2_b_ plot_v1
* u3  vin3_c_ plot_v1
* u4  vout3_abxorc_ plot_v1
* u5  aandb plot_v1
.tran 1e-00 90e-00 0e-00

* Control Statements 
.control
run
print allv > plot_data_v.txt
print alli > plot_data_i.txt
plot v(vin1_a_)
plot v(vin2_b_)
plot v(vin3_c_)
plot v(vout3_abxorc_)
plot v(aandb)
.endc
.end
```
## References
▫️ “Design and Implementation of New Feynman and Toffoli (NFT) Gates in Quantum-dot Cellular Automata (QCA)” by Sajjad Waheed, Md. Golam Rasel.  
▫️ “Cost Efficient Design of Reversible Adder Circuits for Low Power Applications” by Neeraj Kumar Misra, Mukesh Kumar Kushwaha, Subodh Wairya, Amit Kumar.

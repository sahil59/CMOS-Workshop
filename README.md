## Day 1

### **_1.1.0 Circuit design and Spice simulations_**

![image](https://user-images.githubusercontent.com/84899907/139198063-3df5f69e-0b57-48eb-b644-af9898bcce2d.png)
![image](https://user-images.githubusercontent.com/84899907/139198091-879cad9e-fef0-4b2c-a8db-f55616d8fb99.png)

Day one we got to know about the basic meaning of the words “Circuit design” and “SPICE simulation” how to interpret or analyze the graph to get the knowledge about the specific components delay time. Also, some questions were answered like: 
        
* Why do we need SPICE?
* How we can draw delay table with the help of delay table?
* Where does the delay of a cell comes from?
* Are the models accurate?
* How do we verify, if what we are doing in static timing analysis are right or not?

### **_1.1.1 Basics about NMOS, Threshold voltage_**

There are two types of MOS:

   * N-channel MOS
   * P-channel MOS

In this part we got to know about the structure of N-channel metal-oxide semiconductor (NMOS) which is built on a p type substrate, its structure is as follows: -

 ![image](https://user-images.githubusercontent.com/84899907/139267706-a89cbd78-3648-467d-8613-701ef126a994.png)

Where,

   G is gate\
   S is source\
   D is drain\
   B is body

NMOS is a 4 terminal (gate, source, drain and body) device which consists of p-substrate having an isolation region made up of SiO<sub>2</sub> (Silicon dioxide) which helps to keep the two transistors independent from each other if they are kept close to each other. It also has n<sup>+</sup> diffusion region where we have a space between them to place gate oxide over which Poly-si or metal gate is placed.

Also, in the same video we learnt about the threshold voltage (V<sub>t</sub>). 
Then we took a case where voltage across the gate and source is 0 i.e., V<sub>gs</sub> = 0. Where drain source and body are connected to the ground. Here we have two junctions; substrate-source (B-S) and substrate-drain (B-D) in the form of p-n junction diode. Both are off since no voltage is applied. S-D resistance is high because they are grounded. If we apply V<sub>gs</sub> voltage to gate positive charges move towards the p-substrate leaving behind the negative charges.

### **_1.1.2 Continuation of the threshold voltage_**

   So, if we increase the gate voltage, depletion layer increases causing a phenomenon called Strong inversion where the semi-conductor surface inverts to n – type material. The V<sub>gs</sub> voltage at which strong inversion occurs is called Threshold Voltage (V<sub>t</sub>). And with the further increase of gate voltage, it will start attracting the heavily dopped area of negative charges from the source terminal side or the drain side. There will be no change in the depletion layer width since it has already been depleted but there will be increase in the channel width.




Now if we take two scenarios in the above condition:-

Case 1: When V<sub>sb</sub> = 0 <br  />
        No more depletion takes place.<br  />


Case 2: When V<sub>sb</sub> = positive value<br  />
        Additional depletion occurs between the source and abstract.<br  />

### **_1.1.3 Continuation of the two scenarios_**

In second case due to positive voltage few charges from the channel are pulled towards the source terminal. Due to this still there is no inversion observed but in the first case still there is depletion as semi-conductor surface inverts to n-type material at voltage V<sub>gs</sub> = V<sub>to</sub>. Semi-conductor surface in second case inverts to n-type material at voltage V<sub>gs</sub> = V<sub>to</sub> + V<sub>1</sub>.

From the above cases we can conclude that in the presence of substrate bias V<sub>sb</sub>, additional potential is required for strong inversion.

#### Threshold voltage Equation: 

![image](https://user-images.githubusercontent.com/84899907/139279729-59f7643e-e33d-4b4b-90c2-165a832ce510.png)

Where, 

V<sub>to</sub> = Threshold voltage at V<sub>sb</sub> = 0 which is a function of manufacturing process<br  />
γ = Body effect coefficient, expresses the impact of changes in the body bis Vsb (unit is V<sup> 0.5</sup>)<br  />
ϕ<sub>f</sub> = Fermi potential 

#### Body effect formula:

![image](https://user-images.githubusercontent.com/84899907/139380157-eac55b31-5f15-4f43-ae1f-d36257fb0130.png)
 
Where, <br />

ε<sub>si</sub> = Relative permittivity of silicon = 11.7<br />
 N<sub>A</sub> = doping concentration<br />
             q = charge of the electron<br />
C<sub>OX</sub> = Oxide capacitance

![image](https://user-images.githubusercontent.com/84899907/139380376-e8c3d4eb-9acb-4ebd-a350-55278cb070f4.png)

where,<br />
n<sub>i</sub> = intrinsic doping parameter for the substrate

### **_1.2.0 Resistive operation_**

There are three mods of operation:

1. Cut off region of operation
2. Linear region or Resistive operation
3. Saturation region of operation

Here we learnt about the resistive operation which is also known as linear region. Since V<sub>gs</sub> = V<sub>t</sub>, let’s assume that what will happen ai different voltage V<sub>gs</sub> > V<sub>t</sub>. Hence it will induce the charge Q<sub>i</sub> which is directly proportional to V<sub>gs</sub> - V<sub>t</sub>. If we analyze at V<sub>gs</sub> = 1V, small V<sub>ds</sub> = 0.05V and V<sub>t</sub> = 0.45V, the following graph will be formed as shown in image given below. Due to which V(x) is introduced which is the voltage at point ‘x’ along the channel V<sub>gs</sub> - V(x) is the gate to channel voltage at that point.

![image](https://user-images.githubusercontent.com/84899907/139392116-a3159e70-c2a3-46de-aa85-fd10683a3960.png)
 
### **_1.2.1 First order analysis, drift current_**

#### First order analysis:

![image](https://user-images.githubusercontent.com/84899907/139392232-60b66990-a615-4acc-aae5-7dafe43e03d2.png)

Where, C<sub>ox</sub> = Gate oxide capacitance

![image](https://user-images.githubusercontent.com/84899907/139393105-26db1d3f-a4bd-4fef-a181-5eb5c1b0098d.png)
                     
Where, 

ε<sub>0</sub>x = Oxide permittivity = 3.5 * 10e-11 f/m<br/>
             t<sub>0</sub>x = Oxide thickness
     
Now from the device we have two types of current:

1. Drift current which is the current due to potential difference<br/>

> I<sub>d</sub> = velocity of the charge carriers * available charge * over channel width
	
2. Diffusion current which is current due to difference in the carrier concentration

![image](https://user-images.githubusercontent.com/84899907/139393744-49ba737f-6ef4-422c-b111-40cc4cacc502.png)


### **_1.2.2 Drain current derivation_**

I<sub>d</sub> = velocity of the charge carriers * available charge * over channel width<br/>
 = -V<sub>n</sub>(x) * Q<sub>i</sub>(x) * W
 
By substituting the value of V<sub>n</sub> and Q<sub>i</sub> in the above equation,

velocity of charge carrier (V<sub>n</sub>) = Mobility * electric field = μn * ⅆv∕ⅆx

![image](https://user-images.githubusercontent.com/84899907/139410982-ff8fa2be-6987-4b23-aad2-0f8fdc58136a.png)

We get,

Id = μn* ⅆv⁄ⅆx * [C_OX  -([V_gs-V(x)]-V_t)]*W
Id * dx = μn * dv * [C<sub>OX</sub>-([V_gs-V(x)]-V_t)]*W
Integrating over the length ‘L’ on LHS and over drain-source voltage Vds on RHS, we get the below equation:

Id = μn.C_OX.(W⁄L)[(Vgs-Vt)Vds-〖Vds〗^2/2]
Id = kn'.(W⁄L)[(Vgs-Vt)Vds-〖Vds〗^2/2]
Where, kn'= process transconductance
Id = kn.[(Vgs-Vt)Vds-〖Vds〗^2/2]
Where, kn = kn'.(W⁄L) = gain factor
Now if we substitute the assumed values in the above equations, which are
Vgs = 1V
Vds = 0.05V
Vt = 0.45V
We will get,
Id = kn .[0.0275-0.00125]
Since the last term is similar to 0
∴Id=kn.0.0275→Linear or resistive region of operation
 Id = kn.(Vgs-Vt)Vds →linear f(Vds) 
1.2.3 Resistive region conclusion
We need to find out that what is the impact of drain current and this thing can be only done through SPICE simulation. Also, it will answer the question that How do we calculate Id for different values of ‘Vgs’ and at every value of Vgs, sweep Vds till (Vgs – Vt) using linear equation for Id?
1.2.4 Saturation region
Now we will see that what happens if the Vgs – Vt voltage exceeds it and how it enters Saturation region.
 
In the above table and diagram, we can see that once the Vgs – Vds voltage crosses the threshold voltage it goes to saturation region and hence there is no channel. This region is also called Pinch off region – no channel near drain.
Its condition is as follows:
                                              Vgs – Vds ≤ Vt
1.2.5 Drain current in the saturation region
Voltage over the channel remains constant = Vgs – Vt
By replacing Vds by Vgs – Vt in drain current equation
we get,
Id = kn/2.(Vgs-Vt)^2→no more linear f(Vds) 
∴Id =(kn^')/2.(W⁄L).(Vgs-Vt)^2
Effective conduction channel length is modulated by applied Vds. Hence if Vds increases, Depletion region at drain increases and Effective channel length decreases. Which brings us to the most accurate equation i.e., constant current equation for saturation region for MOS. The equation is as follows: 
∴Id =(kn^')/2.(W⁄L).(Vgs-Vt)^2 [1+λ Vds]
Where, λ = channel length modulation.
1.3.0 SPICE simulation
This time we will learn about how we can setup SPICE simulation so that we can get the accurate result and will also get to know the delay time. 
                                                             
Introduction was given regarding how to use SPICE netlist and what is the syntax for it.
 
 
SPICE netlist for NMOS

1.3.1 SPICE syntax
 
1.3.2 Technology file and commands
Under this topic we saw that how to use or define the technology files and how it can help us to simulate.



                     




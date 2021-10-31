# CMOS WORKSHOP

![image](https://user-images.githubusercontent.com/84899907/139587520-202938c1-dba8-482d-9167-01d89a175b75.png)

## Day 1

### **_1.1.0 Circuit design and Spice simulations_**

![image](https://user-images.githubusercontent.com/84899907/139198063-3df5f69e-0b57-48eb-b644-af9898bcce2d.png)
![image](https://user-images.githubusercontent.com/84899907/139198091-879cad9e-fef0-4b2c-a8db-f55616d8fb99.png)

Day one we got to know about the basic meaning of the words “Circuit design” and “SPICE simulation” how to interpret or analyze the graph to get the knowledge about the specific components delay time. Also, some questions were answered like: 
        
* Why do we need SPICE?
* How we can draw delay table with the help of simulation?
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

![image](https://user-images.githubusercontent.com/84899907/139434105-3d343c5a-fbd2-427b-945d-a50be0565337.png)

Integrating over the length ‘L’ on LHS and over drain-source voltage Vds on RHS, we get the below equation:

![image](https://user-images.githubusercontent.com/84899907/139434271-2f345306-f39b-4e27-9235-910ef1706fe4.png)

Where,<br/>

kn'= process transconductance

![image](https://user-images.githubusercontent.com/84899907/139434567-a3c68349-8ce1-47c1-8ad6-5aa170a5db56.png)

Where,<br/>

kn = kn'.(W⁄L) = gain factor

Now if we substitute the assumed values in the above equations, which are

V<sub>gs</sub> = 1V<br/>
V<sub>ds</sub> = 0.05V<br/>
V<sub>t</sub> = 0.45V<br/>

We will get,

I<sub>d</sub> = kn * [0.0275 - 0.00125]

Since, the last term is similar to 0

∴ Id=kn * 0.0275 → Linear or resistive region of operation

I<sub>d</sub> = kn.(V<sub>gs</sub>-V<sub>t</sub>)V<sub>ds</sub> → linear f(V<sub>ds</sub>) 
 
### **_1.2.3 Resistive region conclusion_**

We need to find out that what is the impact of drain current and this thing can be only done through SPICE simulation. Also, it will answer the question that How do we calculate I<sub>d</sub> for different values of ‘V<sub>gs</sub>’ and at every value of V<sub>gs</sub>, sweep V<sub>ds</sub> till (V<sub>gs</sub> – V<sub>t</sub>) using linear equation for Id?

### **_1.2.4 Saturation region_**

Now we will see that what happens if the V<sub>gs</sub> – V<sub>t</sub> voltage exceeds it and how it enters Saturation region.

![image](https://user-images.githubusercontent.com/84899907/139436798-4c70deff-4e23-4fdb-9e8f-d5100e9d1a38.png)

In the above table and diagram, we can see that once the V<sub>gs</sub> – V<sub>ds</sub> voltage crosses the threshold voltage it goes to saturation region and hence there is no channel. This region is also called Pinch off region – no channel near drain.

Its condition is as follows:

   V<sub>gs</sub> – V<sub>ds</sub> ≤ V<sub>t</sub>
					      
### **_1.2.5 Drain current in the saturation region_**

Voltage over the channel remains constant = V<sub>gs</sub> – V<sub>t</sub>

By replacing V<sub>ds</sub> by V<sub>gs</sub> – V<sub>t</sub> in drain current equation

we get,

I<sub>d</sub> = kn/2.(V<sub>gs</sub>-V<sub>t</sub>)<sup>2</sup> → no more linear f(V<sub>ds</sub>)

∴ I<sub>d</sub> = (kn')/2 * (W⁄L) * (V<sub>gs</sub>-V<sub>t</sub>)<sup>2</sup>

Effective conduction channel length is modulated by applied Vds. Hence if Vds increases, Depletion region at drain increases and Effective channel length decreases. Which brings us to the most accurate equation i.e., constant current equation for saturation region for MOS. 

The equation is as follows: 

![image](https://user-images.githubusercontent.com/84899907/139438188-45963fc8-281f-48e6-ac8f-d0c6431376f1.png)

Where, 

λ = channel length modulation.

### **_1.3.0 SPICE simulation_**

This time we will learn about how we can setup SPICE simulation so that we can get the accurate result and will also get to know the delay time.

![image](https://user-images.githubusercontent.com/84899907/139437096-f0b571c6-f797-457b-87dc-fee93b1e2049.png)
                                                             
Introduction was given regarding how to use SPICE netlist and what is the syntax for it.
 
![image](https://user-images.githubusercontent.com/84899907/139437449-818083a9-1aae-4112-8786-21537fb070d2.png)

### **_1.3.1 SPICE syntax_**

![image](https://user-images.githubusercontent.com/84899907/139437562-3d15abf6-cfe7-4107-a4a3-4aafaea3be3c.png)

### **_1.3.2 Technology file and commands_**

Under this topic we saw that how to use or define the technology files and how it can help us to simulate.

### **_1.3.3 and 1.3.4 First simulation in SPICE and sky130 models_**


> * ## Lab work
     
![image](https://user-images.githubusercontent.com/84899907/139438761-e526d986-1174-4c62-be36-66c725a8ca08.png)

![image](https://user-images.githubusercontent.com/84899907/139438938-9a675810-c859-4020-9dad-16cbf663d715.png)

![image](https://user-images.githubusercontent.com/84899907/139438995-7b25d911-2495-4ab0-9568-31df7cc6044a.png)

![image](https://user-images.githubusercontent.com/84899907/139439067-d488420b-60bb-4135-98ad-e2a1cc355ecd.png)

![image](https://user-images.githubusercontent.com/84899907/139439140-d31b901f-015f-487b-8d8a-04024458705c.png)

> * ## OUTPUT 

![image](https://user-images.githubusercontent.com/84899907/139439313-018566a4-96cc-48e7-8217-d657f3437ae8.png)

![image](https://user-images.githubusercontent.com/84899907/139439348-ec627f74-4072-46ba-b464-9d886bd57f47.png)

## DAY 2

### **_2.1.0 Simulation for lower nodes_**

![image](https://user-images.githubusercontent.com/84899907/139474776-e3f765ec-fd8e-4319-92be-26820c1df27c.png)

### **_2.1.1 Drain current vs gate voltage_** 

![image](https://user-images.githubusercontent.com/84899907/139477052-4b04f975-807c-4ac4-ba0c-2ee907bcbe92.png)

### **_2.1.2 velocity saturation at higher and lower electric field_**

For lower values of electric field velocity tends to be in linear electric field and after cut off velocity saturates or enters saturation region.

![image](https://user-images.githubusercontent.com/84899907/139477112-fed84f9e-8f68-43f5-9394-1eb6bd7da6cb.png)

Trends at the lower field is followed as velocity tends to be a linear function but at the higher fields, velocity becomes constant because of scattering effects.

### Observation 1: 

![image](https://user-images.githubusercontent.com/84899907/139582047-1f3d7921-f916-4198-8b32-71b01c66b7e1.png)

Re-deriving drain current using below boundary condition we get,

![image](https://user-images.githubusercontent.com/84899907/139582069-3ccfe739-5377-4b9b-a991-cca7757cb675.png)

![image](https://user-images.githubusercontent.com/84899907/139583463-59868abf-8e9d-4c50-9553-08f9b1680755.png)


### **_2.1.3 Velocity saturation_**

V<sub>dsat</sub> is a technology parameter which is called as saturation voltage i.e., voltage at which device velocity saturates and is independent of V<sub>gs</sub> or V<sub>ds</sub>

If we take some conditions

* If Vgt = minimum vale

![image](https://user-images.githubusercontent.com/84899907/139582263-a84f7830-a84c-4b45-9798-55862477371f.png)

* If  Vds = minimum value 

![image](https://user-images.githubusercontent.com/84899907/139582308-b7096bbd-0383-48c0-82e0-463bec5c2176.png)

![image](https://user-images.githubusercontent.com/84899907/139582330-6d979eb9-6dd9-4106-8201-8dcc2749064d.png)

### Observation 2:

![image](https://user-images.githubusercontent.com/84899907/139582363-b5bd704c-f529-4711-a16c-bc9b18fa6868.png)

### **_2.1.4 Id - Vgs_**

> * ## LAB Work

![image](https://user-images.githubusercontent.com/84899907/139582433-16359d82-5d9e-4508-89f3-3e9e24c677e3.png)

![image](https://user-images.githubusercontent.com/84899907/139582467-d9f7d1f8-1a43-448c-b394-d6d6ff0ae391.png)

> * ## OUTPUT

![image](https://user-images.githubusercontent.com/84899907/139582486-775525ae-9055-43a3-a849-54d4fb82a981.png)

![image](https://user-images.githubusercontent.com/84899907/139582525-8fa49f51-2c9f-4667-8ee0-4311a10b8899.png)

### **_2.1.5 Vt_**

> * ## LAB Work

![image](https://user-images.githubusercontent.com/84899907/139582672-927d9700-e5e8-4fb8-8eb3-3d582aca2fd8.png)

> * ## OUTPUT

![image](https://user-images.githubusercontent.com/84899907/139582724-b1cec448-2eee-42e4-82ce-76fd4e0718eb.png)

### **_2.2.0 CMOS - transfer Characteristics (VTC)_**

![image](https://user-images.githubusercontent.com/84899907/139582938-a02e186f-ecc6-4442-bc37-a7264ff5a7b1.png)

Transistor → Switch

* With infinite OFF resistance when |V<sub>gs</sub>| < |V<sub>t</sub>|
* With infinite ON resistance when |V<sub>gs</sub>| > |V<sub>t</sub>|

![image](https://user-images.githubusercontent.com/84899907/139582947-52805c93-b745-4518-9930-439b6226a700.png)

### **_2.2.1 MOS voltage current_**

![image](https://user-images.githubusercontent.com/84899907/139582972-44543c31-f41a-4c99-99ea-ba86cdc3d1fb.png)

Where V<sub>in</sub> = V<sub>dd</sub>

Direct path exists between V<sub>out</sub> and V<sub>s</sub>, resulting in V<sub>out</sub> = 0

When V<sub>in</sub> = 0

Direct Path exists between V<sub>dd</sub> and V<sub>out</sub>, resulting in V<sub>out</sub> = V<sub>dd</sub>

![image](https://user-images.githubusercontent.com/84899907/139583056-b682262c-bed0-44d9-b4bd-603246a15bb0.png)

### **_2.2.2 PMOS and NMOS drain current drain voltage_**
	
By observations: 

V<sub>gsn</sub> = V<sub>in</sub> – V<sub>ss</sub> = V<sub>in</sub>
V<sub>dsn</sub> = V<sub>out</sub>

V<sub>gsp</sub> = V<sub>in</sub> -V<sub>dd</sub>
V<sub>dsp</sub> = V<sub>out</sub> – V<sub>dd</sub>

![image](https://user-images.githubusercontent.com/84899907/139583677-ace2f4dc-5bb9-44e0-a0c3-d1d34cd5f064.png)


By observation: 
	
I<sub>dsp</sub> = -I<sub>dsn</sub>

![image](https://user-images.githubusercontent.com/84899907/139583187-1b67f8bb-0575-4b45-9b2e-6d648626dd3a.png)
	
### **_2.2.3 Convert PMOS gate-source-voltage to V<sub>in</sub>_**

Steps to convert the given terms in the terms of V<sub>in</sub> and V<sub>out</sub>.

Step 1:
	
![image](https://user-images.githubusercontent.com/84899907/139583278-9b033b96-a8b0-457a-ab5d-2bce8720f36b.png)
 
### **_2.2.4 Convert PMOS and NMOS drain-source-voltage to v<sub>out</sub>_**

Step 2:
	
 ![image](https://user-images.githubusercontent.com/84899907/139583306-cdb32313-ada6-4b35-8598-4a3a13beb27c.png)

Step 3:
 
![image](https://user-images.githubusercontent.com/84899907/139583317-4cb2f552-c47e-4793-b005-67e505202283.png)

### **_2.2.5 Merge PMOS and NMOS load curves and plot VTC_**

Step 4:

V<sub>in</sub> and V<sub>out</sub> are common to PMOS and NMOS. Graphically we will pick up V<sub>in</sub> points from the intersection of corresponding load lines.
 
 ![image](https://user-images.githubusercontent.com/84899907/139584221-45013779-6041-4a49-80dd-ea80d144dadd.png)

## DAY 3 

### **_3.1.0 SPICE deck for COMS_**

•	Component connectivity<br/>
•	Component values<br/>
•	Identify ‘nodes’<br/>
•	Name ‘nodes’

### **_3.1.1 SPICE simulation for CMOS_**
 
 ![image](https://user-images.githubusercontent.com/84899907/139584245-b2251455-721f-4b7b-ac97-3ba9e94cf7e4.png)

### **_3.1.2 SPICE simulation for CMOS_**
 
 > * ## LAB Work
 
 ![image](https://user-images.githubusercontent.com/84899907/139584278-a37c7974-39d1-475b-b1d4-bd4c8d1a1a58.png)

 ![image](https://user-images.githubusercontent.com/84899907/139584280-0eb1dcca-cdb1-4a42-82e1-0ec54fc54426.png)

 > * ## OUTPUT
 
 ![image](https://user-images.githubusercontent.com/84899907/139584299-186cb206-4ff0-401a-b733-81ae10c78997.png)

![image](https://user-images.githubusercontent.com/84899907/139584309-5df0ae20-cf63-49f0-8ddc-df19ea07f399.png)

> * ## LAB Work

![image](https://user-images.githubusercontent.com/84899907/139584328-17a839e3-9f59-431c-9791-bf316aa11e3e.png)

![image](https://user-images.githubusercontent.com/84899907/139584337-4d8caec8-3f6a-468d-89ee-13f3787f9f71.png)

> * ## OUTPUT

![image](https://user-images.githubusercontent.com/84899907/139584349-1299325e-86c5-4788-b1f3-5f4222a606fc.png)

![image](https://user-images.githubusercontent.com/84899907/139584369-fb761b9b-b074-42d1-804b-adbd58ea1dff.png)

### **_3.2.0 Switching Threshold, V<sub>m</sub>_**

![image](https://user-images.githubusercontent.com/84899907/139584404-34a5ebc1-9b2d-4bfa-81b6-f3e7d6c2d7ff.png)
 
### **_3.2.1 Analytical expression of Vm as a function of (W/L)p and (W/L)n_**

![image](https://user-images.githubusercontent.com/84899907/139584422-d0945cf6-661c-46d6-a887-1e8b68eba8c6.png)
  
  ![image](https://user-images.githubusercontent.com/84899907/139584442-12ca339b-d956-497a-8992-e7cf36705179.png)

Solving the above equation for V<sub>m</sub>
 
 ![image](https://user-images.githubusercontent.com/84899907/139584464-2d6b6588-bfcc-4868-abc3-56b3c8d45431.png)

### **_3.2.2 Analytical expression of (W/L)p and (W/L)n as a function of V<sub>m</sub>_**

Alternatively, the required ratio of POMS v/s NMOS transistor size can be derived such that V<sub>m</sub> is set

![image](https://user-images.githubusercontent.com/84899907/139584599-b3cc7b1a-231c-4ff9-b6b5-da9c91742658.png)

![image](https://user-images.githubusercontent.com/84899907/139584626-d94dbd3f-aa97-45a7-b49f-0cfcf304c155.png)

### **_3.2.3 Static and dynamic simulation of CMOS inverter_**
 
![image](https://user-images.githubusercontent.com/84899907/139584640-d9ba3084-dc72-43c0-b12c-c94998878c39.png)

![image](https://user-images.githubusercontent.com/84899907/139584648-ac6962d2-fc61-4f13-8796-5d16f05b43e7.png)

### **_3.2.4 Static and dynamic simulation of CMOS inverter with increased PMOS width_**
 
 ![image](https://user-images.githubusercontent.com/84899907/139584664-e5513df9-76f6-4781-95bb-950f16df67e2.png)

### **_3.2.5 Applications of CMOS inverter in clock network and STA_**

![image](https://user-images.githubusercontent.com/84899907/139584735-1ca974a8-f74c-418a-9c99-58de4d34464a.png)
 
 Approximately equal rise-fall delay. Typical characteristics for a clock inverter/buffer
 
 ![image](https://user-images.githubusercontent.com/84899907/139584757-0a08d0f4-f774-4bb3-8f90-f1fe0c702e51.png)

## DAY 4

### **_4.1.0 Introduction to noise margin_**

What is noise margin ?

![image](https://user-images.githubusercontent.com/84899907/139584860-20285908-07fc-4d20-aada-f131fd47c7fb.png)

Actual i/o characteristic of a inverter with finite slope 

### **_4.1.1 Noise margin voltage parameters_**
 
 ![image](https://user-images.githubusercontent.com/84899907/139584889-784d196d-350f-4446-b526-5e5f465365f8.png)

### **_4.1.2 Noise margin equation and summary_**

![image](https://user-images.githubusercontent.com/84899907/139584918-81df9ed2-84d9-47ed-b8b3-22f439ce8b9a.png)

![image](https://user-images.githubusercontent.com/84899907/139584924-d28fbd3b-e905-471d-a0d9-1418db168785.png)

### **_4.1.3 Noise margin variation with respect to PMOS width_**
 
 ![image](https://user-images.githubusercontent.com/84899907/139584947-6ddff6a3-f202-4214-8136-9e8ecd6634d4.png)

### **_4.1.4 Noise margin labs_**
 
 > * ## LAB Work
 
 ![image](https://user-images.githubusercontent.com/84899907/139584989-f7f5d136-8c28-4e6b-b381-dc7454b5df38.png)

 ![image](https://user-images.githubusercontent.com/84899907/139584995-08d61bfd-b214-4109-ab55-040b7a9ebef3.png)

> * ## OUTPUT 

![image](https://user-images.githubusercontent.com/84899907/139585021-994a8511-0f6f-4b02-a766-97734b24116a.png)

![image](https://user-images.githubusercontent.com/84899907/139585025-e9500090-56b6-4d97-be50-80419f756aa2.png)

![image](https://user-images.githubusercontent.com/84899907/139585044-ce19829b-b2da-4771-80be-9363e89aa06e.png)


## DAY 5

### **_5.1.0 Smart SPICE simulation for power supply variations_**
 
 ![image](https://user-images.githubusercontent.com/84899907/139585061-f60444aa-3c77-4c91-9137-8906f9bd5a46.png)

### **_5.1.1 Advantages and disadvantages using low supply voltage_** 
 
 Advantages of using 0.5V supply
 
 1. Increase in gain (close to 50% improvement)
 2. Significant reduction in engergy (close to 90% improvement)

Disadvantages

1. Performance impact


### **_5.1.2 Supply Variation Labs_**

> * ## LAB Work

![image](https://user-images.githubusercontent.com/84899907/139585183-3fa2940e-dbae-46d7-a99f-4106c039bcf9.png)

![image](https://user-images.githubusercontent.com/84899907/139585188-630633a5-464d-4255-9171-72edf5447893.png)

> * ## OUTPUT

![image](https://user-images.githubusercontent.com/84899907/139585201-90b12530-7d75-4dbd-9e1d-6a2a2f67c492.png)

![image](https://user-images.githubusercontent.com/84899907/139585209-971a8f65-18f4-47ab-b64d-8df5a1ee2ff8.png)

### **_5.2.0 Sources of variation and Etching process_**
 
![image](https://user-images.githubusercontent.com/84899907/139585233-8b0d58e2-3c68-4601-870c-2a4795ebf88e.png)

![image](https://user-images.githubusercontent.com/84899907/139585238-b2d528ab-d02d-4a1d-a4ee-a6df2f0efb30.png)

![image](https://user-images.githubusercontent.com/84899907/139585248-d66d4bb0-4abb-4292-99d4-d098d075d67e.png)

### **_5.2.1 Sources of variation and oxide thickness_**
 
![image](https://user-images.githubusercontent.com/84899907/139585265-cdf5f3e5-625f-4d70-a4ae-38861289c797.png)

![image](https://user-images.githubusercontent.com/84899907/139585272-dc039b17-5fbe-41b2-b0d6-07fb5b708968.png)

### **_5.2.2 Smart SPICE simulation for device variations_**
 
 ![image](https://user-images.githubusercontent.com/84899907/139585308-bd20a099-9624-480a-8381-075f1b130c09.png)

![image](https://user-images.githubusercontent.com/84899907/139585314-e21fe826-8979-4b88-82fc-273bd180ac64.png)

### **_5.2.3 Conclusion_**

![image](https://user-images.githubusercontent.com/84899907/139585334-d7b7869a-dee5-46ac-9b55-22051801cf16.png)
 
### **_5.2.4 Device Variation Labs_**
 
 > * ## LAB Work

![image](https://user-images.githubusercontent.com/84899907/139585432-ac1131fd-4cf3-40ae-abca-0fc245845635.png)

![image](https://user-images.githubusercontent.com/84899907/139585442-0af4cbf8-fa65-4a51-a17e-f7594569b3b5.png)

> * ## OUTPUT

![image](https://user-images.githubusercontent.com/84899907/139585480-1dd10d5c-fd75-46ad-b2c1-4c66351b9bf0.png)

![image](https://user-images.githubusercontent.com/84899907/139585486-7de7d9bf-09d2-4654-acd4-179d17a91ac6.png)

## Conclusion

This workshop gave a brief idea about the ground level of the MOSFET and CMOS and how does it work, what are their characteristics and how does it work. I also got to know about the SPICE simulations lab and I also learnt how to analyse the graph and take output from it. ALL Thanks Kunal sir and his team.

## References

https://vsdiat.com/enrolledCourses

https://github.com/kunalg123/sky130CircuitDesignWorkshop

https://github.com/VrushabhDamle/sky130CircuitDesignWorkshop/blob/main/README.md

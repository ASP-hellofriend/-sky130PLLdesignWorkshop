# Phase-Locked Loop(PLL) IC design on Open-Source Google-Skywater 130nm Workshop

![](https://www.vlsisystemdesign.com/wp-content/uploads/2021/07/PLL-Workshop-Banner_efabless.png)

## Brief Description
This 2-day Workshop, conduted by [VLSI System Design], focuses on Phase-Locked Loop IC design using Open-Source Google-Skywater 130nm node. The workshop takes an intuitive approach to designing a simple PLL with extraordinarily little math and without diving into complex frequency domain analysis or control system theory. The tools used are Ngspice (for circuit simulation) and Magic (used to create layout design and for finding out parasitic capacitances). These tools were briefly covered. The workshop started with basic PLL concepts, spanning all the steps in the IC design flow - circuit design, simulation, layout, parasitics extraction, post layout simulation and finally. It also, briefly, included the use of the latest CARAVEL harness to make tapeouts.

# *INDEX*
- [INDEX](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#index)
- [Day 1: PLL Theory and Lab setup](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#day-1-pll-theory-and-lab-setup)
    - [Part 1: Introduction to PLL](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-1-introduction-to-pll)
    - [Part 2: Introduction to Phase Frequency Detector](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-2-introduction-to-phase-frequency-detector)
    - [Part 3: Introduction to Charge Pump](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-3-introduction-to-charge-pump)
    - [Part 4: Introduction to Voltage Controlled Oscillator and Frequency Divider](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-4-introduction-to-voltage-controlled-oscillator-and-frequency-divider)
    - [Part 5: Tool Setup and Design Flow](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-5-tool-setup-and-design-flow)
    - [Part 6: Introduction to PDK, specifications and pre-layout circuits](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-6-introduction-to-pdk-specifications-and-pre-layout-circuits)
    - [Part 7: Circuit design simulation tool - Ngspice Setup](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-7-circuit-design-simulation-tool---ngspice-setup)
    - [Part 8: Layout design tool - Magic Setup](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-8-layout-design-tool---magic-setup)
- [Day 2: PLL Labs and post-layout simulations](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#day-2-pll-labs-and-post-layout-simulations)
    - [Part 9: PLL components circuit design](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-9-pll-components-circuit-design)
    - [Part 10: PLL components circuit simulations](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-10-pll-components-circuit-simulations)
        - [Simulation File for Charge Pump](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#simulation-file-for-charge-pump)
        - [Simulation File for VCO](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#simulation-file-for-vco)
        - [Simulation File for PFD](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#simulation-file-for-pfd)
        - [For the mcq on charge pump](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#for-the-mcq-on-charge-pump)
    - [Part 11: Steps to combine PLL sub-circuits and PLL full design simulation](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-11-steps-to-combine-pll-sub-circuits-and-pll-full-design-simulation)
    - [Part 12: Troubleshooting steps](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-12-troubleshooting-steps)
    - [Part 13: Layout design](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-13-layout-design)
    - [Part 14: Layout Walkthrough](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-14-layout-walkthrough)
        - [For the mcq on box function](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#for-the-mcq-on-box-function)
    - [Part 15: Parasitic Extraction](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-15-parasitic-extraction)
        - [For the mcq on parasitics extraction](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#for-the-mcq-on-parasitics-extraction)
    - [Part 16: Post Layout simulations](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-16-post-layout-simulations)
        - [The post layout simulation](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#the-post-layout-simulation)
        - [For the mcq on post layout simulation](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#for-the-mcq-on-post-layout-simulation)
    - [Part 17: Steps to combine layouts](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-17-steps-to-combine-layouts)
    - [Part 18: Tapeout theory](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-18-tapeout-theory)
    - [Part 19: Tapeout labs](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#part-19-tapeout-labs)
- [Conclusion](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#conclusion)

# Day 1: PLL Theory and Lab setup

The first day of the Workshop was dedicated towards acquainting us with the concepts related to PLL such as its internal components, their working, the uses of PLL and why it is advantageous over other methods of frequency generation.
A brief introduction to the two softwaress; NgSPICE and Magic was also provided, along with installation and setup instructions.

## Part 1: Introduction to PLL

Phase-locked loops (PLL) is a control system in which the output signal is based on the input signal and a feedback reference. It is used extensively to generate a precise clock signal with a clear spectrum (i.e., without phase or frequency noise), over a wide range of frequencies.

- Quartz crystals and Voltage-Controlled Oscillators (VCO) can be used to generate clock pulse.
- Quartz crystals have pure spectum but can only generate one frequency.
- VCOs can be controlled with an input voltage signal. However, they tend to have noise in their frequency spectrum.

![PLL Theory 1](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.1%20desc.jpeg)
![PLL Theory 2](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.1%20int%20comps.jpeg)
![Internal Components](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.1%20PLL%20internal%20components.png)

Intuition : PLLs mimics the reference frequency it is provided, while maintaining a clean frequency spectrum. Mimicking a reference frequency refers to producing output frequency which is either equal to or an integral multiple of the reference frequency.
![Intuition](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.1%20PLL.png)

## Part 2: Introduction to Phase Frequency Detector

- The Phase Frequency Detector (PFD) is used to compare the input reference signal and output feedback signal and generate a control signal. It measures the phase difference between Reference (REF) and Output (OUT) signal, using an XOR gate.
- The XOR gate help us detect differences in phase, but we do not have an idea about whether the Output signal is leading or lagging the Reference.
- This issue is resolved using 2 different outputs; UP and DOWN.
- 'Up' signal stays HIGH between falling edge of REF and falling edge of OUT.
- 'Down'signal stays HIGH between falling edge of OUT and falling edge of REF.
- Dead Zone : If the 2 signals input the PFD are very close, i.e., separated by a very small difference in phase, then output waveform gets clipped. This zone is called 'Dead Zone'.
- More sensitive PFD results in better PLL.
![Output at different frequencies](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.2%20PFD%20diff%20freq.png)
![Output in case of lead or lag](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.2%20PFD%20lagging%20and%20leading.png)
![PFD FSM State Diagram](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.2%20fsm.jpeg)
![PFD Sequential Circuit](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.2%20fsm%20using%20ff.jpeg)

## Part 3: Introduction to Charge Pump

- Charge Pump is defined as a kind of DC-to-DC converter that uses capacitors for energetic charge storage to raise or lower voltage.
- They can be modelled as a combination of 2 ideal current sources, which are controlled by 2 switches.

![Desc](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.3%20charge%20pump.jpeg)

- In a PLL, it is used to convert the digital measure of phase/frequency difference into an analog signal to control the VCO.
- The capacitor across the Output is used to smoothen the Output Voltage swing.
- To further smoothen the voltage swing, a low-pass filter, called as Loop Filter, can be used.

![Loop Filter](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.3%20Loop%20Filter.png)

- Output of charge pump controls the VCO. Higher o/p voltage results in faster charging of VCO and hence higher frequency and vice-versa.
- Assumptions :
               - Cx= C/10
               - Loop filter bandwidth = 1/(1 + R.C1),
                   where C1 = C . Cx / (C + Cx)

## Part 4: Introduction to Voltage Controlled Oscillator and Frequency Divider

- A voltage-controlled oscillator (VCO) is an electronic oscillator whose output frequency is proportional to its input voltage. An oscillator produces a periodic AC signal, and in VCOs, the oscillation frequency is determined by voltage.

![Circuit](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.4%20VCO.png)
![Diagram](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.4%20vco%20diag.jpeg)

- Period = 2 * delay * no. of inverters, where delay is time taken to charge the output capacitor of charge pump.
- Frequency depends on delay, which inturn is dependent on current supplied.
- In the given 3 stage inverter, output flips by 'pi radians' in only half the oscillation period.
![Calculation](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.4%20vco%20tp%20calc.jpeg)

- A frequency divider, also called a clock divider or scaler or prescaler, is a circuit that takes an input signal of a frequency, f, and generates an output signal of a frequency : nf, where n is some factor.
![Circuit](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.4%20Frequency%20divider.png)
- Implemented using a T flip-flop.
- Output frequency of T flip-flop is half the frequency of the input signal.

- IMPORTANT TERMS:

  1. Lock range : Lock stage is defined as the stage where the o/p is mimicking the i/p. The range of frequencies over which the PLL is able to follow i/p frequency variations once loacked is called as lock range.
  
  2. Capture range : The range of frequencies for which the PLL is able to attain a lock state from an unlocked state. It depends on filter bandwidth.
  
  Lock range > Capture Range
  
  3. Settling time : The time within which a PLL is able to attain a lock from an initially unlocked state. It depends on how quickly charge pump rises to its stable value.

## Part 5: Tool Setup and Design Flow

- Advisable to build any software tool from its source code as it will be the latest version with all the updates and patches.
- Tools used:
   1. NgSPICE - Transistor-level circuit simulation
   2. Magic - Parasitic design & extraction
  
 - Steps to install NgSPICE:
    Type `sudo apt-get install ngspice` in the Terminal.
    
 - Steps to install Magic:
   1. To update the OS : `sudo apt-get update && sudo apt-get upgrade`
   2. Clone the Magic Repository : `git clone git://opencircuitdesign.com/magic`
   3. Install the csh shell : `sudo apt-get install csh`
   4. Entering the correct directory : `cd magic`
   5. `./configure` 
   6. `make` to compile.
   7. `sudo make install` to install magic on the device.
   
   ![Commands](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.5%20Tools%20Commands.png)
   ![Setup](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.5%20Tools%20Setup.png)
   
- Development Flow :
![Development Flow](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.5%20Development%20Flow.png)

## Part 6: Introduction to PDK, specifications and pre-layout circuits

- SKY130 PDK is used.
- PDK or process design kit is a set of files used within the semiconductor industry to model a fabrication process for the design tools used to design an integrated circuit.
- PDK conatins transistor characteristics and other information such as standard cells, their timing information, their layouts, corresponding Verilogs and so on.
- Transistor characteristics :
  ![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.6%20tran%20char.jpeg)
- Details obtained from PLL specification :  
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.6%20PLL%20spec.jpeg)
![PLL Specification](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.6%20PLL%20Specification.png)
![SKY130 PDK](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.6%20SKY130%20PDK.png)
- Pre-Layout phase is all about the development and the transistor level simulation of the circuits.
 Following are the pre-layout diagrams for FD, VCO, PFD and CP.
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.6%20Pre%20layout%20-%20FD.jpeg)
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.6%20Pre%20layout%20-%20VCO.png)
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.6%20Pre%20layout%20-%20PFD.png)
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Theory/1.6%20Pre%20layout%20-%20CP.png)

## Part 7: Circuit design simulation tool - Ngspice Setup

- Install NgSPICE using Ubuntu's package manager. 
   `sudo apt-get install ngspice`
- Fetch sky130 library needed for simulation. It is present in Google's skywater-pdk repository. We need to select the 'primitives' library.
   `git clone https://github.com/google/skywater-pdk-libs-sky130_fd_pr.git`
- Pick the files needed from "skywater-pdk-libs-sky130_fd_pr" folder. 
- Go to the 'cells' folder and search for "nfet_01v8". Inside this folder, search "tt" and chose the file named "sky130_fd_pr__nfet_01v8__tt_leak.pm3.spice". Copy this file to the directory that will be used for PLL simulations (spice_lib).
- Go to the cells folder and search for "pfet_01v8". Inside this folder, search "tt" and chose the file named "sky130_fd_pr__pfet_01v8__tt_leak.pm3.spice". Copy this file to the directory that will be used for PLL simulations (spice_lib).
- Go to 'models' folder and then go to parameters and copy the files "invariant.spice" and "lod.spice" to the directory that will be used for PLL simulations.
- Open Terminal in the spice_lib directory.

![spice_lib dir.](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/spice_lib%20folder.png)

- In the terminal type the command `nano sky130.lib`.
- Now, include all the files that were just copied.
- Save this file using `ctrl+S` and then exit using `ctrl+X`. Then, press `Enter`. The 'sky130.lib' file looks as follows.

![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/sky130.lib.png)

## Part 8: Layout design tool - Magic Setup

- Needed to work with Skywater node.
- Clone the magic repository to get the source code.
  `git clone git://opencircuitdesign.com/magic`
- Then, install the dependancies which can be found at the [Install](http://opencircuitdesign.com/magic/) page.
- Now go into the magic folder using the "cd" command and compile magic using `./configure` command.
- Run the configure, make and install commands on the terminal.
- Search open pdks on google and select the [RTimothy/open_pdks](https://github.com/RTimothyEdwards/open_pdks)
- Clone this repository and compile it or download [sky130A.tech](https://drive.google.com/file/d/18BG4zzpRrcHP0UoBcNLA3sWFDVdNlUtp/view) and place it in the main folder.


# Day 2: PLL Labs and post-layout simulations

The second day of the Workshop was dedicated to labs. NgSPICE was used for simulating, first the individual components of the PLL and then the PLL itself. Then, after Layout was done, the parasitic capacitences were calculated using Magic. Finally, a brief description of Caravel was given.

## Part 9: PLL components circuit design

- SPICE files are used to create crcuit description.
- SPICE file is a text file with .cir or .spice extension.
- To create a new SPICE file : `touch <File_Name>.cir`.
- We add circuit description to this SPICE file. 
- ALWAYS INCLUDE 'spice_lib' file.
- We include a number and name for each net. We connect these nets to create the circuit.

### **Frequency Divider Simulation FILE**

```
.include sky130nm.lib

xm1 1 2 3 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm2 0 2 3 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm3 3 Clkb 4 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm4 3 Clk 4 0 sky130_fd_pr__nfet_01v8 l=150n w=840n 

xm7 1 4 5 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm8 0 4 5 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm9 5 Clk 6 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm10 5 Clkb 6 0 sky130_fd_pr__nfet_01v8 l=150n w=640n 

xm11 1 6 2 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm12 0 6 2 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm13 1 Clk Clkb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm14 0 Clk Clkb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

v1 1 0 1.8
v2 Clk 0 PULSE 0 1.8 1n 6p 6p 5ns 10ns

c1 6 0 10f
.control
tran 0.1ns 0.2us
plot v(6) v(Clk)+2
.endc

.end

```

- The command `v2 Clk 0 PULSE 0 1.8 1n 6p 6p 5ns 10ns` represents the sequence: voltage1, voltage2, delay, rise time, fall time, pulse width, period.
- The `.control` is used to contro the simulation.
- The command `tran 0.1ns 0.2us` tells the simulator to perform a transient analysis with a given sampling rate (here 0.1ns) for a given amount of time (here 0.2us).
- The `plot v(6) v(Clk)+2` tells the simulator what signals to plot.
- The control block ends with the `.endc`.
- ALL SPICE files ends with `.end`.

## Part 10: PLL components circuit simulations

- We run the SPICE file in the work directory to get the simulation output.
- We open the terminal in the work_dir and then type this command.  
  `ngspice FD.cir`
- Output generated is :  
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/FreqDiv%20Simulation.png)
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/FreqDiv.png)

- We perform similar simulations for Charge Pump, VCO and PFD.
- For charge pump, we perform simulation both in the absence and presence of an input signal. This helps us identify leakage current.

- For Charge Pump with no input:

### **Charge Pump Simulation FILE**
```
.include sky130nm.lib

xm43 3 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=5.4u 
xm44 out downb 3 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm31 out up 7 0 sky130_fd_pr__nfet_01v8 l=150n w=420n
xm32 7 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=5.4u

xm33 2 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm34 8 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm35 9 down 3 1 sky130_fd_pr__pfet_01v8 l=150n w=5400n 
xm36 9 9 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm37 10 10 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm38 10 upb 7 0 sky130_fd_pr__nfet_01v8 l=150n w=5400n

xm39 1 down downb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm40 0 down downb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm41 1 up upb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm42 0 up upb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 
v1 1 0 1.8	
v2 up 0 0 
*PULSE 0 1.8 1n 6p 6p 100ns 200ns
v3 down 0 0

r1 out rc 200
c1 rc 0 64f
c2 out 0 10f

.ic v(out) = 0
.ic c(out) = 0
.control
tran 1ns 20us
plot v(out) C(out)
*plot v(6) V(Clk)+2
* v(D) v(Clk) v(6)
.endc

.end
```
- `.ic` command is used to specify the initial conditions of a signal. Here, it is used to specify the initial condition, before the charging or discharging that happens in the charge pump.
- V2 voltage source is specified as the up signal with 0V and V3 voltage source is specified as the down signal with 0V.
- Simulation performed in work_dir using `ngspice ChargePump.cir` command.

![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/Charge%20Pump%20Simulation.png)

- Small leakage current observed.
- It grows linearly with time. The slope indicates the charging happening when up and down signals are given 0V. 

- For Charge Pump with step input:

### **Charge Pump Simulation FILE**
```
.include sky130nm.lib

xm43 3 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=5.4u 
xm44 out downb 3 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm31 out up 7 0 sky130_fd_pr__nfet_01v8 l=150n w=420n
xm32 7 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=5.4u

xm33 2 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm34 8 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm35 9 down 3 1 sky130_fd_pr__pfet_01v8 l=150n w=5400n 
xm36 9 9 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm37 10 10 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm38 10 upb 7 0 sky130_fd_pr__nfet_01v8 l=150n w=5400n

xm39 1 down downb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm40 0 down downb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm41 1 up upb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm42 0 up upb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 
v1 1 0 1.8	
v2 up 0 PULSE 0 1.8 1n 6p 6p 100ns 200ns
v3 down 0 0

r1 out rc 200
c1 rc 0 64f
c2 out 0 10f

.ic v(out) = 0
.ic c(out) = 0
.control
tran 1ns 20us
plot v(out) C(out)
*plot v(6) V(Clk)+2
* v(D) v(Clk) v(6)
.endc

.end
```
- Simulation Results :
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/CP%20simulation%20for%20Pulse%20input.png)

### **3-Stage VCO Simulation FILE**

```
.include sky130nm.lib

xm1 10 16 3 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm2 3 16 9 9  sky130_fd_pr__nfet_01v8 l=150n w=420n

xm3 10 3 4 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm4 4 3 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm5 10 4 12 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm6 12 4 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm11 10 12 13 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm12 13 12 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm13 10 13 14 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm14 14 13 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm15 10 14 15 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm16 15 14 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm17 10 15 16 10 sky130_fd_pr__pfet_01v8 l=150n w=2400n
xm18 16 15 9 9 sky130_fd_pr__nfet_01v8 l=150n w=1200n

xm7 10 5 1 1 sky130_fd_pr__pfet_01v8 l=150n w=1080n
xm8 5 5 1 1 sky130_fd_pr__pfet_01v8 l=150n w=840n
xm9 5 in 0 0 sky130_fd_pr__nfet_01v8 l=150n w=840n
xm10 9 in 0 0 sky130_fd_pr__nfet_01v8 l=150n w=1080n

xm19 1 16 11 1 sky130_fd_pr__pfet_01v8 l=150n w=1080n
xm20 11 16 0 0 sky130_fd_pr__nfet_01v8 l=150n w=540n

*c1 11 0 10f
v1 1 0 1.8
v2 in 0 0.6


.control
tran 0.1ns 0.5us
plot v(in) v(11)
*setplot tran1
*linearize v(14)
*set specwindow=blackman
*fft v(14)
*dc v2 0 1.2 0.01
*plot mag(v(14))
.endc
.end

```
- Simulation result:
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/VCO%20simulation.png)

- Here the input control signal is given by V2 source and by adjusting this control voltage we can observe change in the operating frequency of the VCO.

### **PFD Simulation FILE**

```
.include sky130nm.lib

xm1 1 2 3 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm2 0 2 3 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm3 3 Clkb 4 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm4 3 Clk 4 0 sky130_fd_pr__nfet_01v8 l=150n w=840n 

xm7 1 4 5 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm8 0 4 5 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm9 5 Clk 6 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm10 5 Clkb 6 0 sky130_fd_pr__nfet_01v8 l=150n w=640n 

xm11 1 6 2 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm12 0 6 2 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm13 1 Clk Clkb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm14 0 Clk Clkb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

v1 1 0 1.8
v2 Clk 0 PULSE 0 1.8 1n 6p 6p 5ns 10ns

c1 6 0 10f
.control
tran 0.1ns 0.2us
plot v(6) v(Clk)+2
.endc

.end

```

- Simulation results:
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/PD.png)
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/PFD%20simulation.png)

## Part 11: Steps to combine PLL sub-circuits and PLL full design simulation

- The various individual SPICE files need to be combined to create a PLL.
- This is done by creating a new file,'PLL_PreLay.cir' in the work_dir.
- Instances of smaller circuits are created usking 'subckt' keyword. We give a name to the block and then specify the input-output pins. 
  Example: subcircuit for CP is defined as `.subckt cp up down out`. 
- To instantiate a sub-circuit, we use "xx" indicating that it is a sub-circuit of general type.
- In instantiation, we mention the sub-circuit name last while during the definition, sub-circuit name is given first and then the pin names are given.
- Similarly, we instantiate all other component circuits and add the loop filter.
- V1 voltage pulse is the input reference signal and the period of this signal is "80ns" (or 12.5MHz) signal.
- Proper naming of the nets and proper assignment of the values for each parameter like width, length, etc. is important as one wrong naming will cause an error in the spice simulation.

### **Simulation FILE**

```
.include sky130nm.lib

xx1 Clk_Ref Clk_Out_by_8 up down pd
xx2 up down VCtrl cp

*Loop Filter
r1 VCtrl rc1 490
c1 rc1 0 355f
r2 rc1 rc2 490
c2 VCtrl 0 350f
r3 rc2 rc3 490
c3 rc3 0 345f
 
xx3 rc3 Clk_Out vco

xx4 Clk_Out Clk_Out_by_2 fd
xx5 Clk_Out_by_2 Clk_Out_by_4 fd
xx6 Clk_Out_by_4 Clk_Out_by_8 fd

v1 Clk_Ref 0 PULSE 0 1.8 0 6ps 6ps 40ns 80ns

.ic v(VCtrl) = 0
.ic v(Clk_Out_by_2) = 0
.ic v(Clk_Out_by_4) = 1.8
.ic v(Clk_Out_by_8) = 0
.control
tran 0.1ns 180us
plot v(Clk_Ref) v(Clk_Out_by_8) v(Clk_Out_by_4)+2 v(Clk_Out_by_2)+4 v(Clk_Out)+6 v(up)+8 v(down)+10 v(VCtrl)+12
.endc

*PFD
.subckt pd Clk1 Clk2 up down 
xm1 1 clk1 3 1 sky130_fd_pr__pfet_01v8 l=150n w=640n 
xm2 3 clk1 4 0 sky130_fd_pr__nfet_01v8 l=150n w=1800n
xm3 4 clk2 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm4 1 clk2 6 1 sky130_fd_pr__pfet_01v8 l=150n w=640n 
xm5 6 clk2 7 0 sky130_fd_pr__nfet_01v8 l=150n w=1800n
xm6 7 clk1 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm7 8 clk1 3 0 sky130_fd_pr__nfet_01v8 l=150n w=2400n 
xm8 clk1 clk1 8 1 sky130_fd_pr__pfet_01v8 l=150n w=640n

xm11 upb 8 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm12 upb 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm15 up upb 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm16 up upb 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n
  
xm9 9 clk2 6 0 sky130_fd_pr__nfet_01v8 l=150n w=2400n
xm10 clk2 clk2 9 1 sky130_fd_pr__pfet_01v8 l=150n w=640n

xm13 downb 9 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm14 downb 9 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm17 down downb 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm18 down downb 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n


*output cap
*c1 up 0 6f
*c2 down 0 6f

v1 1 0 1.8
.ends pd


*CP
.subckt cp up down out
xm43 3 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=18u 
xm44 out downb 3 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm31 out up 7 0 sky130_fd_pr__nfet_01v8 l=150n w=420n
xm32 7 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=4.8u

xm33 2 2 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm34 8 8 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm35 9 down 3 1 sky130_fd_pr__pfet_01v8 l=150n w=5400n 
xm36 9 9 0 0 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm37 10 10 1 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm38 10 upb 7 0 sky130_fd_pr__nfet_01v8 l=150n w=5400n

xm39 1 down downb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm40 0 down downb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm41 1 up upb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm42 0 up upb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

*r1 out rc 200
*c1 rc 0 8f

v1 1 0 1.8
.ends cp


*VCO
.subckt vco in 17
xm1 10 16 3 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm2 3 16 9 9  sky130_fd_pr__nfet_01v8 l=150n w=420n

xm3 10 3 4 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm4 4 3 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm5 10 4 12 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm6 12 4 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm11 10 12 13 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm12 13 12 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm13 10 13 14 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm14 14 13 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm15 10 14 15 10 sky130_fd_pr__pfet_01v8 l=150n w=420n
xm16 15 14 9 9 sky130_fd_pr__nfet_01v8 l=150n w=420n

xm17 10 15 16 10 sky130_fd_pr__pfet_01v8 l=150n w=2400n
xm18 16 15 9 9 sky130_fd_pr__nfet_01v8 l=150n w=1200n

xm7 10 5 1 1 sky130_fd_pr__pfet_01v8 l=150n w=1080n
xm8 5 5 1 1 sky130_fd_pr__pfet_01v8 l=150n w=840n
xm9 5 in 0 0 sky130_fd_pr__nfet_01v8 l=150n w=840n
xm10 9 in 0 0 sky130_fd_pr__nfet_01v8 l=150n w=1080n

xm19 1 16 11 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm20 11 16 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm21 1 11 17 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm22 17 11 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

*c1 11 0 24f
v1 1 0 1.8
.ends vco


*FD
.subckt fd Clk 10

xm1 1 2 3 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm2 0 2 3 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm3 3 Clkb 4 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm4 3 Clk 4 0 sky130_fd_pr__nfet_01v8 l=150n w=840n 

xm7 1 4 5 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm8 0 4 5 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm9 5 Clk 6 1 sky130_fd_pr__pfet_01v8 l=150n w=420n 
xm10 5 Clkb 6 0 sky130_fd_pr__nfet_01v8 l=150n w=640n 

xm11 1 6 2 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm12 0 6 2 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm13 1 Clk Clkb 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm14 0 Clk Clkb 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 

xm15 7 6 1 1 sky130_fd_pr__pfet_01v8 l=150n w=720n 
xm16 7 6 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n

xm19 1 7 10 1 sky130_fd_pr__pfet_01v8 l=150n w=720n
xm20 10 7 0 0 sky130_fd_pr__nfet_01v8 l=150n w=360n 


*c1 7 0 18f
v1 1 0 1.8
.ends fd
.end

```

- In ideal case, the blue feedback signal will overlap the red reference signal perfectly.
- If we take the root-mean-square (RMS) of the variation of the output signal, we get the Jitter (RMS) value which denotes the phase noise.
- It is important to note that this blue signal is in-fact created by the VCO.
- Simulation takes long time because of the complexity of the circuit.
- Results :
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/PLL.png)
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/PLL%20sim1.png)
- Zooming in:
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/PLL%20sim2.png)
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/PLL%20sim3.png)

## Part 12: Troubleshooting steps

- Observe the kinds of issue faced.
- Debug individual components fully before trying to debug the combined simulation.
- Check if any signals are coming flat or if the simulation is crashing. If this is the case then check if all the connections are done properly. Also check if there are any issues like wrong naming, capitalization issues or parameter value issues.
- If the signals are right but the mimicking is not happening then verify the following:
    - For what range of frequencies is the VCO working properly: Is our required output frequency range lying in the VCO's working range.
    - Is the Phase Frequency Detector able to detect the differences: If the phase difference is very small, the PFD might not be able to detect it.
    - Is the rate of Charge Pump output charging and discharging fast: Is it too fast or too slow? Is there too much fluctuations in charging or discharging? This means that the transistor sizing is the thing to pay attention to. Check the response of the CP when 0V is given as the input. If it is still charging then the charge leakage is the issue.
    - Whether the loop filter values are working out: This can be found out using the thumb rules.

## Part 13: Layout design

- To open Magic, we need to open the Terminal in the work_dir and then type `magic -T sky130A.tech`.
- The 2 following windows pop-up.
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/Magic%201.png)
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/Magic%202.png)

- The way to draw here in magic is first to make a box and then fill it with a material.
- By left clicking, we fix the left bottom corner of the box.
- By right clicking, we fix the right top corner of the box.
- If we hover upon a layer (layers panel is present on the right hand side of the window), we can see the name of the layer on the top right corner of the screen.
- By middle clicking on a layer, the box gets filled by the selected layer.
- Materials needed for the transistors:
    - P-diffusion for the PMOS and N-diffusion for the NMOS.
    - For the gate, polysilicon layer is needed.
- DRC error means that there is a size issue or a closeness issue. To know what exactly the issue is, select some part of the error region and press the "?" button on the keyboard and then the error will show up on the "magic command window".
- Before creating a PMOS, we must create an N-Well region and then place the PMOS over it.
- To copy a transistor, make a box around the transistor and press "A" button on the keyboard. Now, place the cursor where we wish to copy it and press "C" button. If we press the "M" button then it becomes the move operation.
- For placing Vdd and ground, place the metal1 layer.
- To connect two transistors, use the loacal interconnect layer (locali) like a wire.
- To connect two layers, look for contact layers in the tray. They are represented with a cross symbol.
- As long as we do not connect a contact, two different layers will not touch even if they overlap.
- If we get a DRC error at this point it means that either the size of the contact is too small or the region of metal1 and local interconnect around the contact is not enough.
- To create a label, draw a line around the edge of the layer that we want to label. A line is drawn by making a box of zero thickness. Type the command `label name` in the magic command window. Name can be any name to be used as label.
- To make a port, draw a box around the label and type `port make` in the magic command window.
- We need to make ports because when we extract the parasitics from our design, the input and output ports will automatically have these names as we have labelled them as ports.

## Part 14: Layout Walkthrough

- Open the magic (.mag) files for the previously designed circuits:
    - Frequency Divider
    - Phase Frequency Detector
        - On the right side, there are two similar drawings on the top and on the bottom, which are additional buffers required for getting full swing.
    - Charge Pump
        - Top most long transistor is just for enabling or disabling the charge pump.
        - Right below it is the upper current source. This much difference in the size of the transistor for the current source is to allow maximum current for the charging and discharging process.
        - Two inverters on the left create the UPz and the DOWNz signals (UPz = up bar and DOWNz = down bar or their inverted variants).
    - Voltage Controlled Oscillator
        - There are seven inverters to reduce the range of frequencies that we are dealing with.
        - There is an additional inverter at the end which helps to obtain a full swing for the output.
        - At the top there is a small PMOS that acts as an enable or disable for the VCO.

### Assessment Question

- Copy the "FD.mag" file in the directory where the technology file "sky130A.tech" is placed.
- Open the Terminal in this directory.
- Open the FD layout file. Type `magic -T sky130A.tech FD.mag` in the Terminal.
- The layout looks something like this.

![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/Magic%20FD.png)

- Now left-click on the bottom left-corner of the layout and right-click on the top right-corner of the layout.
- Go to the Magic Terminal and type `box` command, which gives the area.

![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/FD%20area.png)
- The area in sq. um is given as 29.70 and hence it is the answer.


## Part 15: Parasitic Extraction

- Open the magic file of the circuit that is to be extracted.
- Press "I" button on the keyboard. It selects the whole design. Then, press "X" button to see the complete layout.
- In the magic command window type `extract all`. This extracts the layout connectivity information into a ".ext" file.
- Generally, if there are any warnings at this point, they would be because of wrong connections or short circuits or etc. But these are warnings and need not be errors.
- Now, we need to convert the ".ext" file to a ".spice" file to use for simulations.
- In the magic command window type `ext2spice cthresh 0 rthresh 0` and then type `ext2spice`.
- Here the cthreshold 0 and rthreshold 0 setting is given to tell magic that if any amount of capacitive or resistive effect is present, then we want to extract it.
- In the spice we find a `.option scale=10000u`. Every parameter in the spice file is multiplied by this scale. However, in our case the scale is 10n, not 10000u.

### Assessment question

- Open the "FD.mag" file in the directory where the technology file "sky130A.tech" is placed using the command `magic -T sky130A.tech FD.mag` in the Terminal.
- Now the magic file should open. When it opens press the "I" and "X" button on the keyboard. Then, we follow the requisite steps described above to extract parasitics from this circuit, which is stored in the 'FD.spice file'. We open this file to check the number of parasitic caoacitors. 
- We observe that there are capacitors from C0 to C42. So, there are a total of 43 capacitors present.

## Part 16: Post Layout simulations

- We extract the spice file from the "PFD.mag" file, as described previously.
- Enter the directory where "sky130.lib" and "PFD.spice" are saved using the `cd` command.
- Type the command `nano PFD_postlay.cir` in the terminal. This open a file which we can edit.
- We include "sky130.lib" and "PFD.spice" files.
- We add reference clock and voltage sources and perform transient simulation. The resulting file looks like this:

![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/PFD%20postlay.png)

- Post-Layout Parameters:
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/Post%20Layout%20parameters.png)

- To simulate the circuit after layout we need to write the following code in the file "PLL_PostLay.cir":

```
* SPICE3 file created from PFD.ext - technology: sky130A
.include sky130nm.lib
.option scale=0.01u

XM1000 VDD a_7_412# a_460_368# VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=1664.03 pd=142.146 as=2232 ps=206
XM1001 GND a_7_412# a_460_368# GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=842.4 pd=91.8 as=1116 ps=134
XM1002 a_264_92# Clk2 a_208_92# GND sky130_fd_pr__nfet_01v8 w=240 l=15
+  ad=7920 pd=546 as=5314.29 ps=321.143
XM1003 VDD Clk2 a_208_92# VDD sky130_fd_pr__pfet_01v8 w=65 l=15
+  ad=1502.25 pd=128.326 as=2145 ps=196
XM1004 Up a_460_368# GND GND sky130_fd_pr__nfet_01v8 w=48 l=15
+  ad=1392 pd=154 as=1123.2 ps=122.4
XM1005 GND a_264_92# a_485_83# GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=842.4 pd=91.8 as=1116 ps=134
XM1006 a_151_92# Clk_Ref GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1044 pd=74 as=842.4 ps=91.8
XM1007 VDD a_264_92# a_485_83# VDD sky130_fd_pr__pfet_01v8 w=72 l=15
+  ad=1664.03 pd=142.146 as=2232 ps=206
XM1008 Down a_485_83# VDD VDD sky130_fd_pr__pfet_01v8 w=96 l=15
+  ad=2880 pd=252 as=2218.71 ps=189.528
XM1009 a_7_412# Clk_Ref a_7_356# GND sky130_fd_pr__nfet_01v8 w=240 l=15
+  ad=7920 pd=546 as=5314.29 ps=321.143
XM1010 Up a_460_368# VDD VDD sky130_fd_pr__pfet_01v8 w=96 l=15
+  ad=2880 pd=252 as=2218.71 ps=189.528
XM1011 VDD Clk_Ref a_7_356# VDD sky130_fd_pr__pfet_01v8 w=65 l=15
+  ad=1502.25 pd=128.326 as=2145 ps=196
XM1012 Down a_485_83# GND GND sky130_fd_pr__nfet_01v8 w=48 l=15
+  ad=1392 pd=154 as=1123.2 ps=122.4
XM1013 Clk_Ref Clk_Ref a_7_412# VDD sky130_fd_pr__pfet_01v8 w=65 l=15
+  ad=2145 pd=196 as=2145 ps=196
XM1014 a_7_299# Clk2 GND GND sky130_fd_pr__nfet_01v8 w=36 l=15
+  ad=1044 pd=74 as=842.4 ps=91.8
XM1015 a_208_92# Clk2 a_151_92# GND sky130_fd_pr__nfet_01v8 w=180 l=15
+  ad=3985.71 pd=240.857 as=5220 ps=370
XM1016 Clk2 Clk2 a_264_92# VDD sky130_fd_pr__pfet_01v8 w=65 l=15
+  ad=2145 pd=196 as=2145 ps=196
XM1017 a_7_356# Clk_Ref a_7_299# GND sky130_fd_pr__nfet_01v8 w=180 l=15
+  ad=3985.71 pd=240.857 as=5220 ps=370
C0 Down Up 0.00fF
C1 a_264_92# VDD 0.13fF
C2 a_208_92# a_485_83# 0.02fF
C3 a_460_368# Clk_Ref 0.00fF
C4 Clk2 a_485_83# 0.06fF
C5 a_7_412# VDD 0.14fF
C6 Up VDD 0.13fF
C7 a_460_368# a_485_83# 0.01fF
C8 Down VDD 0.56fF
C9 a_264_92# a_208_92# 0.49fF
C10 a_264_92# Clk2 0.27fF
C11 a_264_92# Clk_Ref 0.01fF
C12 a_7_412# a_208_92# 0.01fF
C13 a_7_412# Clk2 0.01fF
C14 a_7_412# Clk_Ref 0.19fF
C15 a_264_92# a_460_368# 0.00fF
C16 a_7_412# a_7_356# 0.49fF
C17 a_264_92# a_485_83# 0.37fF
C18 a_7_412# a_460_368# 0.34fF
C19 Down Clk2 0.02fF
C20 a_7_412# a_485_83# 0.00fF
C21 a_460_368# Up 0.16fF
C22 Up a_485_83# 0.00fF
C23 a_208_92# VDD 0.27fF
C24 Clk2 VDD 0.08fF
C25 VDD Clk_Ref 0.20fF
C26 Down a_485_83# 0.16fF
C27 a_7_356# VDD 0.15fF
C28 a_7_412# a_264_92# 0.03fF
C29 a_460_368# VDD 0.20fF
C30 VDD a_485_83# 0.31fF
C31 a_208_92# Clk2 0.05fF
C32 a_208_92# Clk_Ref 0.01fF
C33 a_7_412# Up 0.01fF
C34 Clk2 Clk_Ref 0.11fF
C35 Down a_264_92# 0.01fF
C36 a_7_356# a_208_92# 0.02fF
C37 a_7_356# Clk2 0.01fF
C38 a_7_356# Clk_Ref 0.10fF
C39 Up GND 0.22fF
C40 VDD GND 4.13fF
C41 a_485_83# GND 0.34fF
C42 a_264_92# GND 0.52fF
C43 a_208_92# GND 0.10fF
C44 a_7_356# GND 0.34fF
C45 a_460_368# GND 0.34fF
C46 a_7_412# GND 0.65fF

v1 VDD GND 1.8
v2 Clk_Ref 0 PULSE 0 1.8 0n 6p 6p 40ns 80ns
v3 Clk2 0 PULSE 0 1.8 1n 6p 6p 40ns 80ns

.control
tran 0.1ns 0.5us
plot v(Clk_Ref) v(Clk2) v(Up)+2 v(Down)+4
.endc

.end
```

- Simulation results:

![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/Post%20Layout%20Sim%201.png)
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/Post%20Layout%20Sim%202.png)

## Part 17: Steps to combine layouts

- Open Magic using the command `magic -T sky130A.tech` in the Terminal.
- Use 'place instance' options present in 'cells'. The 'place instace' is used to place one or more pre-created circuit layouts in the Magic window.
- Press the "I" button and then the "X" button on the keyboard to open the circuit or to make the circuit visible.
- Now open all layouts in the same window.
- Make quick connections using the wire tool. To access the wire tool press the space bar once and to exit the wire tool press the space bar three more times.
- Extend the layers to make connections between the subcircuits.

In the final PLL design:
- On the right hand side, there is a multiplexer. It is kept to select between the charge pump or an external source to control the VCO.
- On the top left, there are three frequency dividers. The output from them is the feed-back loop and it goes to the PFD on the bottom left.
- The PFD also has the reference clock as input. PFD converts the inputs into the Up or Down signals that control the charge pump at the bottom right.
- The output voltage generated by the charge pump in turn controls the VCO and generates the output that we want.
- After Charge Pump, we must place the loop filter.

- Extract spice netlist and perform the final post layout simulation.
- Save that file as a "GDS" file.
    - The GDS file is the complete layout information that we can send to the fabrication centre to fabricate the IC.
    - To write GDS file, go to the file menu and choose the "Write GDS" option.
    - This gives us our final IC design in ".gds" format.

- The final PLL layout looks as follows:

![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/PLL%20Final%20Layout.png)

## Part 18: Tapeout theory

- Tapeout means to send our final design to the Fab, after 'preparing' it.
- Steps required in preparing the chip:
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/Tapeout.png)

**Caravel**
Caravel is a template SoC for Efabless Open MPW and chipIgnite shuttles based on the Sky130 node from SkyWater Technologies.
![](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/blob/main/Labs%20Simulation%20Results/Caravel.png)

- The user project area we see is the area available to us to place our design.
- This is the IC that finally gets fabricated with our design inside it.
- During the first shuttle, the process was to place and design inside the user project area and then meet the connections from the design ports to the user project area pins and then merge that user project area into the Caravel SoC.

## Part 19: Tapeout labs

- Download the layout file for the analog user project area.
- Once downloaded, extract it to the directory of your choice.
- Now, open it with magic and the technology file sky130A.tech
- Place the design in the user project area and make the connections with the pins.
- It is important to not that one must not move any of the pins that they have given from their location. We only use the pins that we need and connect our design to them.
- At the bottom of the user project area are the wishful ports.
- Along the left of the user project area are the input-output ports and some power ports like Vdd and Vss.
- Along the right of the user project area are a few more input-output ports and power ports like Vccd, Vssd, Vcca and Vssa.
- At the top of the user project area are the analog input-output pins.

- In our design, we have five pins:
    - Enable pins for CP and VCO.
    - Reference clock input pin.
    - Output clock pin.
    - VCO direct input pin.
- The enable pins are connected to the digital input-output pins.
- Reference clock input pin and output clock pin are also digital and so we connect them to the digital input-output pins.
- VCO direct input pin is control voltage pin of analog nature. So, we need to connect it to an analog input-output pin.
- Considering this scenarion, we place our design at the top-right corner and make the connections to the pins using wire tool and contact layers.

# Conclusion

The 2-Day Workshop on Phase-Locked Loop(PLL) IC design introduces its participants to the basics of IC design process, which is particularly important for students and professionals, who intend to pursue a career in Physical Design. The Workshop had a good balance between the theory and practicals. The lectures were short and informative and the labs were sufficiently challenging. The inclusion of assessments at the end was also a good for revision. The overall rigour and depth of the Workshop is highly appreciable.

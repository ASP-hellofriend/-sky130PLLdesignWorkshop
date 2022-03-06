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
- [References](https://github.com/ASP-hellofriend/-sky130PLLdesignWorkshop/edit/main/README.md#references)

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

![]()
![]()
![]()
![]()
![]()
![]()

## Part 10: PLL components circuit simulations

![]()
![]()
![]()
![]()
![]()
![]()

## Part 11: Steps to combine PLL sub-circuits and PLL full design simulation

![]()
![]()
![]()
![]()
![]()
![]()

## Part 12: Troubleshooting steps

![]()
![]()
![]()
![]()
![]()
![]()

## Part 13: Layout design

![]()
![]()
![]()
![]()
![]()
![]()

## Part 14: Layout Walkthrough

![]()
![]()
![]()
![]()
![]()
![]()

## Part 15: Parasitic Extraction

![]()
![]()
![]()
![]()
![]()
![]()

## Part 16: Post Layout simulations

![]()
![]()
![]()
![]()
![]()
![]()

## Part 17: Steps to combine layouts

![]()
![]()
![]()
![]()
![]()
![]()

## Part 18: Tapeout theory

![]()
![]()
![]()
![]()
![]()
![]()

## Part 19: Tapeout labs

![]()
![]()
![]()
![]()
![]()
![]()

# Conclusion

The 2-Day Workshop on Phase-Locked Loop(PLL) IC design introduces its participants to the basics of IC design process, which is particularly important for students and professionals, who intend to pursue a career in Physical Design. The Workshop had a good balance between the theory and practicals. The lectures were short and informative and the labs were sufficiently challenging. The inclusion of assessments at the end was also a good for revision. The overall rigour and depth of the Workshop is highly appreciable.

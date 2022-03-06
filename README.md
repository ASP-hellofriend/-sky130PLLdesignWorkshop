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
## Part 1: Introduction to PLL
## Part 2: Introduction to Phase Frequency Detector
## Part 3: Introduction to Charge Pump
## Part 4: Introduction to Voltage Controlled Oscillator and Frequency Divider
## Part 5: Tool Setup and Design Flow
## Part 6: Introduction to PDK, specifications and pre-layout circuits
## Part 7: Circuit design simulation tool - Ngspice Setup
## Part 8: Layout design tool - Magic Setup

# Day 2: PLL Labs and post-layout simulations
## Part 9: PLL components circuit design
## Part 10: PLL components circuit simulations
## Part 11: Steps to combine PLL sub-circuits and PLL full design simulation
## Part 12: Troubleshooting steps
## Part 13: Layout design
## Part 14: Layout Walkthrough
## Part 15: Parasitic Extraction
## Part 16: Post Layout simulations
## Part 17: Steps to combine layouts
## Part 18: Tapeout theory
## Part 19: Tapeout labs

# Conclusion

# Field-Oriented Control of an Induction Motor in PSCAD

## Introduction
This project implements a simulated induction motor drive system in PSCAD using Field-Oriented Control (FOC). The control system is designed to decouple the torque- and flux-producing current components of the induction motor, allowing independent control of the machine in the rotating dq reference frame.

The simulation provides a configurable environment for analysing induction motor behaviour under different operating conditions. Key motor parameters, controller values, and operating setpoints may be adjusted by the user. During runtime, the model allows observation of internal electrical node values, control signals, and system outputs to support validation and analysis of the implemented control strategy.

---

## Repository Contents
This repository contains the core PSCAD files required to run the simulation:

- `.pscx` – Main PSCAD simulation case containing the full induction motor drive system
- `.psmx` – Supporting PSCAD library/module file containing reusable subsystem and control blocks

Both files are required to run the project and should remain within the same repository structure to ensure correct loading of model dependencies.

---

## Software Requirements
To run the simulation, the following software is required:

- PSCAD x64
- A compatible Fortran compiler configured within PSCAD

The project was developed and tested using PSCAD x64.

---

## How to Run
1. Open PSCAD x64.
2. Load the `.psmx` supporting module file first.
3. Open the `.pscx` main simulation case second.
4. Confirm that all referenced subsystem blocks load correctly.
5. Compile the project using the PSCAD build/compile function.
6. Run the simulation using the PSCAD run command.

The `.psmx` file should be loaded before the `.pscx` case, as the main simulation may reference supporting subsystem definitions contained within the module file.

---

## Outputs
The simulation allows observation of key internal and output variables during runtime, including:

- three-phase inverter output waveforms
- d-axis current response (`Id`)
- q-axis current response (`Iq`)
- electrical angle response
- PWM switching behaviour
- induction motor dynamic response

Small graph components connected to electrical nodes may be copied into the graph display window prior to runtime in order to visualise selected node values during simulation.

---

## Notes and Limitations
This project was developed as a simulation-based implementation of induction motor field-oriented control in PSCAD.

The current control loops and subsystem behaviour were implemented and validated successfully. Full speed-loop validation remains limited by dq-axis alignment sensitivity and is identified as an area for future refinement.

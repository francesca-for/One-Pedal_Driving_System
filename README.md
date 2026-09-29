# One-Pedal Driving System (Model-Based Software Design)

This repository contains the models, control logic, test harnesses, and laboratory reports developed for an automotive **One-Pedal Driving System (OPDS)**.  
The project was developed for the **Model-Based Software Design** course at **Politecnico di Torino** (Department of Control and Computer Engineering - DAUIN, Prof. Massimo Violante).

## Overview

The project explores the **Model-Driven Engineering (MDE)** workflow applied to an automotive One-Pedal Driving control unit, following the **V-Model** development life cycle:

- **Functional Safety (ISO 26262):** Item definition, Hazard Analysis and Risk Assessment (HARA), Automotive Safety Integrity Level (ASIL) allocation, and Functional Safety Concept (FSC) definition.
- **System and Control Modeling:** Dynamic vehicle plant simulation and supervisory control logic designed with **MATLAB**, **Simulink**, and **Stateflow** in compliance with **MAAB** (MathWorks Automotive Advisory Board) modeling guidelines.
- **Verification and Validation (X-in-the-Loop):**
  - **MIL (Model-in-the-Loop):** Closed-loop co-simulation of the controller and vehicle plant models in Simulink using Test Harnesses, assertion blocks, and model coverage analysis (Decision, Condition, and MCDC coverage).
  - **SIL / PIL / HIL (Software/Processor/Hardware-in-the-Loop):** Verification of generated C/C++ code and target deployment on microcontrollers (**Arduino**).
- **Automatic Code Generation:** Generation of MISRA-compliant and portable C/C++ code using **Simulink Coder** and **Embedded Coder** with discrete fixed-step solvers.

---

## Repository Structure

```text
One-Pedal_Driving_System/
├── Lab_1_Kit/           # Lab 1: Functional Safety (ISO 26262), Item Definition, and HARA
├── Lab_2_Kit/           # Lab 2: Plant & Controller modeling, Test Harness, and MIL simulation
├── Lab_3_Kit/           # Lab 3: Functional Safety Concept, Test Cases, and Model Coverage
├── Lab_4_Kit/           # Lab 4: Target deployment on Arduino and hardware integration
├── .gitignore           # Git ignore patterns for MATLAB/Simulink artifacts
└── README.md            # Project documentation
```

### Key Contents

- **Lab_1_Kit:** Assessment matrix (`Assessment matrix.xlsx`) and the laboratory report (`MBSD_Lab 1.pdf`) covering system boundaries, malfunction analysis, and HARA.
- **Lab_2_Kit & Lab_3_Kit:**
  - Closed-loop simulation models: `plant.slx`, `controller.slx`, `harness.slx`, `test1.slx`
  - Model initialization script: `init_fn.m`
  - Enumeration definitions: `TransmissionState.m`
  - Technical reports & documentation: `MBSD_Lab 2.pdf`, `MBSD_Lab 3.pdf`, `Explanations.pdf`
- **Lab_4_Kit:**
  - Arduino hardware integration models: `controller.slx`, `controller_Arduino_ok.slx`
  - Hardware simulation project: `Lab4.sim1`
  - Initialization scripts: `init_fn.m`, `TransmissionState.m`
  - Laboratory report: `MBSD_Lab 4.pdf`

---

## Requirements and Tools

- **MATLAB** (R2022b or newer recommended)
- **Simulink** and **Stateflow**
- **Simulink Test** and **Simulink Coverage**
- **Simulink Coder** and **Embedded Coder**
- **Simulink Support Package for Arduino Hardware** (required for Lab 4)

---

## Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/francesca-for/One-Pedal_Driving_System.git
   cd One-Pedal_Driving_System
   ```

2. **Initialize the workspace:**
   Open MATLAB, navigate to the specific lab directory (e.g., `Lab_2_Kit/`, `Lab_3_Kit/`, or `Lab_4_Kit/`), and run the initialization files to load calibration parameters and data types:
   ```matlab
   run('init_fn.m');
   ```

3. **Run simulations and code generation:**
   - Open `harness.slx` or `test1.slx` to execute MIL closed-loop test scenarios.
   - Open `controller.slx` to inspect the state machine and generate C/C++ code via **Embedded Coder** (press `Ctrl+B` / `Cmd+B`).
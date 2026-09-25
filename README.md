# Model-Based Software Design

This repository contains the models, scripts, and laboratory reports developed for the **Model-Based Software Design** course at **Politecnico di Torino** (Department of Control and Computer Engineering - DAUIN, Prof. Massimo Violante).

## Overview

The project explores the **Model-Driven Engineering (MDE)** workflow applied to automotive and embedded control systems, following the **V-Model** development life cycle:

- **Functional Safety (ISO 26262):** Item definition, Hazard Analysis and Risk Assessment (HARA), and Functional Safety Concept definition.
- **System and Control Modeling:** Design of dynamic plant models and control/supervisory algorithms using **MATLAB**, **Simulink**, and **Stateflow** in compliance with **MAAB** (MathWorks Automotive Advisory Board) guidelines.
- **Verification and Validation (X-in-the-Loop):**
  - **MIL (Model-in-the-Loop):** Co-simulation of the controller and plant models in Simulink using Test Harnesses and model coverage analysis.
  - **SIL / PIL / HIL (Software/Processor/Hardware-in-the-Loop):** Verification of generated C/C++ code and deployment of the control algorithm on target hardware (**Arduino**).
- **Automatic Code Generation:** Generation of portable and target-specific code using **Simulink Coder** and **Embedded Coder** with discrete fixed-step solvers.

---

## Repository Structure

```text
Model_Based_Software_Design/
├── Lab_1 Kit/           # Lab 1: Functional Safety (ISO 26262), Item Definition, and HARA
├── Lab_2_kit/           # Lab 2: Plant and Controller modeling, Test Harness, and MIL simulation
├── Lab_3 Kit/           # Lab 3: Functional Safety Concept, Test Cases, and Model Coverage
└── Lab4_Kit/            # Lab 4: Target deployment on Arduino and hardware integration
```

### Key Contents

- **Lab 1 Kit:** Assessment matrix (`Assessment matrix.xlsx`), laboratory report (`MBSD_Lab 1.pdf`), and project notes (`ReadMe.docx`).
- **Lab 2 & Lab 3 Kits:** Closed-loop simulation models (`plant.slx`, `controller.slx`, `harness.slx`, `test1.slx`), enumerated state definitions (`TransmissionState.m`), workspace initialization scripts (`init_fn.m`), and laboratory reports (`MBSD_Lab 2.pdf`, `MBSD_Lab 3.pdf`, `Explanations.pdf`).
- **Lab 4 Kit:** Hardware deployment models for **Arduino** (`controller.slx`, `controller_Arduino_ok.slx`), hardware simulation project (`Lab4.sim1`), initialization files (`init_fn.m`, `TransmissionState.m`), and laboratory report (`MBSD_Lab 4.pdf`).

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
   git clone <YOUR_REPOSITORY_URL>
   cd Model_Based_Software_Design
   ```

2. **Initialize the environment:**
   Open MATLAB, navigate to the desired laboratory directory (`Lab_2_kit/`, `Lab_3 Kit/`, or `Lab4_Kit/`), and run `init_fn.m` and `TransmissionState.m` to load the required parameters and enumerated data types into the workspace.

3. **Run simulations and code generation:**
   Open the Simulink models (`harness.slx`, `test1.slx`, or `controller.slx`) to execute closed-loop simulations or generate C/C++ code via **Embedded Coder**.
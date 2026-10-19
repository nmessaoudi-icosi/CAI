# SI-HCPN Framework for AI-Assisted Smart-Grid Control

This repository is the companion repository for the manuscript:

**A Slot-Indexed Hierarchical Colored Petri Net Framework for Invariant-Based Execution and Auditing of AI-Assisted Smart-Grid Control**

prepared for submission to **Computing and Informatics**.

## Authors

- Nabil Messaoudi
- Hamdane Mohamed El Kamel
- Malik Mohamed Mahdi
- Souidi Mohammed El Habib
- Haouassi Hicham

Corresponding author:

**Nabil Messaoudi**  
ICOSI Laboratory  
Abbès Laghrour University of Khenchela, Algeria  
Email: messaoudi.nabil@univ-khenchela.dz

---

## Overview

The work presents a **Slot-Indexed Hierarchical Colored Petri Net (SI-HCPN)** framework for the execution and auditing of AI-assisted smart-grid supervisory control.

The framework considers three reference supervisory adapters:

1. **Reactive-only**
2. **Random-Forest-guided deterministic allocation (RF-only)**
3. **Random-Forest-assisted terminal action-value selection (RF+AV)**

The advisory components do not directly modify the shared grid state.  
The **SI-HCPN remains the execution authority**, responsible for authorization, feasibility constraints, state updates, trace generation, and runtime auditing.

The framework combines:

- hierarchical Colored Petri Net execution;
- formal structural and record-level properties;
- Random Forest peak-risk assessment;
- terminal action-value decision support;
- independent runtime stress monitoring;
- execution-trace reconciliation;
- KPI evidence-admission rules.

---

## Repository Status

At the initial manuscript submission stage, this public repository contains:

- this `README.md`;
- a video demonstration of the SI-HCPN framework execution.

The complete reproducibility package is not publicly deposited at this stage.

It can be provided to the **editor and reviewers upon request during peer review** and can be added to this repository if requested as part of the editorial evaluation process.

---

## Execution Demonstration

The repository includes a video demonstration of the framework execution:

`SI-HCPN_execution_demo.mp4`

The demonstration illustrates the execution environment and the interaction between the SI-HCPN supervisory model and its advisory components.

The video is intended to provide a direct view of the operational workflow described in the manuscript.

---

## Framework Architecture

The framework follows the general supervisory chain:

```text
SI-HCPN state
      |
      v
RF risk request
      |
      v
Independent stress monitoring
      |
      v
Optional action-value request
      |
      v
SI-HCPN authorization
      |
      v
Execution and shared-state update
      |
      v
Trace reconciliation
      |
      v
Evidence admission

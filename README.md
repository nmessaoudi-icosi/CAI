# SI-HCPN Framework for AI-Assisted Smart-Grid Control

This repository is the companion repository for the manuscript:

**A Slot-Indexed Hierarchical Colored Petri Net Framework for Invariant-Based Execution and Auditing of AI-Assisted Smart-Grid Control**

prepared for submission to **Computing and Informatics**.

## Interactive SI-HCPN Observatory

**[Open the Observatory on GitHub Pages →](https://nmessaoudi-icosi.github.io/CAI/)**

The **ICOSI SI-HCPN Observatory** is an English-language, browser-based companion dashboard for inspecting execution outputs and comparing AI-assisted peak detection and mitigation results. It supports six-model comparison campaigns, with **Random Forest (RF) retained as the valid reference model**, and can be reused for subsequent tests.

The Observatory analyzes exported results. It **does not execute CPN Tools, retrain AI models, or replace the SI-HCPN execution and auditing framework**.

### What the Observatory provides

| Area | Capabilities |
| --- | --- |
| Import and inspection | Import CSV, JSON or ZIP outputs for one execution at a time; inspect run details, file names and import warnings. |
| Classification | Compare supplied precision, recall, F1 and ROC–AUC scores. |
| Grid operation | Inspect available demand and supply histories, reported peak counts and the final grid state. |
| Mitigation | Display verified discharge and load-shifting totals by asset; show ENS and OME when supplied. |
| Comparison and ranking | Filter by model, scenario and CPN step count; adjust criterion weights and inspect the explicit ranking methodology. |
| Reporting and reuse | Export a PDF through browser printing; export and restore JSON sessions for subsequent analysis. |

### Scientific interpretation

- **Missing is not zero.** Unavailable or uncalculated indicators are shown as **N/A** and are not estimated.
- ENS, OME and peak counts are displayed only when provided. Raw cumulative discharge records are not automatically summed; verified per-asset totals are required.
- Rankings use weighted min–max normalization and require complete data for every active criterion. Ranking is disabled for fewer than two eligible runs or differing scenarios or step counts.
- Matching scenario and step count alone does not establish a controlled comparison. Seeds, workloads, configurations and metric definitions must also be checked before drawing scientific conclusions.
- **Demo data are fictional interface examples**, not experimental evidence from the manuscript. A displayed ranking is not a claim of statistically established model superiority.

### Getting started

1. Open the [live Observatory](https://nmessaoudi-icosi.github.io/CAI/).
2. Select **Import a run**, choose the execution outputs, and specify the model, scenario and CPN step count.
3. Review import warnings and missing indicators before interpreting the charts or rankings.
4. Use **Runs → Export session** to back up your work, or **PDF report → Save as PDF** to export the active view.

Imports are processed locally in the browser. Imported results are **not automatically uploaded to GitHub** or shared with other visitors. Sessions are browser-specific; export them before changing devices or domains.

**The CPN Tools model (`.cpn`) is not included in the Observatory and is not published as part of this dashboard.** It can remain on the researcher's computer.

See the [Observatory guide](observatoire/README.md) for supported file schemas, local development and deployment instructions.

---

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

This public repository provides:

- this scientific overview;
- the [interactive Observatory](https://nmessaoudi-icosi.github.io/CAI/) and its source code in [`observatoire/`](observatoire/);
- the GitHub Pages deployment workflow;
- access to the execution demonstration through the repository's [Releases](https://github.com/nmessaoudi-icosi/CAI/releases).

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
```

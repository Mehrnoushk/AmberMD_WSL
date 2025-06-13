# AmberMD_WSL

[AmberMD_WSL jupyter notebook](https://github.com/Mehrnoushk/AmberMD_WSL/blob/main/AmberMD_WSL.ipynb) aims to assist win running **Amber "Simple Simulation of Alanine Dipeptide" tutorial** using AmberTools on Windows Subsystem for Linux (WSL)  
(derived from the official tutorial [“Simple Simulation of Alanine Dipeptide”](https://ambermd.org/tutorials/basic/tutorial0/)).

---

## Overview

- **What is simulated**  
  - A short explicit-solvent molecular dynamics (MD) simulation of **acetyl‑alanine‑N‑methylamide** (“ACE‑ALA‑NME”, a capped alanine dipeptide) in a solvated water box.
  - Follows a standard pipeline: *build → solvate → minimize → heat → production MD → analyze (e.g., RMSD)*.

- **Based on**  
  - The Amber tutorial originally built for Linux (Amber v20+), adapted here for **WSL/Ubuntu + AmberTools**, using **sander** (or optionally **pmemd**) as the MD engine.

---

## Notebook Structure

1. **System Setup**  
   Generate `tleap.in` to load FF19SB + water model, build the peptide, solvate, and save `parm7`/`rst7`.

2. **MD Input Preparation**  
   Write the three `.in` files based on tutorial:  
   - `01_Min.in` : energy minimization  
   - `02_Heat.in` : heating  
   - `03_Prod.in` : production run

3. **Running MD on WSL**  
   Execute minimization, heating, and production stages using `sander` (or `pmemd`), with proper use of relative directories.

4. **Analysis**  
   Automate trajectory analysis with `cpptraj` and visualize results: RMSD, energies, etc.
---

## Prerequisites

- WSL installed (Ubuntu recommended)
- `conda` environment with AmberTools (`ambertools25+`)
- `sander` (or `pmemd`) working in `$PATH`

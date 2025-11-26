# 📡 Cassegrain Reflector Electromagnetic Solver

A MATLAB project to compute the **far-field radiation pattern** of a **Cassegrain dual-reflector antenna** using a combination of **Physical Optics (PO)** and **Physical Theory of Diffraction (PTD)**.

---

## Overview

This solver calculates the far field of Cassegrain antennas with high accuracy. It supports:

- Dual-reflector geometry (main parabolic reflector + subreflector)  
- Gaussian beam or imported near-field feed excitations  
- Physical Optics for surface currents  
- PTD for edge diffraction contributions  
- Co- and cross-polarization using **Ludwig’s 3rd definition**  
- Custom surface meshing of both reflector surfaces  

The project contains around 65 MATLAB functions, structured to work together through a main driver function.

## Problem Solved

The solver addresses the radiation pattern computation of a Cassegrain reflector system, which includes:

- Generating the surface mesh of both main and subreflectors  
- Evaluating the feed field (Gaussian beam or external near-field data)  
- Computing induced currents on the subreflector reflector surface (PO)
- Illuminates the main reflector using the subreflector currents  
- Accounting for edge diffraction (PTD)  
- Calculating co- and cross-polar far-field components over user-defined angular cuts
- Accounts for subreflector blockage and edge effects  

It outputs the complete far-field pattern for multiple phi-cuts and customizable theta resolution.

---

## Inputs

The user provides:

- **Reflector geometry**: dimensions and relative positions of main and subreflectors  
- **Feed characteristics**: Gaussian beam parameters (beamwidth, taper, total power) or external near-field file  
- **Output configuration**: angular range, number of points per cut, number of phi-cuts, polarization format, and plotting options  

All inputs are specified through MATLAB structs.

## Outputs

The solver returns:

- Co and Cross-polarized far field patterns
- Rectangular Plots of the far-field over the specified cuts  
- Maximum gain and beam characteristics  
- `.mat` file with all computed data  
- Screen Output of All Solver Data Recorded
---

## Examples\Demo

A short video demonstrating the solver running in MATLAB, including far-field calculations and plotting:

- [CassegrainSolverDemo.mp4](examples/CassegrainSolverDemo.mp4)


## How to Run

Run the main solver function in MATLAB:

```matlab
[E, out_grid, solverData] = cassegrain_reflector(freq, Reflectors, Feeder, OutputFormat);


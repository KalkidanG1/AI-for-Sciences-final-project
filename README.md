## **Project Overview**
This repository contains the work for the course project **"Physics-Informed  Identification  of Surface vs. Bulk Degradation  Kinetics in Swelling Hydrogels"**, the code is designed to train **"multi-physics inelastic Constitutive Artificial Neural Network (Mi-CANN) on rubber data under multiple loading modes (uniaxial tension, pure shear, and equibiaxial tension)"**, and to generate the figures shown in the associated work.

Page for accessing the website: 

### **Team Members**
- **Kalkidan Gebru**

### **Course Information**
- **Course:** AI for Science
- **Semester:** Fall 2025
- **Institution:** University of Michigan

1. File Overview

rubber_cann
Main script / entry point to run the CANN model on the rubber data.

Sets up the problem (hyperparameters, paths, options).

Loads the data (via the helper file).

Builds and trains the network.

Saves results needed for plotting.

plotting_rubber
Script used to generate plots and figures from the trained model:

Reads the saved predictions and experimental data.

Plots stress–stretch curves for each loading mode (UT, PS, ET).

Writes the figures to files (e.g., .png or .pdf) in the output directory.

models
Module that defines the model architecture and related routines:

Network layout for the CANN (layers, nodes, activations).

Functions to evaluate the free energy and stresses.

Any helper functions to modify or extend the model.

continuummechhelper
Helper file for continuum mechanics–related tasks and data I/O:

Imports and formats the experimental data files.

Provides functions for computing invariants, stresses, etc.

Collects common utilities used by the main script and model code.

Data files: *_UT*, *_PS*, *_ET*
Experimental data for the different loading modes:

UT – Uniaxial Tension

PS – Pure Shear

ET – Equibiaxial Tension

These files typically contain stretch and stress values used for training and validation.

2. How to Run

Check dependencies
Make sure you have the required programming environment and libraries installed
(e.g., Python/MATLAB + relevant packages, depending on this code base).

Place data files
Ensure all UT, PS, and ET data files are in the expected data/ or project directory,
and that continuummechhelper points to the correct paths.

Run the main script
Execute:

If using Python:

python rubber_cann.py


If using MATLAB:

run('rubber_cann.m')


This will train the model (and/or load existing weights, depending on how the script is set up)
and save predictions for plotting.

Generate figures
After running the main script, execute:

If using Python:

python plotting_rubber.py


If using MATLAB:

run('plotting_rubber.m')


This will produce the stress–stretch plots for UT, PS, and ET.

3. Typical Workflow

Edit models if you want to change the CANN architecture or activation functions.

Run rubber_cann to train / retrain the model on the UT, PS, and ET data.

Use plotting_rubber to visualize the results and export the figures.

Use continuummechhelper whenever you need to extend the data import or continuum-mechanics utilities.

4. Notes

UT/PS/ET data files must match the format expected in continuummechhelper.

If paths or filenames change, update them in rubber_cann and continuummechhelper.

This code is designed to be a minimal, reproducible example of a CANN trained on rubber data for multiple loading modes.

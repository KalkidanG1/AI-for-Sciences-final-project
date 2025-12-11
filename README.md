# Physics-Informed Identification of Surface vs. Bulk Degradation Kinetics in Swelling Hydrogels

## **Project Overview**
This repository contains the work for the course project **“Physics-Informed Identification of Surface vs. Bulk Degradation Kinetics in Swelling Hydrogels.”**  
The code trains a **multi-physics inelastic Constitutive Artificial Neural Network (Mi-CANN)** on rubber experimental data across **three loading modes**:

- **Uniaxial Tension (UT)**
- **Pure Shear (PS)**
- **Equibiaxial Tension (ET)**

The repository also includes scripts for generating all figures presented in the final report and presentation.

Website link: *(add your link here if applicable)*

---

## **Team Members**
- **Kalkidan Gebru**

## **Course Information**
- **Course:** AI for Science  
- **Semester:** Fall 2025  
- **Institution:** University of Michigan  

---

## **1. File Overview**

### **`rubber_cann`**
Main entry point for running the Mi-CANN model on the rubber dataset.

- Sets hyperparameters, training options, and directory paths  
- Loads UT/PS/ET experimental data  
- Builds and trains the Mi-CANN network  
- Saves prediction files for later plotting  

---

### **`plotting_rubber`**
Script for generating the figures shown in the report.

- Loads saved model predictions and raw experimental data  
- Produces stress–stretch plots for UT, PS, and ET  
- Saves figures (e.g., `.png`, `.pdf`) to the output directory  

---

### **`models/`**
Module defining the Mi-CANN architecture and constitutive routines.

- Neural network layout (layers, activations, parameters)  
- Free energy and stress evaluation functions  
- Extendable helper utilities for custom model behavior  

---

### **`continuummechhelper`**
Continuum mechanics helper utilities.

- Loads and formats experimental data  
- Computes invariants, stresses, and other mechanics quantities  
- Shared functions used across scripts  

---

### **`data/`**
Contains experimental rubber datasets:

- `*_UT` — Uniaxial Tension  
- `*_PS` — Pure Shear  
- `*_ET` — Equibiaxial Tension  

---

## **2. How to Run**

### **Step 1 — Check Dependencies**
Ensure the required environment is installed:  
Python or MATLAB + relevant scientific computing libraries.

---

### **Step 2 — Place Data Files**
Confirm all UT, PS, and ET files are in the expected `data/` directory.  
Paths should match those in `continuummechhelper`.

---

### **Step 3 — Train the Model**

#### **Python**
```bash
python rubber_cann.py

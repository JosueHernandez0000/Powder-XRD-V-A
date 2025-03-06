# XRD Data Analysis 
# Automated, fast and simple


## Overview

This repository contains a Python-based standalone executable for analyzing powder X-ray Diffraction (XRD) data. The program focuses on visualization of the experimental data, peak identification and deconvolution of overlapping peaks. The code supports multi-peak fitting using Pseudo-Voigt functions and provides tools to handle overlapping peaks and perform automated peak characterization.

### Table of Contents
1. [Overview](#overview)
2. [Functionality](#functionality)
3. [Main Outputs](#Outputs)
4. [How to Use](#how-to-use)
5. [Technical Details](#technical-details)
6. [Limitations and Areas for Improvement](#limitations-and-areas-for-improvement)
7. [Contribution](#contribution)
8. [License](#license)
9. [Contact](#contact)

---
## 2. Functionality
1. **Plots XRD data**: Plots experimental data, must be in .xy format.
2. **Removes background if needed**: Automatically detects background and lets the user decide whether to remove background or not
3. **Plots XRD with selected reference patterns**: Plots a selected reference pattern in the same plot as the sample XRD for a quick comparison. 
4. **Peak identification**: Automatically detects main peaks in the diffractogram.
5. **Peak deconvolution**: Performs a peak deconvolution around each major peak to identify any overlapping peaks.
6. **FWHM calculation** : Calculates the Full Width at Half Maximum (FWHM) of each epak in the diffractogram.

## 3. Main Outputs
The code is meant to be a quick and easy way to plot and visualize experimental XRD data. The main outputs of the program are the following plots:
1. **XRD spectra with background**
2. **XRD spectra without background**
3. **Plots XRD with selected reference patterns**
4. **All peaks in the diffractogram**
5. **All peak deconvolutions**: The plots show the multipseudo voigt fit/deconvolution with FWHM of the peaks

### Example Outputs

- XRD spectrum with detected peaks:
<div align="center">
   <img src="plots/XRD_plots/XRD with peak detection.png" alt="XRD with peak detection" width="500">
</div>

- Example of Reference pattern obtained from the Crystallographic Open Database (COD):
<div align="center">
   <img src="plots/reference_plots/reference pattern of CsBr.png" alt="SnBr2_ref" width="500">
</div>

- XRD spectrum with selected references for quick comparison:
<div align="center">
   <img src="plots/XRD_plots/Sample and multiple references example.png" alt="Sample XRD with reference patterns" width="500">
</div>

- Example of a peak deconvolution:
<div align="center">
   <img src="plots/deconvolution_plots/4 peak deconvolution example.png" alt="Sample XRD with reference patterns" width="500">
</div>

## 4. How to Use
Follow these steps to use the software:
1. **Clone the repository to your own machine**
2. **Make sure the following foler structure is followed**:
```
Powder XRD VA 1.0.0/
├── reference_patterns/  
│   └── reference_patterns.xlsx   # Stores the crystallographic information of the reference patterns             
│
├── plots/                        # Stores the generated plots
│   ├── deconvolution_plots/            
│   ├── peak_plots/ 
│   ├── reference_plots/          
│   └── XRD_plots/
|
├── raw_xy_data/
│   └── your_data.xy       # XRD data to be analyzed
|
├── README.txt             # Documentation for the project.
├── LICENSE     
└── Powder_XRD_VA.exe      # Standalone .exe file
```

3. **Run the .exe file**
4. **Open the plots in the plots folder**


## 5. Technical Details

### Peak Detection
- Initial peak detection is performed using a fixed value of sensitivity

### Profile Fitting
- Fitting is performed using:
    - **Pseudo-Voigt Model:** Combination of Lorentzian and Gaussian profiles, adaptable for asymmetric peaks.


### Convolution and Deconvolution
- Multi-peak deconvolution is done through a multi-pseudo voigt approximation.
- Peaks are iteratively fitted, with R² optimization to ensure the best-fit parameters.


## 6. Limitations and Areas for Improvement

### Current Limitations
- Peak deconvolution may fail if data is too noisy (usually the case in low intensity peaks)
- Handling of very closely spaced peaks (less than instrument resolution) can be challenging.
- Limited support for asymmetric or skewed peaks outside of Pseudo-Voigt modeling.


### Potential Enhancements

- Let the user fine tune parameters of the analysis

---

## 7. Contribution

Contributions, feature requests, and bug reports are welcome. Please open an issue or submit a pull request.

---

## 8. License

This project is licensed under the MIT License — see the `LICENSE` file for details.

---

## 9. Contact

For questions, feature requests, or collaboration opportunities, please contact the developer.

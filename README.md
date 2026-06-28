# Spectroscopic Suite Analyzer Pro 2026 V.1

**Advanced Spectroscopy Analysis Software**

Copyright (c) 2026 Ahmed Hassan Ibrahim Faraag. All rights reserved.

---

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [Chemical Databases](#chemical-databases)
4. [Themes](#themes)
5. [Installation](#installation)
6. [Usage Guide](#usage-guide)
7. [Spectroscopy Techniques](#spectroscopy-techniques)
8. [File Formats](#file-formats)
9. [Copyright](#copyright)
10. [Building & Setup](#building--setup)

---

## Overview

Spectrum Pro Analyzer is a comprehensive, professional-grade spectroscopy analysis application built with PyQt6. It provides advanced spectral processing, multi-spectrum overlay, compound database search across 27 chemical databases, dynamic theming with 43+ color schemes, and support for 15 spectroscopy techniques.

---

## Features

### Spectral Processing
- **Baseline Correction**: ALS (Asymmetric Least Squares) baseline removal
- **Smoothing**: Savitzky-Golay filter with configurable window and polynomial order
- **Transformations**: Derivative (1st/2nd), Absorbance/Transmittance conversion, FFT, Inverse FFT
- **Arithmetic**: Scale, offset, normalize, add/subtract/multiply/divide spectra
- **Deconvolution**: Gaussian/Lorentzian/Voigt peak deconvolution

### Peak Analysis
- **Peak Detection**: Automatic peak finding with configurable threshold and minimum distance
- **Peak Fitting**: Gaussian, Lorentzian, and Voigt profile fitting
- **Peak Annotation**: Customizable peak labels with style cycling (Normal/Bold/Italic/Bold Italic), color, and size controls
- **Peak/Description Combos**: Separate Peak Operations (Add/Remove/Move/Adjust Peak, Normal) and Description Operations (Add/Delete/Move Description, Normal) combos
- **Sensitivity Slider**: Adjustable peak detection sensitivity (1-100) in toolbar
- **▲/▼ Stepper Controls**: All parameters controllable with up/down stepper buttons:
  - Style: cycles Normal → Bold → Italic → Bold Italic
  - Font Size: 6–36 range
  - Apex Size: 4–30 range
  - Apex Font Size: adjustable
  - Line Width: adjusts ±0.5
  - Detection Sensitivity: adjusts ±5
  - Apex Color: cycles through preset colors
  - Apex Shape: cycles through marker shapes

### Multi-Spectrum Overlay
- Load multiple spectra into one panel with customizable colors and line styles
- Side-by-side overlay and library tabs in the controls panel
- Overlay peak detection with automatic and manual modes
- Save/load overlay projects (`.zsoverlay` format)
- Legend with visibility toggle for each spectrum

### Multi-Figure Layout
- Single, Stacked, Side by Side, Separate, and Plateau layout modes
- Configurable figure counts
- Stack offset slider for separating spectra vertically

### Compound Search & Library
- Search 27 chemical databases simultaneously:
  PubChem, ChEMBL, EPA CompTox, NIST, SDBS, MassBank, Raman Open Database, etc.
- Local SQLite database with 81 pre-loaded compounds
- Compound information display with clickable hyperlinks
- Spectral data overlay from search results

### Export & Reporting
- **Image Export**: PNG, JPG, SVG, PDF with DPI control (72-1200)
- **Office Export**: Word (.docx), Excel (.xlsx), PowerPoint (.pptx)
- **Professional Word Report**: Auto-generated analysis report
- **Data Export**: CSV, JSON format support
- **Plot Digitizer**: Extract data points from published spectra images

### Dynamic Themes
- 43+ built-in color themes including Light, Dark, Ocean, Forest, Neon, and more
- Custom theme creation with color pickers
- Ribbon theme styles: Classic, Modern, Office 365, Fluent, Material, Slate, Cosmic

---

## Chemical Databases

The software searches across 27 chemical databases:

| Category | Databases |
|----------|-----------|
| **Public Chemistry** | PubChem, ChEMBL, ChemSpider, NIST Chemistry WebBook |
| **Spectral** | SDBS, MassBank, Raman Open Database, NIST MS, NIST IR |
| **Environmental** | EPA CompTox, EPA ToxCast, TOXNET |
| **Pharmaceutical** | DrugBank, ChEBI, BindingDB |
| **Materials** | Materials Project, Crystallography Open Database, COD |
| **Other** | Wikipedia Chemistry, ChemIDplus, HMDB, BMRB, PPDB, CACTUS, UniChem, InChI, RSC, ACS |

---

## Themes

Available theme categories:
- **Standard**: Light, Dark, Light Contrast, Dark Contrast
- **Accent Variants**: Blue, Green, Orange, Purple, Red, Teal (Light/Dark)
- **Specialized**: Ocean, Forest, Neon, Solarized, Monokai, Nord
- **Professional**: Modern Light, Modern Dark, Advanced, Slate
- **Custom**: Create your own with the Dynamic Theme panel

---

## Installation

### Quick Start

1. Install Python 3.9 or later from https://www.python.org
2. Run `setup.bat` (Windows) or install manually:
   ```bash
   pip install -r requirements.txt
   ```
3. Run `run.bat` (Windows) or:
   ```bash
   python run.py
   ```

### First Run - Activation

1. On first launch, the Welcome Screen shows your **Machine ID**
2. Use the **Keygen Tool** (`keygen.bat` or `keygen_tool.py`) to generate a serial number from your Machine ID
3. Enter the serial number in the Welcome Screen to activate
4. After activation, the software runs for lifetime — no expiration

### Desktop Shortcut

After installation, create a desktop shortcut:
```bash
python create_shortcut.py
```

Or on Windows, use the Inno Setup installer (`installer/setup.iss`) which automatically creates shortcuts.

---

## Usage Guide

### Loading Data
- File → Open: Load spectrum files (CSV, TXT, DAT, JDX, SPA, SPC, etc.)
- Drag and drop files onto the application window
- File → Load Example Data: Quick access to sample FTIR, Raman, UV-Vis, and NMR spectra

### Peak Detection
1. Use the Detection tab in the control panel
2. Click "Auto-Detect (Technique-Based)" for automatic detection
3. Adjust sensitivity with the slider or ▲/▼ buttons
4. Use "Detect + Add Description" to auto-label peaks

### Manual Peaks
1. Select "Add Peak" from the Peak Operations combo in the toolbar
2. Click on the spectrum to add a peak marker
3. Use "Move Peak" to reposition peaks by dragging
4. Use "Add Description" to annotate peaks

### Styling
- Layout tab controls title style, apex size, line width, figure colors
- Style ▲/▼ cycles through Normal → Bold → Italic → Bold Italic
- Font Size ▲/▼ adjusts title font size (6-36)
- Right-click on the plot for context menu options

### Overlay Mode
1. Load multiple spectra using File → Open
2. Use the Overlay tab to manage spectra visibility and colors
3. Stack offset slider separates spectra vertically
4. Overlay peak detection works on individual selected spectra

---

## Spectroscopy Techniques

Supported techniques with auto-detected axis labels:

| Technique | X-Axis | Y-Axis |
|-----------|--------|--------|
| FTIR | Wavenumber (cm⁻¹) | Transmittance (%) |
| UV-Vis | Wavelength (nm) | Absorbance |
| Raman | Raman Shift (cm⁻¹) | Intensity (a.u.) |
| 1H NMR | Chemical Shift (ppm) | Intensity |
| 13C NMR | Chemical Shift (ppm) | Intensity |
| Mass Spec | m/z | Relative Intensity |
| XRD | 2θ (degrees) | Intensity |
| Fluorescence | Wavelength (nm) | Intensity |
| CD | Wavelength (nm) | Ellipticity |
| XPS | Binding Energy (eV) | Intensity |
| EPR | Magnetic Field (G) | Intensity |
| AES | Kinetic Energy (eV) | Intensity |
| AAPS | Angle (degrees) | Intensity |
| ERP | Magnetic Field (G) | Intensity |
| Other | X | Y |

---

## File Formats

### Input Formats
- CSV, TXT, DAT (comma/tab/space/semicolon separated)
- JCAMP-DX (.jdx, .dx)
- SPA, SPC (proprietary binary formats)
- MOL, SDF (chemical structure files)
- Image files (for plot digitizer: PNG, JPG, BMP, TIFF)

### Output Formats
- PNG, JPG, SVG, PDF (image export with DPI control)
- DOCX (Word document with report)
- XLSX (Excel spreadsheet)
- PPTX (PowerPoint presentation)
- CSV, JSON (data export)
- .zsoverlay (overlay project files)

---

## Copyright

Copyright (c) 2026 Ahmed Hassan Ibrahim Faraag. All rights reserved.

This software is the exclusive property of the copyright holder and is protected by international copyright laws. Unauthorized reproduction, distribution, or modification is strictly prohibited.

The software requires a machine-specific serial number for activation.

---




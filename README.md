# internal-waves / finescale estimations
Code for finescale estimation of shear, strain, and abyssal mixing parameters in the Eastern Mediterranean Sea. Scientific reference: manuscript 
"Bottom topography effects on abyssal diapycnal mixing in the Eastern Mediterranean Sea", Florian Kokoszka¹, Stefania Sparnocchia², Davide Cavaliere³, Vincenzo Artale³, Mireno Borghini⁴, Beatrice Giambenedetti⁵˒⁶, Federico Falcini³*
¹ Stazione Zoologica Anton Dohrn, Naples, Italy
² CNR–ISMAR, Trieste, Italy
³ CNR–ISMAR, Rome, Italy
⁴ CNR–ISMAR, Lerici, Italy
⁵ Università di Roma Tor Vergata, Rome, Italy
⁶ INGV, Rome, Italy
Abstract
The abyssal Ionian Sea is a deep region of interest for the entire ocean circulation of the Mediterranean Sea, since it plays an important role in the ventilation processes of the whole basin. Here we investigate spatial patterns of diapycnal mixing due to internal waves, over the bottom of the Ionian sub-basin. To identify regional features of the internal wave field in terms of vertical shear and strain, we analyze LADCP and CTD profiles, measured across the basin in 2007, covering various seafloor morphologies (shelf, shelf break, and abyssal plain). Our results show that increasing seafloor roughness reduces the variability of the shear-to-strain ratio, a pattern also influenced by correlations between slope and roughness. Roughness appears to constrain waves toward higher frequencies, with high shear-to-strain ratios associated with lower frequencies and flatter propagation angles, and low ratios linked to higher frequencies and steeper beams. Spectral analyses indicate that rougher regions enhance strain variance at small vertical scales while reducing shear variance at larger scales, leading to flatter shear spectra in the low-wavenumber band. Intermediate roughness further enhances energy at shorter scales, and strong roughness consistently elevates strain spectra. Together, these findings suggest that roughness redistributes energy from large-scale shear toward small-scale strain, fundamentally altering the balance of internal wave energy across scales. These results expand our insights for 3D ocean circulation models, providing useful knowledge for ad hoc parameterization of mixing that should capture abyssal, internal wave–driven processes in the Mediterranean Sea.
Keywords
Ionian Sea; diapycnal mixing; internal waves; shear and strain ratio; turbulent kinetic energy

Purpose
This repository reproduces the main calculations of the paper: shear and strain spectra, Rω, estimates of εiw and Kiw in the GM/Kunze framework, and analyses of the relationship with bathymetry (slope, GEBCO roughness). Outputs include intermediate CSV files and the main figures.

Structure
Main notebook: 
- iwgm_shear_strain-CLEAN.ipynb. It orchestrates the workflow, computes spectra, Rω, εiw, Kiw.
Supporting notebooks executed with %run:
– mc_startup.ipynb: initialization, imports, global parameters.
– myfunctions.ipynb, myfunctions_plus.ipynb, myfunctions_iw.ipynb, myfunctions_turner_dd.ipynb: function libraries (spectral methods, finescale diagnostics, Turner angle/double diffusion, plotting).
– bathy_slope_roughness.ipynb: slope and roughness calculations from GEBCO (variance and mean slope at ~10 km scale).
– data_KM3_Pi23.ipynb: import and preprocessing of CTD/LADCP 2007 dataset (stations, near-bottom segments, N², LADCP errors).

Dependencies
Python 3.10+. numpy, pandas, scipy, matplotlib, scikit-learn, mixsea (GM functions: GM_model, gm_shear_variance, gm_strain_variance). Optional: cartopy/pyproj for mapping. Install via pip install -r requirements.txt.

Input data
Calibrated CTD profiles and processed LADCP (LDEO IX.13) with error estimates per bin, GPS positions, depths. GEBCO 15″ grid covering the Ionian Sea for slope/roughness. Paths are set in mc_startup.ipynb and data_KM3_Pi23.ipynb. 

How to reproduce
Open iwgm_shear_strain-CLEAN.ipynb.
Adjust data paths in mc_startup and data_* notebooks.
Run cells.

License and citation
Add an open license (e.g. MIT) and a CITATION.cff. After Zenodo archiving, include the DOI and cite the associated preprint/article once public.

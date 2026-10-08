# LAG-L
LAG-L is a Lagrangian Lorentz approach to resolving particle fluxes at GEO. LAG-L models Earth's magnetosphere macroscopically using discrete protons that propagate according to BATSRUS MHD fields.

List of what the files are and what they do:
  
- 3d__var_1_e20251231-0xx000-000.out: Output MHD fields from BATSRUS. The time xx is replaced with the hour and time, so 1:30 UTC is represented by ...013000-000.out.
- 5D_distribution.ipynb: Main simulation code
- dn_magn-l2-avg1m_g18_d20251231_v2-0-4.nc: magnetic Bz readings from GOES-18 from 00:00 - 02:00 UTC
- Earth.jpg: Earth image for plotting
- goes18_ephemeris_ssc_20250101_v01.cdf: Satellite ephemeris of GOES-18 from 00:00 - 02:00 UTC
- IGRF_Baked_Float.pkl: File containing all the IGRF data required to run the code (not important to the actual calculations, but still needs to be edited out of the code)
- igrf14coeffs.txt: IGRF 14 coefficients given in a text file
- IGRFGridValues.ipynb: file that creates IGRF_Baked_Float.pkl
- Interpolators_4D_float32.pkl: Interpolated MHD fields given in space and time in single-precision. The file is too large to share here unless you have UF OneDrive access: ([https://uflorida-my.sharepoint.com/:u:/g/personal/nfurioso_ufl_edu/IQAY3wIA3EzZQqUEbxXs3ORuAS8TBdG-MAR1nlz6BCdtaVY?e=wlXyTw](https://uflorida-my.sharepoint.com/:u:/g/personal/nfurioso_ufl_edu/IQAY3wIA3EzZQqUEbxXs3ORuAS8TBdG-MAR1nlz6BCdtaVY?e=wbHh1L)); otherwise, it must be created using PrecomputeGridValuesTime.ipynb
- LICENSE: Apache License
- ops_seis-l1b-mpsl_g18_d20251231_v0-0-0: MPS-LO GOES-18 readings from 00:00-02:00 UTC
- plot_all3.ipynb: plotting file that requires outputs from all three solvers (LAG-GC, LAG-L, and SLAG-V). However, it can be edited to just require output from a single solver. Most up-to-date version of the plots
- plot_lorentz.ipynb: Old version of the plotting code that plots LAG-GC alone
- PrecomputeGridValuesTime.ipynb: File that creates Interpolators_4D_Float32.pkl
- README: READ ME file
- sci_mpsh-l2-avg1m_g18_d20251231_v2-0-2: MPS-HI GOES-18 readings from 00:00-02:00 UTC


Make sure to adjust the datetime (sim_start_time) across all files to match your date of interest. Everything is currently set up to begin on December 31st, 2025 at 00:00 and end at 02:00 UTC (MAX_TIME). All the associated parameters are taken from that time as well.

This includes the ephemeris of the GOES-18 satellite, the Kp index (KP_INDEX), and solar parameters (N_sw_input, V_sw_input, Bz_input). Each of these parameters is hardcoded and needs to be adjusted to match any new date other than December 31st, 2025, 00:00 to 02:00.

The number of initial particles needs to be adjusted as well (N_INITIAL_ACTIVE).

If initializing your own MHD run, make sure to use the proper values to initialize that simulation according to the date and time you want to measure.

All files that are needed are included in the repository here. You will need to update the paths for yourself locally to match where you have the data stored in the code

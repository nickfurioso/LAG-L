# LAG-L
LAG-L is a Lagrangian Lorentz approach to resolving particle fluxes at GEO. LAG-L models Earth's magnetosphere macroscopically using discrete protons that propagate according to BATSRUS MHD fields.

Make sure to adjust the datetime (sim_start_time) across all files to match your date of interest. Everything is currently set up to begin on December 31st, 2025 at 00:00 and end at 02:00 UTC (MAX_TIME). All the associated parameters are taken from that time as well.

This includes the ephemeris of the GOES-18 satellite, the Kp index (KP_INDEX), and solar parameters (N_sw_input, V_sw_input, Bz_input). Each of these parameters is hardcoded and needs to be adjusted to match any new date other than December 31st, 2025, 00:00 to 02:00.

The number of initial particles needs to be adjusted as well (N_INITIAL_ACTIVE).

If initializing your own MHD run, make sure to use the proper values to initialize that simulation according to the date and time you want to measure.

All files that are needed are included in the repository here. You will need to update the paths for yourself locally to match where you have the data stored in the code

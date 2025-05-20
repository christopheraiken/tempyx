# tempyx

Bare bones jupyter alternative for finding and tracking lows in healpix data, to avoid having to export to netcdf and use tempestExtremes (etc).

It's very rough - needs some love from someone who knows weather systems and python - but the underlying algorithm seems to be pretty quick.

The strategy is to first locate local minima in surface pressure, which can be done quickly in healpix.  Then apply whatever filters to just these points.

The detection and tracking is all done in healpix pixels.  You convert to lat/lon at the end.

The way I've done it is to detect and track at low zooms and then analyse at high zooms.  You can then adjust the track using the hi res data if necessary.  It should also work for detection straight at high zoom.

![image](https://github.com/user-attachments/assets/43a91719-947d-474e-b247-3d175ba39642)


The test data was produced by the UK Met Office.  Their blurb: 
A group of experiments have been conducted using the Met Office Unified Model (MetUM) with a focus on the DYAMOND-3 period (Jan 2020-Feb 2021). While this experiments include standalone explicit convection global simulations we have also developed a cyclic tropical channel and include limited area model simulations to build our understanding of how resolving smaller-scale processes feeds back on to the large-scale atmospheric circulation.

simulation : 
glm.n2560_RAL3p3

simulation_description :
The MetUM uses a regular lat-lon grid, for our explicit convection global simulations we use the N2560 global grid (~5 km in mid-latitudes) and the latest regional atmosphere-land configuration (RAL3p3). As detailed in Bush et al 2025 the RAL3p3 includes significant developments over previous configurations including the CASIM double-moment cloud microphysics scheme and the bi-modal large-scale cloud scheme. Crucially for DYAMOND-3 simulations the parameterisation of convection is not active and this science configuration has been developed and evaluated targetting high-resolution (regional) simulations."

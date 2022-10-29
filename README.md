# satellite-dodging-ApJL
Code repository for the paper "Satellite Constellation Avoidance with the Rubin Observatory Legacy Survey of Space and Time", J. Hu, M. Rawls, P. Yoachim, Z. Ivezić, ApJL. 

## Abstract: 
We investigate a novel satellite avoidance strategy to mitigate the impact of large commercial satellite constellations in low-Earth orbit on the Vera C. Rubin Observatory Legacy Survey of Space and Time (LSST). To do this, we construct and simulate the motions of planned Starlink and OneWeb satellites, test how effectively the Rubin scheduler algorithm can avoid them, and assess how the overall survey is affected. With both of these satellite constellations fully deployed, and with no satellite avoidance strategy, the LSST would lose ~0.02% of science pixels to satellite streaks, assuming a typical streak width of 50 pixels. Given a reasonably accurate satellite orbit forecast, we find it is possible to adjust the scheduler algorithm to effectively avoid some satellites. Doing so would reduce pixel loss by a factor of two with minimal impact to the survey depth. However, the small fraction of pixels lost to streaks from Starlink and OneWeb renders this mitigation strategy unnecessary. While high-airmass twilight observations are more severely impacted (the majority of these exposures would have a streak), proceeding with no satellite avoidance would only lose ~0.06% of these science pixels. Even if effects such as non-linear crosstalk cascades pixel loss by a factor of five, overall LSST pixel loss from Starlink and OneWeb would still only be at the ~0.1% level. A drastic increase in the number or brightness of satellites during Rubin Operations, or science impacts not well-represented by pixel loss, could conceivably make this satellite avoidance strategy worth implementing in the future.

## Using the Repository: 
The satellite dodging implementation is hosted at the LSST rubin sim repository: https://github.com/lsst/rubin_sim

#### Dependencies: 
A fresh conda environment for installing dependencies is highly recommended: 
  ```
  conda create -n sat-env 
  conda activate sat-env
  ```
* Rubin sims: 
    ```
    conda create -n rubin -c conda-forge rubin_sim # Create a new environment
    conda activate rubin
    rs_download_data  # Downloads ~2Gb of data to $RUBIN_SIM_DATA_DIR (~/rubin_sim_data if unset)
    conda install -c conda-forge jupyter # Optional install of jupyter
    ```
* shapely: `conda install -c conda-forge shapely`
* skyfield:  `pip install skyfield`

#### Generating Figures: 
To create the figures 1,2,3,4,5 in this paper, navigate to the plots folder. 
* Figure 1 is created using constellation_examples.ipynb and satellite_util_examples.ipynb. 
* Figure 2 is created using basis_func_examples.ipynb. 
* Figure 3 and 4 are created in compare_sim_runs.ipynb. 
* Figure 5 is created in twilight_neo.ipynb. 

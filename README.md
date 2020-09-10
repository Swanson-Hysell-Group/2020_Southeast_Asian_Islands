# 2020_Southeast_Asian_Islands

This repository contains data and code associated with the following paper:

Park, Y., Maffre, P., Goddéris, Y., Macdonald, F. A., Anttila, E. S. C., and Swanson-Hysell, N. L., 2020, Emergence of the Southeast Asian islands as a driver for Neogene cooling: Proceedings of the National Academy of Sciences, doi:10.1073/pnas.2011033117

This repository is also archived on Zenodo: *Zenodo link goes here.*

The GEOCLIM model itself is available here: https://github.com/piermafrost/GEOCLIM-dynsoil-steady-state/releases/tag/v1.0

Any questions regarding the code, data, or paper can be directed to yuempark@berkeley.edu.

**Note regarding data availability:**

Some data files required to execute the code (most notably the raw GEOCLIM output files) are too large to be uploaded to GitHub, and therefore are not included within this repository. To access this raw data, please contact yuempark@berkeley.edu. However, critical information has been extracted from the raw GEOCLIM output and saved in .csv's within the `code/output/` folder in this repository.

**Note regarding acronym usage:**

During the development phase of these analyses, the name we were assigning to the Southeast Asian islands changed from 'the Indonesian Archipelago (IA)' to 'the Southeast Asian islands (SEAIs)'. These two names refer to the same set of islands between Australia and mainland Asia, and are used interchangably within this repository.

## Computational Environment

All code contained within this repository is executed within Jupyter notebooks using a Python 3 kernel. The standard [Python 3 Anaconda package distribution](https://www.anaconda.com/products/individual) contains most of the required Python packages by default. However, the following two packages (which deal with GIS data) will need to be installed separately to execute all of the code included within this repository successfully:

* netCDF4
* cartopy

The full computational environment used to execute this code can be found within the `SEAIs_python3.yml` file in this repository.

## Repository Overview

### code

Contains the code and input used to perform the analyses associated with this study.

#### input

This folder contains the data that are used in the Jupyter notebooks in the `notebooks` folder. This includes:

* Geochemical data for various rock types, primarily derived from EarthChem.
* pCO$_{2}$ proxy estimates.
* Shapefiles for the paleoshorelines of the SEAIs.
* Watershed chemical weathering measurements.
* GFDL CM2.0 climatology output.
* Modern temperature and runoff reanalysis data.
* Global lithology data.

Please refer to the documentation within the Jupyter notebooks in the `notebooks` folder for further details.

#### notebooks

This folder contains the Jupyter notebooks that were used to perform the analyses presented in this study.

* `weatherability_curves.ipynb`
    * This notebook generates the weatherability curves associated with our paleo-SEAIs scenarios.
* `climate_masks.ipynb`
    * This notebook converts modern temperature/runoff and GFDL CM2.0 temperature/runoff output into netCDF files of mean temperature/runoff for input into GEOCLIM.
* `figures.ipynb`
    * This notebook does not perform any analyses, but generates some of the figures presented in the manuscript and supporting information.
* `lithology_composition.ipynb`
    * This notebook calculates the Mg and Ca composition of lithological classes in order to develop informed constants for the Ca and Mg values that are used within the GEOCLIM model.
* `lithology_masks_7d.ipynb`
    * This notebook generates the required lithology input files to GEOCLIM from GLiM + LiMW.
* `parameter_exploration.ipynb`
    * This notebook takes the 93,600 chemical weathering maps produced during the calibration stage of GEOCLIM, and removes those parameter combinations that do not match measurements of chemical weathering in watersheds around the world.
* `scenario_analysis.ipynb`
    * This notebook assesses GEOCLIM output for the various scenarios explored in this study.

#### output

This folder contains the output from the Jupyter notebooks in the `notebooks` folder. This includes:

* Critical information extracted from the raw GEOCLIM output.
* The runoff, temperature, lithology, and slope fields that are used as input into the GEOCLIM model.

Please refer to the documentation within the Jupyter notebooks in the `notebooks` folder for further details.

### figures

All figures included in this folder are generated directly by the Jupyter notebooks within the `code/notebooks/` folder, with the exception of `weatherability_curves.pdf`, which has been modified from `weatherability_curves_raw.pdf` using Adobe Illustrator.

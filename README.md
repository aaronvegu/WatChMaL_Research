# WatChMaL_Research
Data analysis notebook on the properties and behavior of gamma, e, pion and muon flavors from the Hyper Kamiokande and WatChMaL neutrino detection project. As part of the doctoral thesis of a researcher within the [Center for Data Analysis and Supercomputing (CADS)](https://cgsait.udg.mx/cads) of the University of Guadalajara.

With emphasis on understanding and analyzing the properties that differentiate the behavior between neutrino gamma and electron flavors, which are usually very similar, in order to more easily discriminate this pair of neutrino flavors.

## Environment
For this notebook Conda is used. To create a new environment from the YAML file, you can use the conda env create command with the --file or -f option followed by the YAML provided on this repo called "environment.yml":

```
conda env create --file environment.yml
```

## Repo Structure

#### data and model_analysis folders
The Data and model_analysis folders contain the H5 and npy data files used for the analysis. For its part, the Data folder contains H5 files with simulation data from the Cherenkov neutrino and radiation detector of the [WatChMaL project](https://github.com/WatChMaL/WatChMaL), while model_analysis contains the output test and verification files of a machine learning model in the process of training to detect and differentiate results between gamma neutrino particles and electron neutrino.

#### utils folder
It contains a python script that is useful for reading H5 files and understanding the structure of the contained data, it does this by reading the H5 file that is passed to it by positional parameter and printing its structure and data count to the console.
To use it, you can execute the script following the next example:

```
python3 ./utils/H5_reader.py <path-to-H5-file>
```

#### environment.yml
The YAML file used to import the conda environment to run this analysis.


## Analysis of partial results
The first of the analyzes carried out on the data of the different flavors of neutrinos was performed in **hits_analysis.ipynb** file.

In this first analysis, an analysis was performed on the hits resulting from each event based on the event charge of the gamma neutrino particle. As a first result of this analysis, we came to the conclusion that there was a positive relationship between the number of hits in the event and its load, where the higher the load = the greater possible number of hits in the event, in this way, it was also observed that there were other factors intervening in the number of hits of the event, since even events with a high load gave a low number of hits.

The next step was to carry out the same analysis of the gamma particle but with all the other particles, which is carried out in the file: **multi_particles_hits_analysis.ipynb**.

##

For the analysis of other possible factors that intervene in the number of hits per event, the position of the collision was selected as a factor to be analyzed, the analysis was carried out in the file **position_analysis.ipynb** using data extracted from the training of a ML model that aims to discriminate between the gamma and electron neutrino flavors. This data is located in the data_analysis folder.

As a partial result of this analysis, we can conclude that the model, although it knows how to differentiate between gamma and electron, shows a mirror or opposite behavior between the results of the particles, since where it is correct when predicting the gamma particle is where it is wrong with the electron particle and vice versa.

## Disclaimer
The analyzes presented in this repository are partial, they are still in the development process and only show a part of the research that is being carried out, therefore it is not claimed that these results are conclusive or final.

mosquito_movement_spatial_repellent

# Method for secondary analysis of trial data

Contains code from the paper <br>
<i>Can trials of spatial repellents be used to estimate mosquito movement?</i> Malinga J, Maia M, Moore S & Ross A. <br>
<i>Parasites & Vectors</i> 2019, 12: 421

This is a copy of the repository in the Swiss TPH github

There is a small error throughout the publication. We erroneously stated that the mean of the distances was lambda. Because the distribution assumed is a half-normal, the mean is lambda*sqrt(2/pi). This error appears in the methods and results of the manuscript. All means should be multiplied by sqrt(2/pi) or 0.798. The conclusions of the paper remain unchanged. The code was correct, but the description of lambda has now been updated. We apologise for this error. 

# cpp codes _analysis

Contains the C++ code to perform the analysis on the trial data (which can be real or simulated).
There are separate files for the trials with/out additional seasonality data. 

Each input dataset has to be renamed to "aggTrapSimul.txt" for the code to run (aggTrapSimul.txt contains an example simulated dataset, which can be made using the R scripts in /r codes simulation). <br>

The output file results.txt (the example is for the version without additional data on seasonality) gives the estimated baseline distribution of mosquitoes in the village (in the case of zero coverage of spatial repellents) as a proportion for each house in the village. The parameter values of interest and the log likelihood are given underneath.  

The fitting method uses the Nelder-Mead algorithm from the AS047 library by John Burkhardt. This came from:<br>
https://people.sc.fsu.edu/~jburkardt/f77_src/asa047/asa047.html


# r codes _ simulation

Contains the R scripts for simulating the trial scenarios (with/out additional seasonality data). The simulated datasets are used to test how well the analysis method would work for a trial with specific parameter values.

The parameter values and file names for the simulations can be edited at the end of each R script.
These R scripts can simulate datasets with different parameter combinations.

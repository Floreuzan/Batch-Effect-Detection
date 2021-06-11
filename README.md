# Revisited kBET method



Various methods have been proposed in
literature to remove or reduce the cell- bias and
batch-effects in single-cell data while preserving
biological variability: linear regression such as
Combat, Seurat’s canonical correlation analysis
and projection of mutual nearest neighbors.

One of the most renowned methods that quantifies the batch effect in scRNA-seq data is kBET
method. It measures if a replicated experiment is well-mixed, i.e., it ensure that any
subset of neighboring samples has the same distribution of batch labels as the full dataset. 

<img src=Batch-effect.PNG width="500">

# Alternative test metrics

kBET uses a &chi;2-based test for random neighborhoods of fixed size to determine whether they
are well mixed, followed by the averaging of the binary test results to return an overall rejection rate.

Here we discuss some alternative nonparametric test metrics specifically to evaluate their
performance in situations where we do not have access to a massive sized dataset: Mann Whitney U-Test, Wilcoxon T-Test, Kolmogorov–Smirnov Test.

# Data simulation

We stimulate data using the Splat package in R using a Gamma-Poisson distribution. We control for the batch-effect (weak, mild, strong) and for the size ratio between the two batches (1/1, 1/3, 1/4, 1/9, 1/19).

#### Notes:

Files named as "result_sim2_ratio_1_*_rjc.ipynb" are the raw code to run the test results for different size ratios.
File "Simulations.ipynb" is a tidy and combined version of the final code.
Folder "weak", "mild", "strong" are the simulated data with different batch effects.
Folder "result_dataframe" is the data of the result generated for each size ratio.
Folder "result_plot" contains the code for the visualization with the plots.
File "data_sim2_generation.Rmd" is the code for data simulation.



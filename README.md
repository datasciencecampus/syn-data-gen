# syn_data_gen
Synthetic data generation pipeline with differential privacy 



We receive lots of requests to generate synthetic data of private/confidential datasets.
The notebook in this directory offers to produce synthetic version of private datasets with
minimal inputs and parameter tweaking from the user.

The purpose of this notebook is to:

Produce Synthetic data  with differential privacy

Ensuring method can synthesise categorical variables (which was a bottleneck for GAN)

One of the method (correlated attributed mode) is based on Bayesian Analysis

Currently being developed for use by GAD/DfE

Initial run performed on dummy dataset provided by GAD was deemed fit for purpose by GAD

They will use the code and feed in with their findings

The code will also be used for generating synthetic data for research and analysis for PhD students

This notebook is based on the work DataSynthesizer: Privacy-Preserving Synthetic Datasets
https://faculty.washington.edu/billhowe/publications/pdfs/ping17datasynthesizer.pdf

The numerical code presented in this notebook is heavily based on open source code available here 
https://github.com/DataResponsibly/DataSynthesizer

DataSynthesizer is the directory where the following parent modules exist:
DataSynthesizer consists of three high-level modules — DataDescriber, 
DataGenerator and ModelInspector. The first, DataDescriber, investigates
the data types, correlations and distributions of the attributes in the 
private dataset, and produces a data summary, adding noise to the distributions
to preserve privacy. DataGenerator samples from the summary computed by 
DataDescriber and outputs synthetic data. ModelInspector shows an intuitive 
description of the data summary that was computed by DataDescriber, 
allowing the data owner to evaluate the accuracy of the summarization
process and adjust any parameters, if desired.

DataSynthesizer can operate in one of three modes:
In correlated attribute mode, we learn a differentially
private Bayesian network capturing the correlation structure
between attributes, then draw samples from this model to
construct the result dataset. In cases where the correlated 
attribute mode is too computationally expensive or when there
is insufficient data to derive a reasonable model, one can use
independent attribute mode. In this mode, a histogram is derived
for each attribute, noise is added to the histogram to achieve
differential privacy, and then samples are drawn for each attribute.
Finally, for cases of extremely sensitive data, one can use random 
mode that simply generates type-consistent random values for each attribute.

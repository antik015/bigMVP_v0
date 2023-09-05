bigMVP
================

This github repository contains code and data to reproduce (upto Monte Carlo variations) results from the paper "Bayesian inference on high-dimensional binary responses" by Chakraborty, Ou and Dunson (2023). The paper can be found [here](https://arxiv.org/abs/2106.02127). 

## Abstract

It has become increasingly common to collect high-dimensional binary response data; for example, with the emergence of new sampling techniques in ecology. In smaller dimensions, multivariate probit (MVP) models are routinely used for inferences. However, algorithms for fitting such models face issues in scaling up to high dimensions due to the intractability of the likelihood, involving an integral over a multivariate normal distribution having no analytic form. Although a variety of algorithms have been proposed to approximate this intractable integral, these approaches are difficult to implement and/or inaccurate in high dimensions. Our main focus is in accommodating high-dimensional binary response data with a small to moderate number of covariates. We propose a two-stage approach for inference on model parameters while taking care of uncertainty propagation between the stages. We use the special structure of latent Gaussian models to reduce the highly expensive computation involved in joint parameter estimation to focus inference on marginal distributions of model parameters. This essentially makes the method embarrassingly parallel for both stages. We illustrate performance in simulations and applications to joint species distribution modeling in ecology.

## bigMVP R package

To isntall the R package bigMVP, first install the package "devtools" in R. Then in the R console enter "install_github("antik015/bigMVP")". 

## Contents

A brief overview of the materials of this repository with directions to use is provided below.

### manuscript
The manuscript folder contains the zip files "Main draft source.zip" and "Online supplement.zip". These zip files contain all the latex source files, figures and bib files to reproduce the the main draft and the online supplement, respectively.

### code

The folder code contains two .Rmd files - bigMVP.Rmd and real_data. Rmd. The bigMvp.Rmd file contains code to reproduce Figure 1 in the manuscript upto Monte Carlo variations. The file also makes use of the four key functions in the bigMVP R package - bigMVP(), bigMVPh(), mvp_mcmc_ni() and mvp_mvmv_lkj(). Further details on the specific usage of these functions canm be found in the help files of the package. The file real_data.Rmd file contains code to analyze the two species prevalence datasets used in the manuscript. To run this file one must first install the package "sjSDM" from CRAN which can be done by enetring "install.packages("sjSDM")". The datasets analyzed in this file are uploaded in the folder "data".

### data

This folder contains the bird and vegetation data that were analyzed in the manuscript. For the bird data the relevant files are "Xt_1_bird.csv" and "Yt_1_bird.csv" and similar names are used for the vegetation. The subscriot "t" stands for training in the filesnames. Two separate validation files are also provided. Please download these files on your computer and set the R path to the correct folder to run the real_data.Rmd file.

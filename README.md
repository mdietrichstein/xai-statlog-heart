[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3262272.svg)](https://doi.org/10.5281/zenodo.3262272)

# Exploration of ML Explainability Methods on the Statlog (Heart) Data Set

The goal of this repository is to explore various Explainable AI (XAI) methods on models trained on an classification task on the [UCI ML - Statlog
(Heart) Data Set](http://archive.ics.uci.edu/ml/datasets/statlog+(heart)).

## Running the code on your system

1. Make sure that Python 3.6 and pip are installed in your system
2. Install the required dependencies: `pip install -r requirements.txt`
3. Start jupyter: `jupyter notebook notebooks`
4. Open the url shown in the output of the previous command in your webbrowser


## Running the code via Docker

1. Build the docker image: `docker build -t xai-statlog-heart .`
2. Run the image: `docker run -p 8888:8888 xai-statlog-heart`
4. Open the url shown in the output of the previous command in your webbrowser

## Notebooks

In the `notebooks` folder you'll find the following notebooks:

**01-data_exploration.ipynb**

This notebook contains a short exploratory analysis of the UCI ML - Statlog (Heart) Data Set.

**02-data_preprocessing.ipynb**

Running this notebook transforms the original dataset (`data/raw/heart.dat`) into a collection of transformed datasets which are used in the subsequent notebooks (`data/processsed`).

**03-classifier_evaluation.ipynb**

Here we evaluate different classification algirithms on the dataset and chose the three best performing to create an ensemble classifier which is used in the remaining two notebooks.

**04-fold_interpretation.ipynb**

Uses 3-Fold cross validation to train three different classifiers and compares the explanations retrieved for each using the following methods:
* [PDP - Partial Dependence Plots](https://christophm.github.io/interpretable-ml-book/pdp.html)
* [ICE - Individual Conditional Expectation Plot](https://christophm.github.io/interpretable-ml-book/ice.html)
* [ALE - Accumulated Local Effects Plot](https://christophm.github.io/interpretable-ml-book/ale.html)
* [Global Surrogate Model](https://christophm.github.io/interpretable-ml-book/global.html)
* [Example-Based Model](https://christophm.github.io/interpretable-ml-book/example-based.html)

**05-good_versus_bad_model.ipynb**

Compares the explanations listed above between the original classifier and one that has been adapted to perform worse.

## Credits
This repository contains a modified version of [ALEPython](https://github.com/blent-ai/ALEPython).



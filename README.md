# Raman_spectra_data

In this repository, we publish the data used in the Master Thesis *Data-driven classification of minerals from their Raman spectroscopy scans for autonomous science on Mars (collaboration with NASA project InVADER)*. 
The initial dataset is from [the RRUFF database](https://rruff.info/). From this database, we consider the [LR-Raman](https://rruff.info/zipped_data_files/raman/LR-Raman.zip) subset frow which we keep only **raw** and the [excellent_oriented](https://rruff.info/zipped_data_files/raman/excellent_oriented.zip) subset from which we keep only **processed** samples. For both subsets, we prune classes with less than 8 samples. We only considers shifts from 200 to 1600 cm-1. We perform upsampling and interpolation to have a constant number of features among samples. Finally, the intensities are normalized. The different sets that we obtain are the following:

## Fully supervised set

In the **`data_fully_supervised/`** directory, we provide the fully supervised data, that is data with labels. The directory is organized into 2 subdirectories:

* `raw/` : 
  - *fullsup.pkl* correspond to the raw training set
  - *holdouttest.pkl* correspond to the raw test set
* `processed/` : 
  - *fullsup_processed.pkl* correspond to the processed training set
  - *holdouttest_processed.pkl* correspond to the processed test set

## Semi-supervised set

In the **`data_semi_supervised/`** directory, we provide the data for the semi-supervised experiments. What is done here is diving the supervised raw dataset (*fullsup.pkl*) into two subdataset, one with the labels (called *supervised_train*) and one without the labels (called *unsupervised_train)*. This division is done for several proportion : 10%, 20%, 30%, 40% and 50% of supervised samples.

* `10_per_cent_of_supervised/` : correspond to subset with 10% of supervised samples and 90% of unsupervised samples
  - *supervised_train0.1.pkl* correspond to the supervised samples
  - *unsupervised_train0.9.pkl* correspond to the unsupervised samples
* `20_per_cent_of_supervised/` : correspond to subset with 20% of supervised samples and 80% of unsupervised samples
  - *supervised_train0.2.pkl* correspond to the supervised samples
  - *unsupervised_train0.8.pkl* correspond to the unsupervised samples
* `30_per_cent_of_supervised/` : correspond to subset with 30% of supervised samples and 70% of unsupervised samples
  - *supervised_train0.3.pkl* correspond to the supervised samples
  - *unsupervised_train0.7.pkl* correspond to the unsupervised samples
* `40_per_cent_of_supervised/` : correspond to subset with 40% of supervised samples and 60% of unsupervised samples
  - *supervised_train0.4.pkl* correspond to the supervised samples
  - *unsupervised_train0.6.pkl* correspond to the unsupervised samples
* `50_per_cent_of_supervised/` : correspond to subset with 50% of supervised samples and 50% of unsupervised samples
  - *supervised_train0.5.pkl* correspond to the supervised samples
  - *unsupervised_train0.5.pkl* correspond to the unsupervised samples


## Shifted test set

In the **`data_shift_experiment/`** directory, we provide the data that we used for investigating the inductive bias of Convolutional Neural Network. The data in this directory is constructed from the raw test set *holdouttest.pkl*. We shift the intensities by 15 and 30 cm-1 to the right. 

* `holdouttest_shifted_15.pkl` : correspond to test set with intensities shifted by 15cm-1
* `holdouttest_shifted_30.pkl` : correspond to test set with intensities shifted by 30cm-1




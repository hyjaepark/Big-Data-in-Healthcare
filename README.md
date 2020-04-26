# CSE6250 - Big Data in Healthcare
This project is for GT CSE6250 Big Data in Healthcare class. The foundation of this project in based on one of the top solutions of CheXpert by jfhealthcare and their ML team members. We want to give credit to their team for developing the foundation of this project. The goal for the first part of the project is to replicate their models and results with the code provided. The second part of the project focuses on optimization of the replicated models in order to improve specificity, therefore, improving the classification of true positives on chest x-ray diagnostics.

## What is Chexpert?
CheXpert is a large dataset of chest X-rays and competition for automated chest x-ray interpretation, which features uncertainty labels and radiologist-labeled reference standard evaluation sets.
## Why Chexpert?
Chest radiography is the most common imaging examination globally, critical for screening, diagnosis, and management of many life threatening diseases. Automated chest radiograph interpretation at the level of practicing radiologists could provide substantial benefit in many medical settings, from improved workflow prioritization and clinical decision support to large-scale screening and global population health initiatives. For progress in both development and validation of automated algorithms, we realized there was a need for a labeled dataset that (1) was large, (2) had strong reference standards, and (3) provided expert human performance metrics for comparison.
## How to take part?
CheXpert uses a hidden test set for official evaluation of models. Teams submit their executable code on Codalab, which is then run on a test set that is not publicly readable. Such a setup preserves the integrity of the test results.

## How to setup
> `pip install -r requirements.txt`
> Designate train.csv and valid.csv in parameter.json. 
> Sample csv files have been included in the data folder
> If you want to train on bigger data visit chexpert homepage and download images
> Designate cnn algorithm in the backbone in parameter.json
> change hyperparameters as you want

## How to train model
> Open cmd and change directory to Team34_code
> python Chexpert/bin/train.py /cfg.json logdir --num_workers 4 --device_ids "0"

*depending on your machine increase the device_ids for faster training
*If you run out of memory change the batch size in paramters.json


## How to test
Save best1.ckpt file in your logdir as best_result.ckpt.

> Open cmd and change directory to Team34_code
> Save your ground truth test data as test_ground_truth.csv in main folder
> python Chexpert/bin/test.py

* if you want to plot the roc figure and get the AUC, run the command
> python Chexpert/bin/roc.py plotname







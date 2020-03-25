# 
The code for Paper 7636 in IJCAI2020
This is the code repository for paper: A new attention mechanism to classify multivariate time series

Data link: https://drive.google.com/open?id=1eMLQIjDCvMIBs_BHDZAmb37MnlywxgyT

Due to the limited data for preparing this GitHub repository, some datasets are uploading.

Running Example using the toy dataset:
For example, the dataset name is "toy" and there are two data files under data/toy folder: train_0.txt and test_0.txt
1. Run Stablized Fully-Convolutional Network with Cross Attention (SFCN-CA)
    1.1 Script:
    # python fcn_ca_main.py 0

    1.2 Outputs:
    The training log file locates at log/<DATASET_NAME>/fcn_classification/
    The trained model locates on object/<DATASET_NAME>/fcn_classification/


2. Run Stablized Fully-Convolutional Network without any attention (SFCN)
    2.1 Script:
    # python fcn_ca_main.py -1

    2.2 Outputs:
    The training log file locates at log/<DATASET_NAME>/fcn_classification/
    The trained model locates on object/<DATASET_NAME>/fcn_classification/


3. Run Stablized Fully-Convolutional Network with Global Attention (SFCN-GA)
    3.1 Script:
    # python fcn_ca_main.py 1

    3.2 Outputs:
    The training log file locates at log/<DATASET_NAME>/fcn_classification/
    The trained model locates on object/<DATASET_NAME>/fcn_classification/


4. Run Stablized Fully-Convolutional Network with Recurrent Attention (SFCN-RA)
    4.1 Script:
    # python fcn_ca_main.py 2

    4.2 Outputs:
    The training log file locates at log/<DATASET_NAME>/fcn_classification/
    The trained model locates on object/<DATASET_NAME>/fcn_classification/


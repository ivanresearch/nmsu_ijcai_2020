#
This is the code repository for paper 7636 that we submitted to IJCAI 2020. The paper title is "A new attention mechanism to classify multivariate time series"

Due to the limited space of the GitHub repository, we only put the processed data of two datasets here. The processed data of the other datasets can be downloaded from google drive link: https://drive.google.com/open?id=1eMLQIjDCvMIBs_BHDZAmb37MnlywxgyT

There are 14 datasets.
Each dataset contains two files: train.txt and test.txt.


Example of running the code using the Ges dataset:
1. Generate the results in Table 2 and Figure 3
    1.1 Script:
    # python fcn_ca_main.py <DATA_NAME> <ATTENTION_TYPE>

    1.2 Parameters:
    <DATA_NAME>: "Ges" is the name of Ges dataset. It means CA-SFCN runs on Ges datasets. The program identifies the parameter file: parameters/all_feature_classification_ges.txt
    <ATTENTION_TYPE>: 0 means run the Cross-Attention Stabilized Fully-Convolutional Network (CA-SFCN)


    1.3 List of all parameter values
    <DATA_NAME>: "Ges" for Ges Dataset
    <DATA_NAME>: "eeg" for Eeg Dataset
    <DATA_NAME>: "eegs" for Eegs Dataset
    <ATTENTION_TYPE>: 0 means run the Cross-Attention Stablized Fully-Convolutional Network (CA-SFCN)
    <ATTENTION_TYPE>: -1 means run the stablized Fully-Convolutional Network (CA-SFCN) without any attention mechanism
    <ATTENTION_TYPE>: 1 means run the Global-Attention Stablized Fully-Convolutional Network (GA-SFCN)
    <ATTENTION_TYPE>: 2 means run the Recurrent-Attention Stablized Fully-Convolutional Network (RA-SFCN)

    1.4 Outputs:
    The training log file locates at log/<DATASET_NAME>/fcn_classification/
    In this example: 
    # python fcn_ca_main.py Ges 0
    The output log file is
    log/ges/fcn_classification/eeg_train_0_fcn_classification_act3_acc_attention0_conv3.log_<TIME_STAMP>.log

    The testing accuracy, training time and testing time can be found at the last three rows of the output log file.
    The testing accuracies are used for the last four columns of Table 2 in the paper. The other columns in Table 2 are directly copied from [Karim et al., 2019].
    The running time information is used for the results in Figure 3.


2. Generate the results in Table 3
    2.1 Rename the parameter cnn_model_parameter_conv1.txt to be cnn_model_parameter.txt.
    cnn_model_parameter_conv1.txt is the cnn setting parameter file with only one convolutional layer
    2.2 Re-run the script in 1.1
    2.3 The accuracy, running time results can be found in the log file: 
    In this example: 
    # python fcn_ca_main.py Ges 0
    The output log file is
    log/ges/fcn_classification/eeg_train_0_fcn_classification_act3_acc_attention0_conv1.log_<TIME_STAMP>.log
    2.4 Similar setting for the cnn with 5 convolutional layers using cnn_model_parameter_conv5.txt
    
#
This is the code repository for paper 7636 that we submitted to IJCAI 2020. The paper title is "A new attention mechanism to classify multivariate time series".

Due to the limited space of the GitHub repository, we only put the processed data of two datasets here. The processed data of the other datasets can be downloaded from google drive link: https://drive.google.com/open?id=1eMLQIjDCvMIBs_BHDZAmb37MnlywxgyT

There are 14 datasets. Each dataset contains two files: train.txt and test.txt.

1. Prerequirments:
    The project is writen by Python 2.7. Following packages are needed to run this project
    1.1. tensorflow-gpu-1.15.0
    1.2 scikit-learn 0.22.0
    1.3 numpy 1.17.3

2. Generate the results in Table 2 and Figure 3
    2.1 Script:
        # python fcn_ca_main.py <DATA_NAME> <ATTENTION_TYPE>

    2.2 Parameters:
        <DATA_NAME>: dataset name. Not case sensitive. 
        14 possible values: act, atn, ara, aus, dsp, eeg, eeg2, ges, har, hts, jvo, net, ohc, ozo.
        This parameter is also used to identify the parameter file. For example, for "ges" dataset, the parameter file is parameters/all_feature_classification_ges.txt. 

        <ATTENTION_TYPE>: the method we can test. 
        4 possible values: -1, 0, 1, 2.
        -1 means SFCN (Stablized Fully-Convolutional Network without any attention)
        0 means CA-SFCN (Cross-Attention Stablized Fully-Convolutional Network)
        1 means GA-SFCN (Global-Attention Stablized Fully-Convolutional Network)
        2 means RA-SFCN (Recurrent-Attention Stablized Fully-Convolutional Network)

        For example, the command python fcn_ca_main.py ges 0
        Runs CA-SFCN method on ges Dataset.

    2.3 Outputs:
        The log file of the training stage file locates at log/<DATASET_NAME>/fcn_classification/
        For example, 
        # python fcn_ca_main.py ges 0
        The output log file is
            log/ges/fcn_classification/ges_train_fcn_classification_act3_acc_attention0_conv3.log_<TIME_STAMP>.log

        The testing accuracy, training time, and testing time can be found at the last three rows of the output log file.

        The testing accuracies are reported in the last four columns of Table 2 in the paper. The other columns in Table 2 are directly copied from [Karim et al., 2019].
        The running time information is reported in Figure 3. 


3. Generate the results in Table 3
    3.1 Rename the parameter cnn_model_parameter_conv1.txt to be cnn_model_parameter.txt.
        cnn_model_parameter_conv1.txt is the cnn setting parameter file with only one convolutional layer
    3.2 Re-run the script in 1.1
    3.3 The accuracy, running time results can be found in the log file: 
        For example: 
        # python fcn_ca_main.py ges 0
        The output log file is
        log/ges/fcn_classification/eeg_train_0_fcn_classification_act3_acc_attention0_conv1.log_<TIME_STAMP>.log
    3.4 Similar setting for the cnn with 5 convolutional layers using cnn_model_parameter_conv5.txt

    The testing accuracies in this section are reported in the Table 3.
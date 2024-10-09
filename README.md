# SMART4EEG
A time-frequency weighted model to classify EEG patterns

Hardware/Software:
1. System：Windows/Linux
2. GPU：Nvidia RTX3090-24Gb * 1

Data Preparation：
1. Data avaiable: https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/data
2. Create a validation_stpectrograms and train_stpec_for_maper folder, and then create a code/model1 folder to store all code files
3. Copy no less than 8000 files from train_stpectPrograms to the train_stpec_for_maper folder, and copy all remaining files to validation_stpectPrograms
4. All code files should be placed in the code/model1 directory
5. Running divide_falid.ipynb will generate two files, updated_train.csv and validation.csv, in the current directory
6. Running the findnvalidation-eegags.ipynb file will generate the validation-eegags folder in the current directory, which contains several validation set .paquet files
7. Run eeg2mel.ipynb to generate the eeg2specs.npy file in the current directory
8. Running spec2pkl.ipynb will generate the EEG_Spectrograms folder in the current directory

Training：
1. Running M1_1.ipynb. It may take approximately 7 hours/Nvidia3090*1 and generates several **.pt files.
2. Running M1_2.ipynb. It may take approximately 5 hours/Nvidia3090*1 and generates several **_v2.pt files.
3. Running M2_1_2.ipynb. It may take approximately 6 hours/Nvidia3090*1 and generates several pop_(training stage)_weight_oof_n(N value)/**.pth files. Setting N value in class CFG.
5. Running M3_1.ipynb. It may take approximately 7 hours/Nvidia3090*1 and generates several **.pt files.
6. Running M3_2.ipynb. It may take approximately 5 hours/Nvidia3090*1 and generates several **_v2.pt files.

Infering:
Running infer.ipynb

Notes:
·All paths are written in the code Config class, and the Config parameters can be modified according to the actual data storage and weight file storage paths. The code training environment is selected as Windows, and if training in a Linux environment, attention should be paid to the path "/" "\" symbol switching
·Please reserve sufficient hard drive capacity in advance for data and intermediate data storage. Suggested capacity: not less than 200Gb.

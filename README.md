# Applying-Deep-Reinforcement-and-Positive-Unlabeled-Learning-to-ADR-Signal-Detection
Applying Deep Reinforcement and Positive-Unlabeled Learning to ADR Signal Detection
AddToAllData Import all data extracted from the ADRs Database into a single file.

PTNAMEtoCID Modify all PT Names (Adverse Reaction Names) in the file to the corresponding CUI from the MedDRA website.

CIDtoLabeled Compare the ATC Code and CID with the trusted dataset. Mark the data that appears in the trusted dataset as 1, and those that do not appear as 0.

StringSplitATC Split the ATC Code in the labeled data.

LabelEncoder_ATC Convert the English letters in the ATC Code into numerical values.

OneHotEncoder_ATC Perform one-hot encoding on the ATC Code.

Change_The_Position_of_Sex Rebuild the data after one-hot encoding, as the ATC Code was moved to the front during the process. This step restores it to the original position.

BalanceTrainData__PUTestData_Generator Downsample the data to create balanced training data and generate imbalanced test data based on the original proportion.
The test data will not be used for the final evaluation. Please use the method in the test_creater folder to generate the final realistic test data.
This test data is only for use during model training.

Main:
_DQN: A DQN model built using the Keras RL2 package, available for training and testing.
_TestFullDataOnDQN: A DQN model built using the Keras RL2 package, available for complete testing of the data from the first to the last record (used for _DQN).
_CEM: A CEM model built using the Keras RL2 package, available for training and testing.
_DQN_new: A complete DQN workflow rebuilt using TensorFlow, available for training and testing.
Other.ADR_signal_detection_methods_X6 Perform comprehensive detection of test data using six drug adverse reaction signal detection methods and output evaluation indicators.
(If other forms of test data are needed, please modify the data source and map the abcd contingency table columns as needed.)

Other.DataLabelCount Used to calculate the total number of each label.

Other.Eps Used to calculate decay values from 1 to 0.01.

Other.PNV Used for PNV processing of data (please refer to Senior Ziyu’s literature).

Other.TestData_Clean Used to denoise the test data.

Other.TrainData_shuffled Used to shuffle the training data.

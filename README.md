# Human Protein Classification with PyTorch

An approach to classify mixed patterns of proteins in microscope images using transfer learning.  
Data Source: Kaggle  
Link: 

##Python Libraries/Frameworks Used
Pytorch
Pandas
Numpy
Matplotlib, seaborn (for ploting images and visualisation)

##Notes
1. The Dataset is found to have class imbalances through visualisation. To handle this, F1 score is used as an evaluation metric, instead of normal accuracy.
3. Two different approaches to split into train and vaidation sets were made, one using masking and other using conventional train_test_split, and scores were recorded. It was observed that f1 score for masking was better due to slightly more amount of data to train. 

##Features
1. Channel-wise Data Augmentation : Each of the channels is normalised by subtracting from mean and dividing by standard deviation across each channel. This is helpful to prevent any one channel from disproportionately affecting gradients.  
For this purpose the values of mean and standard deviation are taken from ImageNet Dataset, which is suggested for pre-trained models on ImageNet.  
Reference: [Pre-Trained models_Pytorch](https://pytorch.org/vision/stable/models.html) 











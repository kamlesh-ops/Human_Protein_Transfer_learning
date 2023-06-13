# Human Protein Classification with PyTorch


An approach to classify mixed patterns of proteins in microscope images using transfer learning.  
Data Source: Kaggle  
Link: 

## Python Libraries/Frameworks Used
Pytorch
Pandas
Numpy
Matplotlib, seaborn (for ploting images and visualisation)

## Notes
1. The Dataset is found to have class imbalances through visualisation. To handle this, F1 score is used as an evaluation metric, instead of normal accuracy.
3. Two different approaches to split into train and vaidation sets were made, one using masking and other using conventional train_test_split, and scores were recorded. It was observed that f1 score for masking was better due to slightly more amount of data to train. 

## Features
1. Channel-wise Data Augmentation : Each of the channels is normalised by subtracting from mean and dividing by standard deviation across each channel. This is helpful to prevent any one channel from disproportionately affecting gradients.  
For this purpose the values of mean and standard deviation are taken from ImageNet Dataset, which is suggested for pre-trained models on ImageNet.  
Reference: [Pre-Trained models_Pytorch](https://pytorch.org/vision/stable/models.html) 

2.Different transformations applied to the image:
  1. Random Cropping
  2. Random Resized Cropping
  3. Normalize
  4. ToTensor(mandatory to convert into pyTorch Tensor)
  5. RandomHorizontalFlip
  6. RandomRotation

## Training
1. To increase the speed of training, available GPU used.
2. Learning Rate Scheduling - To change learning rates after each batch of training.
3. Weight Decay - Regularization technique, prevent weights from becoming too large.
4. Gradient Clipping - To clip gradient to smaller values while training.

# Loss:
Binary-Cross Entropy Loss which are suitable and align for F1 metric(when binary loss decrease, f1 metric do not change much)












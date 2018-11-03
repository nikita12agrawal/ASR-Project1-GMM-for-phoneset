# ASR-Project1-GMM-for-phoneset

Project 1 Objectives:

A. To train GMM for a given phoneset (40 classes) in the database provided
    1. Understand database handling - # speakers, DR1-DR8, per speaker data, play/use PRAAT to browse sentences, identify 2 different cross-sections of train/test splits, understand annotation files - .phn, .wrd etc., how to read the wavefile, plot, see the waveform for your self, understand sampling rate etc.
    2. How to read phonetic segments using .phn files (phone-level segmentation, at sample level)
    3. Use MFCC generating code to dump features of each read phone waveform as in Item 2 above. Each phone-segment will give a sequence of feature vectors @ frame-rate i.e., for a frame-size of 10ms. Dump sequence of vectors in a phone-wise file: columns: dimension of feature vector (inclding 13 + 13 Delta + 13 Delta-Delta).
    4. Reading features from the phone-wise feature dump - to create a bag-of-vectors (an array of vectors) inside the code.
    5. Building phone-wise GMM from phone-wise feature bag-of-vectors. (USE DIAGONAL COVARIANCE always).
    6. Train the GMM a) for MFCC (13), b) MFCC + Delta MFCC (26), c) MFCC + Delta + Delta-Delta and all the (a), (b), (c) i) with and ii) without energy coefficient (zeroeth coefficient and corresponding 14th coeff, and 27th coeff) - all for one size of GMM (e.g. 64)
    7. Train the GMM with different number of mixtures only for Case (a)(ii) - (2, 4, 8, 16, 32, 64,128,256) 
    8. Understand the generated model parameter format for a given GMM
The scikit toolbox with inbuilt features to train GMM maybe used or write your own EM training algorithm

B. Testing
    1. Read the test file provided and read the features
    2. Employ MAP rule to classify a each  feature vector in the sequence for a given test file (40-way classification problem)
    3. Find the frame-level accuracy for a given test feature set (understand how to use Ground Truth from .phn file - need to prepare the 'frame-level' ground truth for feature vectors
    4. Find the phoneme error rate (PER) for a given utterance
    5. Repeat 3 and 4 for differrent number of mixtures in the model
    5. Arrive at the optimal number of Mixture components for maximum accuracy - smaller # mixtures (e.g. 2 or 4) --> poor modeling, very high # mixtures (e.g. 256) inadequate training data for estimating large no. of mixture parameters



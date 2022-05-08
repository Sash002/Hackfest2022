# Hackfest2022

**Goal of our project**

The primary goal of the project is to leverage recent  developments  in  smart  water  technologies  to  detectand  reduce  water  leakages  in  large  water  distribution  networks  with  the  aid  of  neural  networks. We  have  developed two different models, the first model is based on Artificial NeuralNetworks (ANNs) which not give the desired accurecy. The second  model  is  based  on convolutional NeuralNetworks (CNNs) .  CNNS model able  to  correctly  classify  the  leak nodes with good accuracy,

**DATA COLLECTION**

**Included Files with the repository -**

Data : A portion of used Data to observe the nature

Analysis_and_Model.ipynb : Analysis of Data, Training the model, Testing the model


**DATA PREPROCESSING**

We have used LIBROSA python package for audio analysis purpose

Used matplotlib for data visualisation

WE have then normalises the AUDIO DATAS

Used Numpy library for high performance multidimensional array calculations.

Here we have use MFCC(Mel-Frequency Cepstral Coefficients)featrure extraction to extract features from audio files 
which will convert it into an one dimensional array .


**MODEL**

With the help of tensorflow,Keras python library we have successfully created
a CNN(convolution Neural Network model)

Earlier we have use ANN(artificial Neural Network)with 3 DEnse layer with RELU activation function and
with an output layer with SOFTMAX function,which doesnt give a required /optimum score to the model 
so we rejected it and carry forward our training with CNN

In CNN moderl we have used 9 layers(total)with 7 hidden layers of conv 1-D with diffrent kernel size ,keeping the PADDING same and 
applying Batchnormalization in the middle layers 
and one GLOBALMAXPOOLING1-D to the last hidden layer .

We compiled our model using BINARY_CROSSENTROPY LOSS,and optimizer used : ADAM,with ACCURACY metric

**FITTING THE MODEL**

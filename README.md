# Hackfest2022

**Goal of our project**

The primary goal of the project is to leverage recent  developments  in  smart  water  technologies  to  detectand  reduce  water  leakages  in  large  water  distribution  networks  with  the  aid  of  neural  networks. We  have  developed two different models, the first model is based on Artificial NeuralNetworks (ANNs) which not give the desired accurecy. The second  model  is  based  on convolutional NeuralNetworks (CNNs) .  CNNS model able  to  correctly  classify  the  leak nodes with good accuracy,

Team Members
1. Vikky Anand
2. Anubhav Rajak
3. Arunim Basak
4. Saswati Subhalaxmi
5. Aneesha Das

# DATA COLLECTION

**Included Files with the repository -**

Data : A portion of used Data to observe the nature

Analysis_and_Model.ipynb : Analysis of Data, Training the model, Testing the model

This data acoustic signals recorded from real and buried water distribution networks (WDNs) in Hong Kong. The signals were collected from about ninety leak sites throughout a period of a year using three different non-destructive technologies, namely noise loggers, hydrophones, and micro-electro-mechanical-system (MEMS) accelerometers. The leak signals were collected when leakage is reported, while the no-leak signals were recorded when a previously visited leak site is repaired. Both leak and no-leak signals were recorded from metal and non-metal pipes. 
In PipeNet, a system based on wireless sensor networks, was proposed. It aims to monitor water flow and detect leaks by attaching acoustic and vibration sensors to large bulk-water pipelines and pressure sensors to normal pipelines. This theory is the major basis for origin of the dataset that we are using from Google dataset.

After downloading the dataset , it was organised such that all the leak and no-leak audio files are separated in two folders. This dataset is then uploaded in the google drive and merged with google colab. A water_leakage.txt file is created and then using os package ,the paths of all the audio files are added in the first column of that text file and then in the 2nd column , those audio files are labeled  as 0 and 1 representing non_leak and leak respectively. Then using pandas , the txt file is converted into csv using the dataframe.to_csv() function. 

Link for Dataset : https://data.mendeley.com/datasets/hkn8mxcjyz/1

CSV file we created : [water_shufflefinal.csv](https://github.com/Anubhavrajak/Hackfest2022/files/8646387/water_shufflefinal.csv)


# DATA PREPROCESSING

We have used LIBROSA python package for audio analysis purpose

Used matplotlib for data visualisation

WE have then normalises the AUDIO DATAS

Used Numpy library for high performance multidimensional array calculations.

Here we have use MFCC(Mel-Frequency Cepstral Coefficients)featrure extraction to extract features from audio files 
which will convert it into an one dimensional array .


# MODEL

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

We have taken BATCH_SIZE of 16 and condired 15 EPOCHS with validation data as our X_TEST,Y_TEST and fit our model with 
X_TRAIN,Y_TRAIN.

Consequently we got our final epoch training accuracy of 92.86% with a train_loss of 0.224
and test accuracy of 89.29% with val_loss of 0.3694

we have plotted our training and test loss to visualise our model 

![download](https://user-images.githubusercontent.com/79101972/167283505-71fd7e3d-dca7-4a1e-80d4-1a340ffe9164.png)


We have tested our prediction on the test data set which gives an array whose values are between 0 and 1

we have taken a threshold value of 0.5.i.e, if the value of prediction is more than 0.5 then it will come under class 1 else in class 0
(classification)

**1-->LEAK PIPE**
  
**0-->NON-LEAK PIPE**

**DEPLOYMENT**

After building the model, the model is deployed via a user friendly web interface, namely *Gradio*. Time series is given for the inputs for the output to predict if there's a leak or not.
The Interface class has 3 parameters-the leak_detector function, the input components being Time Series data and the output component showing whether there is a leak or not.


# Hackfest2022

**Goal of our project**

The primary goal of the project is to leverage recent  developments  in  smart  water  technologies  to  detectand  reduce  water  leakages  in  large  water  distribution  networks  with  the  aid  of  neural  networks. We  have  developed two different models, the first model is based on Artificial NeuralNetworks (ANNs) which not give the desired accurecy. The second  model  is  based  on convolutional NeuralNetworks (CNNs) .  CNNS model able  to  correctly  classify  the  leak nodes with good accuracy,

# **DATA COLLECTION**

**Included Files with the repository -**

Data : A portion of used Data to observe the nature

Analysis_and_Model.ipynb : Analysis of Data, Training the model, Testing the model

This data acoustic signals recorded from real and buried water distribution networks (WDNs) in Hong Kong. The signals were collected from about ninety leak sites throughout a period of a year using three different non-destructive technologies, namely noise loggers, hydrophones, and micro-electro-mechanical-system (MEMS) accelerometers. The leak signals were collected when leakage is reported, while the no-leak signals were recorded when a previously visited leak site is repaired. Both leak and no-leak signals were recorded from metal and non-metal pipes. 
In PipeNet, a system based on wireless sensor networks, was proposed. It aims to monitor water flow and detect leaks by attaching acoustic and vibration sensors to large bulk-water pipelines and pressure sensors to normal pipelines. This theory is the major basis for origin of the dataset that we are using from Google dataset.

After downloading the dataset , it was organised such that all the leak and no-leak audio files are separated in two folders. This dataset is then uploaded in the google drive and merged with google colab. A water_leakage.txt file is created and then using os package ,the paths of all the audio files are added in the first column of that text file and then in the 2nd column , those audio files are labeled  as 0 and 1 representing non_leak and leak respectively. Then using pandas , the txt file is converted into csv using the dataframe.to_csv() function. 

Link for Dataset : https://data.mendeley.com/datasets/hkn8mxcjyz/1



# **DATA PREPROCESSING**

We have used LIBROSA python package for audio analysis purpose

Used matplotlib for data visualisation

WE have then normalises the AUDIO DATAS

Used Numpy library for high performance multidimensional array calculations.

Here we have use MFCC(Mel-Frequency Cepstral Coefficients)featrure extraction to extract features from audio files 
which will convert it into an one dimensional array .


# **MODEL**

With the help of tensorflow,Keras python library we have successfully created
a CNN(convolution Neural Network model)

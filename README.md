# Field Flow Estimation of Vehicles
Code for the PyTorch implementation of "Field Flow Estimation of Vehicles" for vehicle data which includes the flow fields like velocity and pressure. I have implemented 2 model Encoder-Decoder model and Style GAN model. So, both are giving the output pretty good so its hard to mention which is performing more better because each model have some pros and cons. I have also provided pretrained weights for each model you can use them to finetune the model incase you requirement to run the model is not satisfied.

# Abstract
In the automobile industry, flow fields, including velocity and pressure fields, are commonly utilized as references for vehicle form design to ensure steering stability and energy conservation. Flow fields are typically estimated using computational fluid dynamics (CFD) simulations, which are time-consuming and costly. Designers want a more efficient and engaging technique for advanced shape discussion and design. In order to do this, we present a fast estimation approach based on 3D convolutional neural networks. To boost estimation efficiency, we use a style extractor to gather sufficient deep features of each vehicle design and apply them using adaptive instance normalisation. In addition, the estimation model is trained using a proposed loss function that consists mostly of a slice-weighted square and a combination loss function. Our suggested method outperforms, particularly in wake regions and near the vehicle surface flow field estimates. As a result, the suggested method enables for the design of vehicle forms while maintaining optimal aerodynamic performance in significantly less time than extended CFD simulations.

# Dataset
A dataset including 3D vehicle shape information and related flow fields is utilized for the training estimation model. The dataset contains unsigned distance functions (uSDFs) as inputs and 3D flow fields around the vehicle as outputs.

# Requirement
  Atleast 16GB GPU memory
  pip install pytorch
  pip install numpy
  pip install torchmetrics 
  pip install pytorchlightning
  pip install matplotlib
  pip install tensorboard
  Use python version>=3.8
  and other you can install if I forgot to mention.
  
# Training
To train the particualar model first install all the packages required and then in the hyparameter.py you can change your parameters according your system requirements and also change the path of training data in the training.py itself and in the dataloder.py match the input format of data with your dataset and in dataloader.py I have used x=x[128:512,64:192,0:64]/255 to extract the important features from the data you can change this according to your need by visualising your own data. You do not need to change anything in the model.py and loss_function.py but you have to make some changes in the Lightning_model.py training.py dataloader.py according to your requirements and also I have implemented 3 loss functions, so you can use any of them and can visualize your ouput on all of them.

# Testing
To test the model you have to make some changes in the dataloader.py take input velocity and pressure vector as a array of list and run the test.py and binary mask of each case is present , where one means the region that allows air to pass through, was added into the dataset. so you can also use that in one of the plots to gain more insights.

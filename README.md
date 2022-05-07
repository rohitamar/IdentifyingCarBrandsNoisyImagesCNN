# Identifying Car Brands in Noisy Images Using Convolutional Neural Networks

## Abstract

The exponential production of cars has resulted in a need for better vehicle classification systems. Such systems include automated highway toll collection, traffic flow control, and perception in self-driving vehicles. These classification systems require improvement in their ability to identify a car based off an image. Most existing research has developed models on clear car images, however, this is not reflective of real world conditions comprised of external factors such as inclement rain, snow, or motion blur. In this paper we seek to classify car brands in noisy and blurry images using convolutional neural networks as a means of better simulating real world conditions. We used the Stanford Cars Dataset, which contains 16,185 images of 196 classes of cars. Our auto-encoder model was able to accept either a noisy/blurred image as input and output an appropriately denoised/deblurred image. Afterwards, training our Resnet architecture for 15 epochs, we were able to identify (predict the make, model and year) of a car image with an accuracy of 82 percent. Our research better tailors models for vehicle classification systems that are consistent with real world conditions.

## Instructions

Run the notebook in the GitHub through Google Colaboratory unless you have a powerful GPU locally. Ensure that you have the appropriate libraries (which are elaborated in the first cell of the notebook) before running the code. 

## Stanford Cars Dataset and pre-trained models

The models we have trained uses the [Stanford Cars Dataset](https://ai.stanford.edu/~jkrause/cars/car_dataset.html "Stanford Cars Dataset"). In order to quickly load, partition, and modify the images of the dataset, we utilized PyTorch's DataLoader class. However, to do so, the dataset must be organized in folders representing the different classes within the dataset. The original dataset has not been organized in such a manner; hence, we downloaded the dataset from [this Kaggle link](https://www.kaggle.com/datasets/jessicali9530/stanford-cars-dataset "Kaggle Dataset Link"), which had already organized in this manner.  

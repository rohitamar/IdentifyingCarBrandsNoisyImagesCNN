# Identifying Car Brands in Noisy Images Using Convolutional Neural Networks

## Authors
* [Rohit Amarnath](https://github.com/rohitamar)
* [Aravind Kumar](https://github.com/aravindk5)
* [Mugdhesh Pandkar](https://github.com/MugPand)

## Abstract

The exponential production of cars has resulted in a need for better vehicle classification systems. Such systems include automated highway toll collection, traffic flow control, and perception in self-driving vehicles. These classification systems require improvement in their ability to identify a car based off an image. Most existing research has developed models on clear car images, however, this is not reflective of real world conditions comprised of external factors such as inclement rain, snow, or motion blur. In this paper we seek to classify car brands in noisy and blurry images using convolutional neural networks as a means of better simulating real world conditions. We used the Stanford Cars Dataset, which contains 16,185 images of 196 classes of cars. Our auto-encoder model was able to accept either a noisy/blurred image as input and output an appropriately denoised/deblurred image. Afterwards, training our Resnet architecture for 15 epochs, we were able to identify (predict the make, model and year) of a car image with an accuracy of 82 percent. Our research better tailors models for vehicle classification systems that are consistent with real world conditions.

## Instructions

Run the notebook in the GitHub through Google Colaboratory unless you have a powerful GPU locally. Ensure that you have the appropriate libraries (which are elaborated in the first cell of the notebook) before running the code. 

## Stanford Cars Dataset and pre-trained models

The models we have trained uses the [Stanford Cars Dataset](https://ai.stanford.edu/~jkrause/cars/car_dataset.html "Stanford Cars Dataset"). In order to quickly load, partition, and modify the images of the dataset, we utilized PyTorch's DataLoader class. However, to do so, the dataset must be organized in folders representing the different classes within the dataset. The original dataset has not been organized in such a manner; hence, we downloaded the dataset from [this Kaggle link](https://www.kaggle.com/datasets/jessicali9530/stanford-cars-dataset "Kaggle Dataset Link"), which had already organized in this manner. Note that you only need this dataset (which is about 2GB of storage!) if you would like to build a model from this dataset. We have attached our pretrained models in the models folder of this repository -- we also have code that shows exactly how to get it running on your notebook. Lastly, note that both the dataset and the pre-trained models must be stored in your Google Drive if you're using Colaboratory (if you're using locally, you will have to switch all the paths). This also requires you to mount your drive, which we have  also shown how to do.

## Results
We trained Resnet with 10 epochs on the training and test sets. Initially, in the first epoch, we recorded an accuracy of 22.0956 on the training set and 27 percent on the test set. With training, at the 10th epoch, our model achieved an accuracy of 97.8554 on the training set and 82 percent on the test set. The high level of accuracy achieved represents that given an image as input, we will be able to accurately identify the make, model and year of a car.

Finally, we sought to test validate the high accuracies obtained in the previous steps. We sought to see whether our linked system, where we linked our denoising and deblurring models with Resnet, could correctly classify a car given an input image. To test our overall project, we passed in an image of a Toyota Camry Sedan 2012. Our model was able to accurately identify the make, model, and year of the car with confidence 11.2752. The confidence appears to be somewhat low, however given the level of specificity of a car that the model predicts, this confidence level is satisfactory.

<figure>
<img src="images/blurToClear.png" alt="blurToClear" style="width:100%">
<figcaption align = "center"><b>Fig.1: Deblurring Model </b></figcaption>
</figure>


<figure>
<img src="images/noiseToClear.png" alt="noiseToClear" style="width:100%">
<figcaption align = "center"><b>Fig.2: Denoise Model </b></figcaption>
</figure>

The above images showcase the results of our deblur and denoise image. As you can see, the autoencoder worked fairly well in removing the noise within the image and then sharpening to match the original image. The below image shows the entire pipeline in action.

<figure>
<img src="images/results.png" alt="results" style="width:100%">
<figcaption align = "center"><b>Fig.3: Final Results </b></figcaption>
</figure>

## Future Direction
Currently, our model only classifies clear images, blurry, and noised images. In the future, this capability could be extended to images that are both noisy & blurry, as well as images that include harsh angles of rotation. We may utilize many of the techniques suggested by Krause and colleagues in handling vehicle datasets and potentially converting 2D images into 3D scans that may offer more insight into brand localization. We may also attempt to expand the research done by Xinchen Liu and colleagues on a deep learning approach for urban surveillance that utilizes a two pass process of coarse-to-fine and near-to-distant search techniques.

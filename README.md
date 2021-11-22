# Image-Classification-with-CNN

This repo includes an approach for classification of Natural Scenes around the world. A detailed explanation with some metrics can be found below. 

## Problem details


![image](https://user-images.githubusercontent.com/68281371/142773289-307c598e-e25f-4da6-b46b-fd16011ee01e.png)

![image](https://user-images.githubusercontent.com/68281371/142773624-1bab963b-d00d-4024-a51e-4147d9e326ed.png)

Main task is to classify the images with respective categories:

- Buildings
- Forest 
- Glacier
- Mountain 
- Sea
- Street

The accompanying Kaggle kernel can be found here: https://www.kaggle.com/puneet6060/intel-image-classification

## Model 

I used the Resnet50 which was pretrained on the ImageNet dataset. I have used the fastai library as it provides a lot of flexibility, speed, easo-of-use. Fastai also has implemented a Learning rate finder which provides the best value for the learning rate parameter after training a sample batch. 

## Image augmentations 

I used the following Image augmentations

- Flip 
- Rotation 
- RGB Randomize
- Random lighting and contrast change
- Jitter

### Images with Augmentations
![image](https://user-images.githubusercontent.com/68281371/142777425-a76f9aaf-6a62-4865-9397-901515d2ebe9.png)

### Resnet50 
![image](https://user-images.githubusercontent.com/68281371/142839898-6b53404a-062a-468b-8138-af96381ea765.png)

Top losses and confusion matrix 

![image](https://user-images.githubusercontent.com/68281371/142841337-428cd45e-e9f7-4e74-a1e8-296ac04a46b0.png)

The number of classes correctly classified and the number of classes misclassified can be clearly seen by the confusion matrix. The model struggles to classify mountains and glaciers and buildings and streets as the dataset is a bit inconsistent in this regard. Some images are also not properly labelled. 

![image](https://user-images.githubusercontent.com/68281371/142841625-43e350d9-c2be-47f0-8713-657e4621e06f.png)

## Further Learning
- We can try implementing deeper architectures like the Resnet101 which has deeper layers and is capable of capturing more fine grained features
- Based on a couple researches, the fundamental problem of Imagenet pretrained models are that they are pretrained on an object classification dataset therefore it becomes an arduous task to train all the layers instead of just training the last layers of the model. An approach based on the Resnet50 model pretrained on the Places365 dataset should be able to perform better
- A significant boost could be achieved by removing mislabelled images or images which have a low confidence score

## Run 

In order to run the Resnet50 model run the [ImageClassificationwithCNN.ipynb](ImageClassificationwithCNN) file







# Joint-Object-Detection-and-Depth-Estimation
 # **Deep Learning Final Project**
 
 **Joint Object Detection and Depth Estimation**
 
 
 In this project,  we designed a network that consists of two main modules, namely depth estimator and object detector. This module can detect objects and determine their depth by considering a certain depth. We explained every section in detail in the Report file. 
 ## **Depth Estimation**
 
 The goal of this part is to develop a Deep Learning Model for Monocular Depth Estimation. We got inspiration from these two articles. : 
 [U-Net: Convolutional Networks for Biomedical Image Segmentation](https://arxiv.org/abs/1505.04597)
 and [High Quality Monocular Depth Estimation via Transfer Learning](https://arxiv.org/abs/1812.11941).
 Both of the models are trained on NYUv2 Dataset and we saved the weights for both networks.
 
 This project implements the UNet Convolutional Neural Network with a ResNet encoder (pre-trained on imagenet weights) on the NYU-Depth v2 dataset and achieved a soft accuracy of 83% on the test set.
 
 We explained both networks in detail in the Report file.
 
 Blow images show the original image and the depth map. 
 
 ![](https://github.com/Fateme-Azizabadi/Joint-Object-Detection-and-Depth-Estimation/blob/main/Images/Original.Image.jpg)
 
 ![](https://github.com/Fateme-Azizabadi/Joint-Object-Detection-and-Depth-Estimation/blob/main/Images/Depth.Map.png)
 
 
 
 ## **Object Detection**
 
 For the object detection task, we used two pre-trained models, namely YOLOv4 and the API TensorFlow. We explained each of these networks in detail in the Object Detection section in the Report file. Since the YOLOv4 network gives us better accuracy, YOLOv4 is used for the joint model.
 
 The image below shows the output of the YOLOv4 object detector. 
 
 ![](https://github.com/Fateme-Azizabadi/Joint-Object-Detection-and-Depth-Estimation/blob/main/Images/Object.Detection.png)
 
 ## **Joint Object Detection and Depth Estimation**
 
 To connect these two networks, the Detector and Depth Module receive the input image simultaneously and perform object detection and depth estimation operations, respectively. Then we read the center of the Bounding Box of each detected object from the output of the Detector and find the depth attributed to that center by the Depth Module. Finally, we display these depths on the image for each of the Bounding Boxes.
 
 
 The image below shows the output of the joint module. 
 
 ![](https://github.com/Fateme-Azizabadi/Joint-Object-Detection-and-Depth-Estimation/blob/main/Images/Joint.png)
 
 ## **Joint Object Detection and Depth Estimation with Threshold**
 
 To estimate the depth of each object and detect them from a certain depth, a function is written. This function receives the image storage path and the threshold value desired by the user from the input and delivers the output image.
Firstly, we estimate the depth of the image using the Depth Module and masking the image based on the given threshold. Secondly, this masked image is given to the Detector to detect objects. Finally, Bounding Boxes and the depth of each BBOX are displayed on a clean image and delivered to the user. 

We explained this section in detail in the Report file. 

The image below shows the output of the joint module with threshold. We consider Threshold=4 meter for this image. 
 
 ![](https://github.com/Fateme-Azizabadi/Joint-Object-Detection-and-Depth-Estimation/blob/main/Images/Joint.with.Threshold.png)
 
 

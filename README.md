# Surgical-Tool-Type-Classification
## Written by-
### Md. Kamrul Hasan 
### Erasmus Scholar on Medical Imaging and Application (MAIA) [http://maiamaster.udg.edu/]
### For more details write me at kamruleeekuet@gmail.com
[![MKH](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)] <br />

In this project, the different types surgical tool is classified using CNN where in training directory, there are 5 types of tools as shown in Figure below: 

![ToolTypeDefinition](https://user-images.githubusercontent.com/32570071/54871230-28c41500-4db1-11e9-80ff-bca41f4caf40.PNG)

To implement this DCNN classification Network, VGG16 has been used. VGG16 was fitted with the pre-trained model that trained on ImageNet. 

To overcome overfitting due to limited numbers of training images, first 10 layers of VGG16 (See the figure below) which is block2_pool has been frozen. Because at the beginning layers of DCNN, only low label of features are learning.  

Another point to be noted that the training images are not balanced which are like below- <br>
{'Type01': 0, 'Type02': 1, 'Type03': 2, 'Type04': 3, 'Type05': 4} <br>
{0: 1.0, 1: 1.72, 2: 1.47, 3: 14.0, 4: 5.89}

To overcome this class unbalancing, following code has been used which return the class weight that can be added to the fit generator to calculate the total cost function. 
![classBalance](https://user-images.githubusercontent.com/32570071/54871748-b3107700-4db9-11e9-95ec-81c618eba2af.PNG)

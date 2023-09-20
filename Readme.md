# <b> Comparing Various variants of VGG with MLP </b>

I am using the DuckDuckGo API to download images for my project. Downloaded 100 images of two classes - I chose Anteater and Capibara as my classes. After downloading 100 images of both the classes i have compared various variants of VGG with MLP. I have also compared the performance of VGG16 with and without data augmentation.

<br>

## <b> Observations </b>

|Model  | Training Time        | Training Loss  | Training Accuracy | Testing Accuracy | Number of model parameter |
| :--------------:|:----------------:|:-------------:| :---------------:|:-------------:|:------------:|
| VGG (1 block) | 505.7 s      | 0.0131 | 100.00 |69.70 |40,969,345 |
| VGG (3 block) | 359.5 s     | 0.0578      |   100.00 |77.273 |10,341,697 |
| VGG (3 block) with data augmentation | 437.6 s | 0.3768      |    88.50 |83.333 |10,341,697 |
| Pre-trained VGG16  | 1554.3 s | 0.0321   |  100.00 |92.424 |17,082,433 |    
|MLP|  295.5 s | 0.0052 | 100.00 |  75.758 |  17,083,585 |


<br>

### <b> Number of model parameters </b>
Number of model parameters is increasing with the increase in number of layers within the model. VGG1 is however an exception to this rule. This is because VGG1 has less numbers of VGG blocks hence the size of image is not reduced. When this image is flattened out and connected to fully connected layers, the number of parameters increases.

### <b>Training time.</b> 
Training time is increasing with the increase in number of model parameters. Model parameters will increase with increase in number of layers and number of filters in each layer. 

### <b> Training loss </b>
Training loss is decreasing with the increase in number of model parameters. This is because with increase in number of model parameters, model is able to learn more complex patterns in the data. VGG3 with data augmentation shows more loss than VGG3 without data augmentation. This is because VGG3 without data augmentation is able to overfit the train data as the epochs increases while VGG3 with augmentation cannot do so. Data augemtaion is a regularization technique, adding noise to the training data, and encouraging the model to learn the same features, invariant to their position in the input. This makes the model move away from the overfitting region due to which loss is more.

### <b> Training accuracy </b>
Training accuracy is increasing with the increase in number of model parameters. This is because with increase in number of model parameters, model is able to learn more complex patterns in the data.

### <b> Testing accuracy </b>
Testing accuracy is increasing with the increase in number of model parameters. This is because with increase in number of model parameters, model is able to learn more complex patterns in the data. MLPs and VGG1 is an exception to this rule. This is because MLPs and VGG1 are not able to learn complex patterns in the data.

<u>Note:</u> Training accuracy and testing accuracy are not same because model is overfitting the train data as the epochs increases. 


<br>

## <b> Data Augmentation </b>

Training deep learning neural network models on more data can result in more skillful models, and the augmentation techniques can create variations of the images that can improve the ability of the fit models to generalize what they have learned to new images.

Image data augmentation is a technique that can be used to artificially expand the size of a training dataset by creating modified versions of images in the dataset.Data augmentation can also act as a regularization technique, adding noise to the training data, and encouraging the model to learn the same features, invariant to their position in the input.

<br>

## <b> Epochs vs Model Performance </b> 

As the number of epochs increases, the model performance increases. This is because the model is able to learn more complex patterns in the data. However, the model performance saturates after a certain number of epochs. This is because the model is overfitting the train data as the epochs increases.

<br>

<img src = ./plots/VGG_16_plot.jpg>

<br>

As evident from the graph above the model performance saturates after 30 epochs. This is because the model is overfitting the train data as the epochs increases.

<br>

## <b> MLPs vs VGG16 </b>

MLP is unable to perform as good as VGG16 even though have similar number of parameters. One of the main problems is that spatial information is lost when the image is flattened(matrix to vector) into an MLP. 

CNN architecture like VGG  work well with data that has a spatial relationship. Therefore CNNs are go-to method for any type of prediction problem involving image data as an input.The benefit of using CNNs is their ability to develop an internal representation of a two-dimensional image. This allows the model to learn position and scale in variant structures in the data, which is important when working with images.


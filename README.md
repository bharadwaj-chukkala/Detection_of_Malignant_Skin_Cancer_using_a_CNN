# Detection_of_Malignant_Skin_Cancer_using_a_CNN

## Objective: 
To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution which can evaluate images and alert the dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.

### Summary of the Skin Cancer Data:

1. Total number of images: 2357
2. Images consist of Bening and Malignant Oncological Diseases.
3. Data was gathered by ISIC (International Skin Imaging Collaboration).
4. Images were sorted according to the classification taken with ISIC.
5. All the subsets were divided into the same number of images, with an excpetion for melanomas whose images are slightly dominant.

### Diseases in the Dataset
 1. Actinic keratosis
 2. Basal cell carcinoma
 3. Dermatofibroma
 4. Melanoma
 5. Nevus
 6. Pigmented benign keratosis
 7. Seborrheic keratosis
 8. Squamous cell carcinoma
 9. Vascular lesion

## CNN Model Architecture
- The CNN is a Sequential Model type which allows us to construct our Neural Network Architecture layer by layer
- The Architecture will be a combination of 2D convolution layers along with Max pooling in this architecture.
- We will be using activation functions Softmax and RelU.
- Why am i using ReLU?, Because it is simple, effective and addresses the problem of vanishing gradients. 
- Why am i using Softmax?, Because it makes interpreting the outputs of the Neural Network easier in the case of Multi-Class Classification by normalizing the outputs to probablities.

### Architecture -> Rescaling + Convolution + Pooling + Dropout + Flatten + Dense
- **Rescaling**:  rescaling the input data ensures that all features are on a similar scale.
  - This is particularly important when working with different types of features, such as pixel intensities and spatial coordinates, as having features with disparate scales can lead to biased or inefficient learning.
  - a rescaling layer also helps to mitigate the influence of outliers in the data. Outliers, which are data points that significantly deviate from the majority of the data, can adversely affect the model accuracy.
- **Convolution**: It is specifically designed to process and analyze spatial structures in data such as images.
  - A convolutional layer applies a set of learnable filters to the input data, convolving them with the input pixels to extract and learn meaningful features. 
  - These filters act as feature detectors, capturing different characteristics like edges, textures, or patterns present in the input. 
  - By repeatedly applying these filters, a convolutional layer hierarchically learns and abstracts more complex features at different scales.
- **Pooling**: Also known as a subsampling layer, it's primary purpose is to reduce the spatial dimensions (width and height) of the input volume, while retaining the most important information.
  - They help to reduce the computational complexity of the network by decreasing the number of parameters and operations. This allows the CNN to process larger input volumes more efficiently.
  - Pooling layers introduce a form of translation invariance in the network by aggregating neighboring features and extracting their most representative elements.
- **Dropout**: This layer is used for regularization purposes. It helps reduce overfitting, which occurs when the model becomes too specialized to the training data. 
  - A dropout layer randomly selects a fraction of the neurons (typically 20-50%) in a neural network and temporarily "drops out" or turns off these neurons during training. This means that these neurons do not contribute to the forward and backward pass of the network, effectively reducing the complexity and capacity of the model.
  - By dropping out neurons, the model becomes less reliant on a single set of features and learns to create redundant representations. This helps in creating more robust and generalized features, thereby improving the model's ability to generalize and perform well on unseen data. 
- **Flatten**: It is primarily used to transform multidimensional data into a one-dimensional array.
  - In neural networks, data is typically represented in the form of tensors, which are multi-dimensional arrays. However, many algorithms and functions in machine learning and deep learning are designed to work with one-dimensional input. 
  - This is where the flatten layer comes into play. The flatten layer takes the multi-dimensional input and reshapes it into a one-dimensional array. This is done by sequentially stacking all the elements of the input array one after another. The resulting flattened array can then be easily fed into the subsequent layers of the network.
- **Dense**: It is used to connect every neuron from the previous layer to the neurons in the current layer.
  - The purpose of a dense layer is to allow the network to learn complex patterns and relationships in the data.
 
## References
1. [Convolution Layers for CNNs](https://machinelearningmastery.com/convolutional-layers-for-deep-learning-neural-networks/)
2. [Pooling Layers for CNNs](https://machinelearningmastery.com/pooling-layers-for-convolutional-neural-networks/)
3. [Dropout Layers for CNNs](https://towardsdatascience.com/dropout-in-neural-networks-47a162d621d9#:~:text=Dropout%20layers%20have%20been%20the%20go%2Dto%20method%20to%20reduce,modern%20era%20of%20deep%20learning.&text=In%20this%20era%20of%20deep,career%20of%20building%20neural%20networks.)
4. [Dense Layers for CNNs](https://analyticsindiamag.com/a-complete-understanding-of-dense-layers-in-neural-networks/)
  - By connecting all the neurons in the previous layer to the current layer, the dense layer can capture interactions between all the features present in the input data. 
  - This enables the network to make non-linear transformations and extract higher-level representations.

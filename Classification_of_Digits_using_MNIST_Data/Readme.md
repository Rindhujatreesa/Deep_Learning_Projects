## Classification of MNIST data using NumPy Only

This project attempts to classify digits with Convolutional Neural Network using ***Numpy*** library

### Data Source
The MNIST dataset is used to fit the CNN model. 
A quick glimpse of the dataset - 
|  Data  |  Size  |
|--------|--------|
| MNIST_784 | 70000 $\times$ 784 |
| Train | 60000 $\times$ 784 |
| Test  | 10000 $\times$ 784 |

### Methodology

1) Data Pre-Processing

 - Reshaping each row in (28, 28) shaped array
 - Splitting the data set into training and testing sets
 - One-hot Encoding for the classification

2) Defining Function classes for CNN

 - Linear Layer
 - ReLU Layer
 - Softmax activation With Cross Entropy Loss
 - 2D - Convolution
 - 2D Max Pooling
 - Stochastic Gradient Descent Optimization

3) Training and Testing Model

#### One Hot Encoding
One-hot encoding of labels helps represent categorical variables as binary vectors. 
- This enables the machine-learning algorithms to function directly without any bias or incompatibility.
- We convert each of the digits from 0 to 9 into an array of zeros and ones such that the position in the array where it is equal to the value will be 1 and the rest will be zero.

#### Linear Layer (Fully Connected)
This layer will contain weights and biases. 
  During the forward pass, we'll compute the matrix multiplication and addition as:
  
$X.W + b$

#### ReLU Layer
The ReLU (Rectified Linear Unit) activation function will transform input values of <code>x</code> to:

$max(0, x)$

#### SoftMax Activation with Cross Entropy Loss
After the final layer, we'll use a softmax function to get probability distributions for multi-class classification. The cross-entropy loss will then measure the difference between the predicted and true distributions. The formula for the softmax function for a given input 
<code>z</code> is:

<code>softmax(z<sub>i</sub>) = exp(z<sub>i</sub>) / &Sigma; exp(z<sub>j</sub>)</code>

Where the summation is over all classes. The cross-entropy loss for true labels <code>y</code> and predicted probabilities <code>p</code> is:

<code>-&Sigma; y<sub>i</sub> log(p<sub>i</sub>)</code>

#### 2D - Convolution
The convolutional layer will contain filters (or kernels) that will be convolved with the input image to detect patterns. The convolution operation for an input <code>I</code> and a filter <code>F</code> is:

<code>(I &ast; F)(x, y) = &Sigma; &Sigma; I(x - i, y - j) F(i, j)</code>

#### 2D Max Pooling
Max pooling will downsample the input based on the maximum value in a region. For a given region <code>R</code> in the input:

<code>max_pool(R) = max(R)</code>


#### Stochastic Gradient Descent (SGD) Optimization
SGD will be used to update the weights based on the gradients computed during backpropagation. The weight update rule is:

<code>W<sub>new</sub> = W<sub>old</sub> - &alpha; &times; dW</code>

Where <code>&alpha;</code> is the learning rate and <code>dW</code> is the gradient of the loss with respect to the weights.

## Conclusion
- In this implementation, a Convolutional Neural Network (CNN) model for classifying handwritten digits from the MNIST dataset was developed and trained. 
- The model architecture consists of a convolutional layer followed by ReLU activation, max-pooling, and a fully connected layer with softmax activation for multiclass classification.
- The model was trained using the Stochastic Gradient Descent (SGD) optimizer over 5 epochs with a batch size of 250.
- During training, the model learned to recognize intricate patterns and features in the input images, enabling it to make accurate predictions.
- The training process involved iterative forward and backward passes, adjusting the model's parameters to minimize the softmax cross-entropy loss.
- After the training process, the model demonstrated a high level of accuracy on the unseen test dataset, achieving an accuracy of 96.44%.

<b>This high test accuracy indicates the effectiveness of the CNN architecture and the optimization techniques used.</b>

# Swish (SiLU) vs ReLU

## To clone this repo

`git clone https://github.com/ruvate/swish-vs-ReLU.git `

To run the code use ` python3 src.py <path_to_folder> `.

## choice of Activation Function

The choice of activation functions in Deep Neural Networks has a signficant impact on the training dynamics and task
performance. Currently, the most successful and widely-used activation function is the Rectified Linear Unit (ReLU),
which is f(x) = max(0, x). Although various alternatives to ReLU have been proposed, none have managed to replace it due
to inconsistent gains. So, google brain team has proposed a new activation function, named *Swish*, which is simply f(x)
= x * sigmoid(x). Their experiments show that Swish tends to work better than ReLU on deeper models across a number of
challenging datasets. For example, simply replacing ReLUs with Swish units improves top-1 classification accuracy on
ImageNet by 0.9% for Mobile NASNet and 0.6% for Inception-ResNet-v2.

Swish function can be seen as a smoothing function which nonlinearly interpolates between a linear and the ReLU
function.


## results 

I tried making a small CNN+LSTM network and observe the difference in accuracy on MNIST dataset; the obtained results
were interesting. 

- When working with the combination of CNN + LSTM network, ReLU performs a tiny bit better (~0.6%) than Swish activation
  function. 
- However, when we remove the LSTM part and only work with CNN attached to fully connected layers. Swish significantly
  outperforms ReLU in terms of test accuracy on 10,000 images.

I would recommend to use **Swish** activation function for your own Neural Architecture instead of ReLU and seeing what
difference does it make on the performance of the model. 


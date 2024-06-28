# Neural Networks

*from 3Blue1Brown*

- ***Note :-*** Throughout the explanation, we consider a neural network taking a square image of 28*28 = 784 pixels and giving one of the 10 outputs - 0 to 9. This Neural Network consists of 2 hidden layers, each having 16 Neurons. The input and output layers have 784 neurons and 10 neurons respectively.

# Sturctural Aspects and Basic Working :-

## 1. *Neuron -*

 A thing that holds a number ranging from 0 to 1 (termed as ‘Activation’ of the neuron).

## 2. *Layers -*

A set of neurons, which are connected to several other sets of Neurons. The layers of neurons present between the input layer and the output layer, are termed as ‘*Hidden Layers*’. 

- In case of a neural network identifying handwritten digits, the neurons in the hidden layers can be thought of to be activated when certain characteristic parts e.g. a straight line or a loop in upper side of image, is detected.
- The activation of neurons of input layer cause activation of some specific neurons in subsequent layers and ultimately, some neurons in last layer activate to varying extents. The neuron which is the mst activated, in the output layer, provides the neural network’s best guess of output for the input provided.

![Screenshot from 2024-06-28 15-16-56.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_15-16-56.png)

- It can also be thought that neurons from previous hidden layer detect parts of these; loops or lines. Hence, detection of small structures in image in various layers cause activation of certain neurons in subsequent layers and thus, can detect the image.

![Screenshot from 2024-06-28 15-23-12.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_15-23-12.png)

## 3. *Weights -*

Weights are real numbers, either positive or negative, assigned to the connection between 2 partcular neurns, each being from adjacent layers. Weights are multiplied with activation of neuron from previous layer and then, carrying out the same for all neurons of previous layer, sum of all these numbers, i.e. ‘*weighted sum*’ is passed to the connected neuron of next layer. Here, ‘w’ are weights and ‘a’ represents activation of neurons of previous layer, which has ‘n’ neurons.

![Screenshot from 2024-06-28 15-30-18.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_15-30-18.png)

## 4. *Bias -*

Bias is any number, which indicates threshold value of the activation of a neuron due to the neurons frm previous layer. It is subtracted from the weighted sum. 

For example, here, the bias is ‘10’.

![Screenshot from 2024-06-28 16-26-57.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_16-26-57.png)

## 5. *Squishification function -*

The value of weighted sum, along with correction of bias, can turn out to be any real number; s as to simplify calculations, we try to scale down the values of weighted sum to a value ranging from 0 to 1 using a squishificatin function. Here, sigmoid function is used.

E.g. Sigmoid, ReLU, softmax, etc.

![Sigmoid Function](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_16-38-54.png)

Sigmoid Function

![Rectified Linear Unit (ReLU)](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_16-40-23.png)

Rectified Linear Unit (ReLU)

- Hence, the functioning of Neural Network depends solely on the values of weights and biases. Basically, in the process of *‘**Learning**’* the Neural Network adjusts its weights and biases after each input and thus, imroves itself.
- General Representation of above equations :

![Screenshot from 2024-06-28 16-36-05.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_16-36-05.png)

# Operation Mechanism of Neural Network :-

- A labelled dataset is provided as input to the neural network. Depending on the differences between the output f neural netwprk and the expected output, the values of required weights and biases are adjusted so that the neural network will perform better on subsequest data. This is the process by which a Neural Network learns.
- Thus, the main goal is to generalize the action of Neural Network. Hence, after training it on ‘Training Data’, which is labelled, it is also checked with ‘Testing Data’, whichj cntains unlabelled data elements, whu=ich are completely new for the Neural Network and its accuracy is analysed.

## 1. *Cost Function -*

- Initially, we randomly assign weights and biases of the Neural Network. In this scenario, the Neural network performs very badly, with (maybe) some exceptions of good guesses.
- Now, we take the square of the difference of the activations of each of the neurons of the output layer and add them together. This value is termed as ‘***Cost***’ of the corresponding training example (training input). Higher the cost, worse is the performance of the Neural Network.
- The cost of all training examples are noted; they form the data points of the ‘***Cost Function**’ .*

## 2. *Gradient Descent and Introduction to Backpropagation -*

- We aim to minimize the cost, i.e. we are concerned about the minima of the cost function. Hence, we use the result from Multivariable Differential Calculus, that, the gradient of a function gives the direction of maximum slope. We then tend to the minima by traversing path along the function, in direction opposite to that of the Gradient. Then, we can trace the values of parameters of that function; for cost function, they would be the weights and biases in the Neural Network, and change them accordingly.
- One drawback of this method is that it turns out to be complicated for complicated cost functions, which have a larger number of minima.
- Hence, we choose any arbritry point on the curve of cost function, and measure its Gradient around that point; we tend to traverse the function in the direction opposite to that of the Gradient. Continuing this repeatedly, one can approach the local minimum of the cost function.
- The negative Gradient of the cost function for all weights and biases, for each step, gives the changes that need to made in the weights and biases so that the value of the cost function decreases. Each of its values also gives information as to which input of the cost function needs to be modified to how much extent, and to either be increased or decreased.
- The algorithm which performs the above changes to weights and biases, is termed as ‘***Backpropagation***’.
- Smoother variations in cost functions are needed for finding the corresponding local minimum accurately. Hence, the activations of neurons of last layer (as cost function depends on them) have values which vary smoothly; rather, all neurons have continuoulsy variable activations.
- ***Gradient Descent*** - the process of repeatedly varying the input of a function by using a multiple of negative gradient of the function.
- It is observed that for this particular Neural Network under consideration, it is not like the neurons of the hidden layers identify specific patterns in the input image, but its like of a more random form of arrangements of pixels. ALs, this is why even when we provide the Neural Network with a random image, it gives a confident guess out of the 10 digits, though it is wrong.
- It is observed that Neural Networks learn properly labelled data faster than randomly labelled data.
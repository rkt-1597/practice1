# Neural Networks

*from 3Blue1Brown*

# Sturctural Aspects and Basic Working:-

## 1. *Neuron -*

 A thing that holds a number ranging from 0 to 1 (termed as ‘Activation’ of the neuron).

## 2. *Layers -*

A set of neurons, which are connected to several other sets of Neurons. The layers of neurons present between the input layer and the output layer, are termed as ‘*Hidden Layers*’. 

- In case of a neural network identifying handwritten digits, the neurons in the hidden layers can be thought of to be activated when certain characteristic parts e.g. a straight line or a loop in upper side of image, is detected.
- The activation of neurons of input layer cause activation of some specific neurons in subsequent layers and ultimately, some neurons in last layer activate to varying extents. The neuron which is the mst activated, in the output layer, provides the neural network’s best guess of output for the input provided.

![Screenshot from 2024-06-28 15-16-56.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_15-16-56.png)

- It can also be thought that neurons from previous hidden layer detect parts of these ;loops or lines. Hence, detection of small structures in image in various layers cause activation of certain neurons in subsequent layers and thus, can detect the image.

![Screenshot from 2024-06-28 15-23-12.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_15-23-12.png)

## 3. *Weights -*

Weights are real numbers, either positive or negative, assigned to the connection between 2 partcular neurns, each being from adjacent layers. Weights are multiplied with activation of neuron from previous layer and then, carrying out the same for all neurons of previous layer, sum of all these numbers, i.e. ‘*weighted sum*’ is passed to the connected neuron of next layer. Here, ‘w’ are weights and ‘a’ represents activation of neurons of previous layer, which has ‘n’ neurons.

![Screenshot from 2024-06-28 15-30-18.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_15-30-18.png)

## 4. *Bias -*

Bias is any number, which indicates threshold value of the activation of a neuron due to the neurons frm previous layer. It is subtracted from the weighted sum. Here, the bias is ‘10’.

![Screenshot from 2024-06-28 15-34-44.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_15-34-44.png)

## 5. *Squishification function -*

The value of weighted sum, along with correction of bias, can turn out to be any real number; s as to simplify calculations, we try to scale down the values of weighted sum to a value ranging from 0 to 1 using a squishificatin function. 

E.g. Sigmoid, ReLU, softmax, etc.

 

![sigmoid.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/sigmoid.png)

![Screenshot from 2024-06-28 15-47-44.png](Neural%20Networks%20182a99e3c172458bac92a1430a6cff2e/Screenshot_from_2024-06-28_15-47-44.png)
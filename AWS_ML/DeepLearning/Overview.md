# Deep Learning Frameworks

A GPU is capable of parallelizing a lot of neurons, and you can also have more than one GPU on one computing node, and you can have many nodes in a cluster.  
So you could really scale this up infinitely, and build something massive, maybe even brain-scale someday.

However, we need some sort of a framework to use this from a programming standpoint and actually define the networks that we want to set up before they're sent out to training on your GPUs.  
A very popular choice is **Tensorflow**, which is made by Google and it also incorporates a higher level API called Keras that we'll look at here.
This is actually a snippet of real Keras code here that's setting up a neural network similar to the one that we just looked at.

<p style="color:darkblue;">
model = Sequential()<br>  
model.add(Dense(64, activation='relu', input_dim=20))<br> 
model.add(Dropout(0.5))<br> 
model.add(Dense(64, activation='relu'))<br> 
model.add(Dropout(0.5))<br> 
model.add(Dense(10, activation='softmax'))<br> 
sgd = SGD(lr=0.01, decay=1e-6, momentum=0.9, nesterov=True)<br> 
model.compile(loss='categorical_crossentropy', optimizer=sgd, metrics=['accuracy'])<br> 
</p>

Basically, it has a dense layer of 64 neurons that has a input dimension of 20.  
So we're feeding in 20 input neurons. That might be a one-hot encoded category of 20 different categories, for example.  
We're adding a dropout layer for regularization.  
There's another layer of neurons in the middle there of 64, with a activation function called ReLU, another dropout layer and finally, an output layer that has 10 output classification neurons at the end using Softmax issues in one of them.  
We also define the optimizer function here, in this case called SGD, and we compile the model and at that point we can train it, and make predictions from it.   

Now, in addition to **Tensorflow and Keras**, there's also something called **Apache MXNet**.

# Types of Neural Networks

There are three main types of neural networks:
1. **Feed forward Neural network** - You just have a bunch of layers of neurons on top of each other, where you feed in your features at the bottom, and output predictions of classifications come out at the top.
2. **Convolutional Neural networks (CNN)** - Those are commonly used for image classification, because they're built to deal with two-dimensional data.  
So if you need to figure out if there's a stop sign in an image, a CNN is probably what you'll use for that.
3. **Recurrent Neural Networks (RNN)** - These generally are made for dealing with sequences of some sorts, sequences in time perhaps like making predictions of stock prices over time or just things that have some order to them.  
So for example, you might use an RNN for machine translation.  
If you want to understand the words in a sentence, and the order of those words matter, an RNN might be a way of capturing those relationships, and predicting how to complete a sentence, or how to translate a sentence from one language to another.   

Couple of key acronyms in that space are **LSTN** (long, short-term memory) and **GRU** (gated recurrent unit).  


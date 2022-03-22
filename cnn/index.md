| [Homepage](https://dl4genaudio.github.io) | [Course content](https://dl4genaudio.github.io/#course-content) | [Spanish](https://dl4genaudio-github-io.translate.goog/cnn/?_x_tr_sl=auto&_x_tr_tl=es&_x_tr_hl=en&_x_tr_pto=wapp) |

# Convolutional Neural Networks (CNNs)

## Representing data as tensors

* So far, the data we put in a neural network has looked like a matrix `NxD`, where `N` is the number of datapoints we are using to do a gradient descent step, and `D` is the number of features in each datapoint. 

* Instead of matrices, we can use tensors to represent data with more dimensions. For example, a tensor can be used to represent datapoints that are magnitude spectrograms with dimensions `NxTxF`, where `T` is the number of time bins in each datapoint, and `F` the number of frequency bins.

* We can also use a tensor to represent datapoints as complex spectrograms if we separate the real and imaginary parts and stack them to obtain a tensor of shape `NxTxFxC`, where `C=2` and each `C` is a "channel", with channel 1 being the real part and channel 2 being the imaginary part of the complex spectrogram. 

## CNN operations

* To understand how CNNs work, we must understand their origins in image recognition.

* Before CNNs, for a neural network to be able to process images, one needed to flatten all the pixels in a tensor with image datapoints (shape `NxWxHxC`) into a matrix (shape `Nx(W*H*C)`).

* 2D CNN operations were developed by [Yann LeCunn](https://en.wikipedia.org/wiki/Yann_LeCun) in the late 80s, and work as follows:
    * Do NOT flatten the image tensor and leave it in the form `NxTxFxC`
    * Use `M` filters with shape `KxLxC` to convolve with each datapoint ([visualize convolution here](https://towardsdatascience.com/intuitively-understanding-convolutions-for-deep-learning-1f6f42faee1))
        * `K<=T`, `L<=F`
    * Add `M` biases, one for each of the `M` filters
    * Apply a non-linearity to the output.
    * What's the shape of the output?

* A convolutional operation is very often followed by a pooling operation ([visualize the pooling operation here](https://www.geeksforgeeks.org/cnn-introduction-to-pooling-layer/)). A pooling layer further reduces redundancy in the output of a convolutional layer as follows:
    * Pass a window of size `QxR` (`Q<=T` and `R<=F`) over the convolutional output
    * In each window, keep only the largest value (max-pooling) or the mean (mean-pooling)

## CNN operations on audio signals

* When working with time-frequency representations of audio signals, the same principle proposed by Yann LeCunn can be used. 

* However, we can also use 1D convolutions on audio data with shape `NxT`.
    * What would be the shape of the convolutional filter(s) in this case?
    * How would the pooling operators look like?

## From CNN features to a neural network output

* After a series of convolution+pooling operations, the hidden layers must be reshaped into a matrix form (via a flattening operator) to use the usual dense layers in a neural network and produce and output. 

* As a result, a CNN can have a final ourput that is either a classifier (using softmax and cross entropy), a regressor (using a linear layer and MSE) or any other output+cost-function pair you like.

* Armed with all of this information, let's understand together the first CNN ever: the [LeNet](https://www.datasciencecentral.com/lenet-5-a-classic-cnn-architecture/)

## CNN regulatization with dropout and batchnorm

## The Adam optimization algorithm


# Homework 8a: continue working with your assigned paper from last class

* Due Mar 23. In your reddit post, answer:
    * What research question are they trying to answer?
    * What dataset did they use and why is this a good/bad selection?
    * How did they split the data into training, validation, and test sets?
* Due Mar 24. In your reddit post, answer:
    * Which different experiments did they carry out to showcase what their model does?
    * How did they train their model?
        * What optimizer did they use?
        * What loss function did they use?
        * What metric did they use to measure model performance?
    * What baseline method/model are they comparing against?
* Due Mar 25. In your reddit post, answer
    * What results did they obtain with their model and how does this compare against the baseline?
    * What would you do to:
        * Develop an even better model
        * Use their model in an applied setting
    * What criticisms do you have about the paper?
* Due Mar 28. In your reddit post.
    * Link to a slideshow (use 10-15 slides) where you use all the grahics and text you need to present this paper to your classmates.
* Due Mar 30 during class: deliver a high-quality "journal-club" presentation of the paper
    
        
# Homework 8b (due March 29)

* Next class we will have a guest speaker
    * [Jessica Torres-Soto](https://jntorres.github.io) (Stanford PhD Alumna) will talk to us about her research.
    * She will focus her presentation on this paper: [Multi-task deep learning for cardiac rhythm detection in wearable devices](https://www.nature.com/articles/s41746-020-00320-4)
    * Read Jessica's paper in detail, but focus on the part that covers the model architecture and results. 
    * On our course subreddit, there is a thread to discuss Jessica's paper. 
    * You must post two questions you have after reading the paper. 
    * Do not repeat questions that have already been asked.
    * The sooner you post, the less likely it will be that somebody else already asked your question. 
    * You must also try to answer at least one of the questions asked by your peers.

# [Homework 8c: Convolutional neural network](https://colab.research.google.com/github/dl4genaudio/assignments/blob/main/cnn.ipynb)

Due April 5th at 11:59PM ([Eastern Standard Time](https://www.timeanddate.com/time/zones/et))

# Homework 8d (due April 5)

* On April 6, we will have a guest speaker
    * [Hugo Flores](https://hugofloresgarcia.github.io/) (Northwestern University PhD candidate) will talk to us about his research.
    * He will focus his presentation on these two papers: 
        * [Deep learning tools for audacity: helping researchers expand the artist’s toolkit](https://arxiv.org/pdf/2110.13323.pdf)
        * [Leveraging hierarchical structures for few-shot musical instrument recognition](https://arxiv.org/pdf/2107.07029.pdf)
    * Read one (or both) of Hugo's papers in detail, but focus on the part that covers the model architecture and results. 
    * On our course subreddit, there is a thread to discuss Hugo's papers. 
    * You must post two questions you have after reading one (or both) of the papers. 
    * Do not repeat questions that have already been asked.
    * The sooner you post, the less likely it will be that somebody else already asked your question. 
    * You must also try to answer at least one of the questions asked by your peers.

# Homework 8e (due April 6)

Submit a final project proposal where you address ALL of the following questions with as much detail as possible:

* What research question are you trying to answer?
* Who else has asked a similar research question? 
    * List at least 5 relevant papers you have read
    * Give a brief summary of each
* What dataset(s) will you use and why is this a good/bad selection?
    * How will you split your data for training?
        * include number of datapoints in each split 
        * which features present in the data will you use?
        * what labels present in the data will you use?
* What model architecture will you use and why?
    * What are the inputs?
    * What are the outputs?
* Which different experiments will you carry out to showcase what your model does?
* How will you train your model?
    * What optimizer will you use?
    * What loss function will you use?
    * What metric will you use to measure model performance?
* What baseline method/model will you compare your model against?
* What results do you expect to get?
    * Include mock figures showing how you will visualize the results that you expect.
    * Include at least one figure from another paper that you will reproduce using your model.

___

&copy; [Iran R. Roman](https://iranroman.github.io) 2022


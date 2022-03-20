| [Homepage](https://dl4genaudio.github.io) | [Course content](https://dl4genaudio.github.io/#course-content) | [Spanish](https://dl4genaudio-github-io.translate.goog/neural_network/?_x_tr_sl=auto&_x_tr_tl=es&_x_tr_hl=en&_x_tr_pto=wapp) |

# Feedforward neural networks

## Recapituation of supervised learning systems studied thus far

* We have studied how linear regression can help us predict continuous values via a linear relationship with a set of features.

* We have also studied how we can use logistic regression and softmax to classify datapoints into different discrete categories.

* The equations for these systems are:
    * Linear regression <img src="https://render.githubusercontent.com/render/math?math=\hat{y}_i = x_iW %2B b \in \mathbb{R}^{1x1}">
    * Logistic regression <img src="https://render.githubusercontent.com/render/math?math=\hat{y}_i = \sigma(x_iW %2B b) = \frac{1}{1 %2B e^{-(x_iW %2B b)}} \in \mathbb{R}^{1x1}">
    * Softmax <img src="https://render.githubusercontent.com/render/math?math=\hat{y}_i=softmax(x_iW %2B b) = \frac{e^{x_iW %2B b}}{\sum_je^{x_iW %2B b}} \in \mathbb{R}^{1xC}">
 
* If you notice, we have 
    * used <img src="https://render.githubusercontent.com/render/math?math=W"> and <img src="https://render.githubusercontent.com/render/math?math=b"> to transform the input data <img src="https://render.githubusercontent.com/render/math?math=x_i">.
    * the result of this transformation gets further processed by a function to get the output <img src="https://render.githubusercontent.com/render/math?math=\hat{y}_i">.

* However, we can apply more transformations to the input data before reaching the final output. 

## Neural network with one hidden layer

* Instead of computing <img src="https://render.githubusercontent.com/render/math?math=\hat{y}_i"> directly, we can use input data <img src="https://render.githubusercontent.com/render/math?math=x_i"> to compute a "hidden state" <img src="https://render.githubusercontent.com/render/math?math=h = f(x_iW %2B b) \mathbb{R}^{1xH}">. 

* The function <img src="https://render.githubusercontent.com/render/math?math=f()"> that gives the hidden state is non-linear and arbitrary (although some non-linearities are more commonly used).

* If we used this hidden state with the systems we have studied so far in this class, their equations would be:
    * Linear regression neural network <img src="https://render.githubusercontent.com/render/math?math=\hat{y}_i = h_iW %2B b \in \mathbb{R}^{1x1}">
    * Logistic regression neural network <img src="https://render.githubusercontent.com/render/math?math=\hat{y}_i = \sigma(h_iW %2B b) = \frac{1}{1 %2B e^{-(h_iW %2B b)}} \in \mathbb{R}^{1x1}">
    * Softmax neural network <img src="https://render.githubusercontent.com/render/math?math=\hat{y}_i=softmax(h_iW %2B b) = \frac{e^{h_iW %2B b}}{\sum_je^{h_iW %2B b}} \in \mathbb{R}^{1xC}">

* These equations represent three different neural networks, each of which could be used for different tasks and applications.

## The choice of non-linearity

* Today, the most commonly used non-linearity is ReLU (Rectified Linear Unit) or [some of its variants](https://en.wikipedia.org/wiki/Rectifier_(neural_networks)).

* Other useful non-linearities include sigmoid and the hyperbolic tangent (tanh).

* Advantages of ReLU over other non-linearities include:
    * the fact that it does not "saturate"
    * its computation does not involve an exponentiation and instead is a "thresholding" operator
    * it results in the network learning a sparse representation

## Feedforward neural networks

* In the previous sections we talked about a neural network with one hidden layer.

* However, we can have more hidden layers. In fact, you can have as many as necessary (how do you know how many are necessary?).

* The resulting compuational architecture is known as a feedforward neural network. 


# [Homework 7a: Feedforward neural network](https://colab.research.google.com/github/dl4genaudio/assignments/blob/main/nn.ipynb)

# Homework 7b (read below for details)

* Read one of the following papers:
    * [CREPE: a convolutional representation for pitch estimation](https://arxiv.org/abs/1802.06182)
    * [WaveNet: a generative model for raw audio](https://arxiv.org/abs/1609.03499)
    * [Phase-aware speech enhancement with deep complex U-net](https://openreview.net/pdf?id=SkeRTsAcYm)
    * [A single-step approach to musical tempo estimation using a convolutional neural network](https://www.tagtraum.com/download/2018_schreiber_tempo_cnn.pdf)
    * [Rapid decoding of hand gestures in electrocorticography using recurrent neural networks](https://www.frontiersin.org/articles/10.3389/fnins.2018.00555/full)
* Next class you will have 5 minutes to (in this order):
    * Show us the figure in the paper with the model architecture.
    * Tell us the name of the model.
    * Tell us what type of model it is.
    * In two or three sentences, tell us what the model does.
    * In two or three sentences, explain what the inputs and outputs of the model are.
    * Walk us through the model architecure (i.e. what does each block, arrow, color, etc. in the figure represent?).
* Create a subreddit post with the information that you will share in class.
* IMPORTANT: in your post/presentation you may only use the figure in the paper with the model architecture.

# Homework 7c (read below for details)

* Next class we will have a guest speaker
    * [Julia Wilkins](https://steinhardt.nyu.edu/people/julia-wilkins) (PhD student at NYU) will talk to us about her research.
    * She will presentat her paper: [VocalSet](https://pseeth.github.io/public/papers/wilkins_seetharaman_ismir18.pdf)
    * Read Julia's paper in detail, but focus on the part that covers the model architecture and results. 
    * On our course subreddit, there is a thread to discuss Julia's paper. 
    * You must post two questions you have after reading the paper. 
    * Do not repeat questions that have already been asked ny others in the thread.
      * The sooner you post, the less likely it will be that somebody else already asked your question. 
    * You must also answer at least one of the questions asked by your peers.

All three due Mar 22th at 11:59PM ([Eastern Standard Time](https://www.timeanddate.com/time/zones/et))

___

&copy; [Iran R. Roman](https://iranroman.github.io) 2022


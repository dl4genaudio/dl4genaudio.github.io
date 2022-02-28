| [Homepage](https://dl4genaudio.github.io) | [Course content](https://dl4genaudio.github.io/#course-content) | [Spanish](https://dl4genaudio-github-io.translate.goog/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=en-US) |

# Softmax classification

## Multilabel classification

* We have talked about two types of regression: linear and binary

* We also covered how to use gradient descent to optimize a linear regressor and a logistic (i.e. binary) classifier. 

* Linear and binary classification are extremelly powerful. However, sometimes we want to separate data into `C` distinct categories. This is known as multilabel (or multiclass) classification.

* As an example, imagine you want to classify the different vowels of human speech. 

## The [PCVC speech](https://www.kaggle.com/sabermalek/pcvcspeech) dataset

* The Persian Consonant Vowel Combination (PCVC) dataset contains audio for persian vowels, pronounced in combination with a preceding consonant. 

<img src="https://github.com/smalekz/PCVC/blob/master/Images/PhonemeList.JPG" alt="drawing" width="100"/>

* Imagine that we want to use this dataset to develop a classification algorithm that can hear and identify which persian vowel is being said. 

* You can read more about this dataset in the original publication.
  * [Malekzadeh, S., Gholizadeh, M.H. Ghayoumi zadeh H., and Razavi, S.N., 2018. Persian phonemes recognition using PPNet. arXiv preprint arXiv:1812.08600.](https://arxiv.org/abs/1812.08600)

## Softmax

* Softmax is a function that allows you take an input <img src="https://render.githubusercontent.com/render/math?math=x_i \in \mathbb{R}^{1xD}"> and use it to generate "probabilities" across each of the `C` classes. 

* The equation of softmax is <img src="https://render.githubusercontent.com/render/math?math=softmax(\theta_i) = \frac{e^{\theta_i}}{\sum_je^{\theta_i}} \in \mathbb{R}^{1xC}">

* If we want to use softmax to classify datapoints <img src="https://render.githubusercontent.com/render/math?math=x_i \in \mathbb{R}^{1xD}">, then <img src="https://render.githubusercontent.com/render/math?math= \theta_i = x_iW - max_j(x_iW) \in \mathbb{R}^{1xC}"> (where <img src="https://render.githubusercontent.com/render/math?math=max(x_iW)"> is subtracted for computational stability purposes) and <img src="https://render.githubusercontent.com/render/math?math=W \in \mathbb{R}^{DxC}"> is our matrix with the parameters we are using for classification.

## Cross-entropy loss

* Last class we saw that we can use the binary cross entropy loss to optimize a logistic regression classifier. 

* To optimize a softmax (i.e. multiclass) classifier, we will use the categorical cross entropy loss <img src="https://render.githubusercontent.com/render/math?math=J = -\frac{1}{N}\sum_{i=1}^{N}y_ilog(softmax(\theta_i))">.

* <img src="https://render.githubusercontent.com/render/math?math=y_i \in \mathbb{R}^{1xC}">, the ground truth, is a one-hot vector, where only an entry is the number <img src="https://render.githubusercontent.com/render/math?math=1"> and all other entries are <img src="https://render.githubusercontent.com/render/math?math=0">. Each index in <img src="https://render.githubusercontent.com/render/math?math=y_i"> represents a different category. The index with the number <img src="https://render.githubusercontent.com/render/math?math=1"> indicates which class the corresponding datapoint (i.e. <img src="https://render.githubusercontent.com/render/math?math=x_i">) truly belongs to. 

## Regularization

* So far, the optimization routines we have implemented (linear and logistic regression) can give different solutions for the parameters.

* This is due to the objective function being only constrained by the comparison between a predicted value <img src="https://render.githubusercontent.com/render/math?math=\hat{y}_i"> and its ground truth <img src="https://render.githubusercontent.com/render/math?math=y_i">.

* We can add a term to the loss to regularize the parameters `W`, so that we impose a condition over the type of values that can be present in `W`. The most common type of regularization is the squared L2 norm <img src="https://render.githubusercontent.com/render/math?math=J = -\frac{1}{N}\sum_{i=1}^{N}ysoftmax(x_iW) + \lambda\sum_{d=1}^{D}\sum_{c=1}^{C}W^2"> 

# [Homework 6: softmax](https://colab.research.google.com/github/dl4genaudio/assignments/blob/main/softmax.ipynb)

Due Mar 16 at 11:59PM ([Eastern Standard Time](https://www.timeanddate.com/time/zones/et))

___

&copy; [Iran R. Roman](https://iranroman.github.io) 2022

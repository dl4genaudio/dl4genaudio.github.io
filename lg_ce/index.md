| [Homepage](https://dl4genaudio.github.io) | [Course content](https://dl4genaudio.github.io/#course-content) | [Spanish](https://dl4genaudio-github-io.translate.goog/lg_ce/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=en&_x_tr_pto=wapp) |

# Logistic regression, binary cross-entropy, and error metrics

## Logistic regression

* Last class we talked about how we can use linear regression to model linear relationships between features <img src="https://render.githubusercontent.com/render/math?math=X \in \mathbb{R}^{N\times D}"> and a target <img src="https://render.githubusercontent.com/render/math?math=Y \in \mathbb{R}^{N}">.

* But not all relationships between features and targets are linear. Sometimes the relationship is categorical (i.e. different instruments, or different musical genres).

* Now picture this scenario:
    * You have <img src="https://render.githubusercontent.com/render/math?math=N"> datapoints, each with <img src="https://render.githubusercontent.com/render/math?math=D"> features, and you have organized them in a matrix <img src="https://render.githubusercontent.com/render/math?math=X \in \mathbb{R}^{N\times D}">.
    * Half of these datapoints have features extracted from Violin tones, while the other half were extracted from Bass Tuba tones. 
    * You also have a vector <img src="https://render.githubusercontent.com/render/math?math=Y \in \mathbb{R}^{N}">, which is filled with zeros or ones, with each "zero" indicating that the features in the corresponding row of <img src="https://render.githubusercontent.com/render/math?math=X \in \mathbb{R}^{N\times D}"> were extracted from a Violin tone, and each "one" indicating Bass Tuba.

* You can use the logistic regression formula to find a vector <img src="https://render.githubusercontent.com/render/math?math=w \in \mathbb{R}^{D}"> and a bias term <img src="https://render.githubusercontent.com/render/math?math=b \in \mathbb{R}^{1}"> that allow you to transform the features into values between <img src="https://render.githubusercontent.com/render/math?math=0"> and <img src="https://render.githubusercontent.com/render/math?math=1">. 

* The logistic regression formula is <img src="https://render.githubusercontent.com/render/math?math=\hat{y} = \sigma(\theta) = \frac{1}{1 %2B e^{-\theta}} \in \mathbb{R}^{N}">, where <img src="https://render.githubusercontent.com/render/math?math=\theta = Xw %2B b">.

* Once we have transformed our features <img src="https://render.githubusercontent.com/render/math?math=X"> into <img src="https://render.githubusercontent.com/render/math?math=\hat{y}">, we can define a threshold (usually `0.5`) under (above) which all values in <img src="https://render.githubusercontent.com/render/math?math=\hat{y}"> will be treated as zeros (ones). 

* With this procedure, we can assess the performance of our logistic regression model against the ground truth data <img src="https://render.githubusercontent.com/render/math?math=y">.

* Question: how many parameters does logistic regression involve? How about linear regression? Why?

## Binary cross-entropy

* Last class, when we optimized linear regression, we used the function <img src="https://render.githubusercontent.com/render/math?math=J = \frac{1}{2}\frac{1}{N} \sum_{i=1}^N (y_i - \hat{y_i})^2">.

* For logistic regression we must use the binary cross-entropy loss, which is defined by <img src="https://render.githubusercontent.com/render/math?math=J = -\frac{1}{N} \sum_{i=1}^{N} y_i log(\hat{y}_i) %2B (1-y_i)log(1-\hat{y}_i)"> (the origins of this function come from statistics. If you are curious, you should take or review the materials for an introductory machine learning class, like Stanford's [CS229](https://cs229.stanford.edu/notes2021fall/cs229-notes1.pdf)).

* Inspecting the binary cross-entropy loss, you can see that when <img src="https://render.githubusercontent.com/render/math?math=y_i=0">, <img src="https://render.githubusercontent.com/render/math?math=J = -\frac{1}{N} \sum_{i=1}^{N} (1-y_i)log(1-\hat{y}_i)">. In contrast, when <img src="https://render.githubusercontent.com/render/math?math=y_i=1">, <img src="https://render.githubusercontent.com/render/math?math=J = -\frac{1}{N} \sum_{i=1}^{N} y_ilog(\hat{y}_i)">.

* When minimizing the binary cross-entropy loss using an algorithm like gradient descent, what we are effectively doing is making <img src="https://render.githubusercontent.com/render/math?math=y"> and <img src="https://render.githubusercontent.com/render/math?math=\hat{y}"> as simiar to each other as possible.

* Question: why does the binary cross-entropy loss have a negative sign at the beginning?

## Error metrics for binary classification

* When we are done optimizing our logistic regression model, we must evaluate it using our validation data splits (also, remember the evaluation data)?

* It's very common practice to calculate a [confusion matrix](https://en.wikipedia.org/wiki/Confusion_matrix), which tells us the number of:
    * true positives
    * false negatives
    * false positives
    * true negatives

* Having the confusion matrix, it is also easy to calculate the:
    * overall model accuracy
    * true positive rate
    * true negative rate
    * false positive rate (type-i error)
    * false negative rate (type-ii error)

* Error metrics are essential to interpret how our model performs on the different data splits of cross-validation.

# [Homework 5: Optimizing and evaluating logistic regression](https://colab.research.google.com/github/dl4genaudio/assignments/blob/main/logistic_regression.ipynb)

Due Mar 8th at 11:59PM ([Eastern Standard Time](https://www.timeanddate.com/time/zones/et))
___

&copy; [Iran R. Roman](https://iranroman.github.io) 2022

| [Homepage](https://dl4genaudio.github.io) | [Course content](https://dl4genaudio.github.io/#course-content) | [Spanish](https://dl4genaudio-github-io.translate.goog/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=en-US) |

# Cross validation and linear regression

## Cross validation

* No matter how big a dataset is, at the end of the day it has a limited number of datapoints. 

* Data is very valuable, and to develop robust machine learning methods, we must use it carefully. WARNING: the improper use of data is guaranteed to be a waste of your time.

* Cross-validation is a simple and robust method to carefully use data to systematically analize how well a model can perform.

* To carry out cross-validation, we must randomly split our data into two sets:
    * A development with \~95\% of the data
    * And a testing set, with \~5\% of the data 
        * We will save the testing set to assess our model (or models) at the very final testing phase of the development cycle.

* Cross-validation further splits randomly the development data into a `C` number of folds (usually five) of equal size. 

* Then, we will train our model (from scratch) using `C-1` of the development folds, and we will validate (i.e. assess model performance) using the remaining fold. 

* We will repeat this procedure until we have used each of the `C` folds as the validation fold, and we will calculate the average cross-validation accuracy across folds. 

* Note: some datasets have already been split into testing and development sets, and the development set can also be already split into fixed training and validation sub-sets. In this situation it is recommended to follow the suggested training and validation data splitting intead of creating training and validation folds. 
 
* Stop and think: why is all of this necessary?

## Linear regression

* Given a datapoint <img src="https://render.githubusercontent.com/render/math?math=x_i \in \mathbb{R}^{D}"> (i.e. with D features) and a dependent observation <img src="https://render.githubusercontent.com/render/math?math=y_i \in \mathbb{R}^{1}">, can we use the equation of a line to describe the relationship between <img src="https://render.githubusercontent.com/render/math?math=x"> and <img src="https://render.githubusercontent.com/render/math?math=y">? 

* Picture this scenario: 
    * you have a dataset consisting of musical tones, each with a fundamental frequencies (f0). 
    * You calculate the average zero-crossing rate per second for each of these tones. 
    * If the zero-crossing rate is <img src="https://render.githubusercontent.com/render/math?math=x_i"> and f0 is <img src="https://render.githubusercontent.com/render/math?math=y_i">, you could use a line and an error term to model the data using the equation <img src="https://render.githubusercontent.com/render/math?math=y_i=wx_i+b+\epsilon_i">.

* To assess this model, we must assume there will be an error <img src="https://render.githubusercontent.com/render/math?math=\epsilon"> that we will have to "tolerate", and find the variables <img src="https://render.githubusercontent.com/render/math?math=w"> and <img src="https://render.githubusercontent.com/render/math?math=b"> using the objective function <img src="https://render.githubusercontent.com/render/math?math=J = \frac{1}{2}\frac{1}{N} \sum_1^N (y_i - \hat{y_i})^2">, where <img src="https://render.githubusercontent.com/render/math?math=N"> is the number of datapoints we are using to calculate the objective, and <img src="https://render.githubusercontent.com/render/math?math=\hat{y_i}=wx_i+b">.

* The objective function is effectively half the [mean squared error](https://en.wikipedia.org/wiki/Mean_squared_error) <img src="https://render.githubusercontent.com/render/math?math=2J = \sum_1^N \epsilon_i^2"> between our model prediction <img src="https://render.githubusercontent.com/render/math?math=\hat{y_i}"> and the ground-truth value <img src="https://render.githubusercontent.com/render/math?math=y_i">.

* We can use a simple method like gradient descent [(review if necessary)](https://towardsdatascience.com/linear-regression-using-gradient-descent-97a6c8700931) to find the optimal <img src="https://render.githubusercontent.com/render/math?math=w"> and <img src="https://render.githubusercontent.com/render/math?math=b"> so that <img src="https://render.githubusercontent.com/render/math?math=J"> is as low as possible.

# [Homework 4: Cross-validation and linear regression](https://colab.research.google.com/github/dl4genaudio/assignments/blob/main/cv_and_lr.ipynb)

due Mar 1st at 11:59PM ([Eastern Standard Time](https://www.timeanddate.com/time/zones/et))

___

&copy; [Iran R. Roman](https://iranroman.github.io) 2022

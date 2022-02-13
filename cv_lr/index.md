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

* Given a datapoint <img src="https://render.githubusercontent.com/render/math?math=x_i in \mathbb{R}^{D}"> (i.e. with D features) and a dependent observation <img src="https://render.githubusercontent.com/render/math?math=y_i in \mathbb{R}^{1}">, can we use the equation of a line to describe the relationship between <img src="https://render.githubusercontent.com/render/math?math=x"> and <img src="https://render.githubusercontent.com/render/math?math=y">? 

* Picture this scenario: 
    * you have a dataset consisting of musical tones, each with a fundamental frequencies (f0). 
    * You calculate the average zero-crossing rate per second for each of these tones. 
    * If the zero-crossing rate is x and the fundamental frequency is y, you could use a line to describe y = wx + b + e

* To assess this model, we must assume there will be an error e that we will have to "tolerate", and find the variables w and b.

* To find w and b, we can define the objective function `J = (y - y_hat)^2`, which we can optimize using a simple method like gradient descent [(review if necessary)](https://towardsdatascience.com/linear-regression-using-gradient-descent-97a6c8700931).  


___

&copy; [Iran R. Roman](https://iranroman.github.io) 2022

| [Homepage](https://dl4genaudio.github.io) | [Course content](https://dl4genaudio.github.io/#course-content) | [Spanish](https://dl4genaudio-github-io.translate.goog/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=en-US) |

# Logistic regression and binary cross-entropy

## Logistic regression

* Last class we talked about how we can use linear regression to model linear relationships between features <img src="https://render.githubusercontent.com/render/math?math=X \in \mathbb{R}^{N\times D}"> and target <img src="https://render.githubusercontent.com/render/math?math=Y \in \mathbb{R}^{N}">.

* But not all relationships between features and targets are linear. Sometimes the relationship is categorical (i.e. different instruments and different musical genres).

* Now picture this scenario:
    * You have <img src="https://render.githubusercontent.com/render/math?math=N"> datapoints, each with <img src="https://render.githubusercontent.com/render/math?math=D"> features, and you have organized them in a matrix <img src="https://render.githubusercontent.com/render/math?math=X \in \mathbb{R}^{N\times D}">.
    * Half of these datapoints have features extracted from instrument tones that were played with musical <img src="https://render.githubusercontent.com/render/math?math=pp"> dynamics, while the other half were extracted from instrument tones that were played with musical <img src="https://render.githubusercontent.com/render/math?math=ff"> dynamics. 
    * You also have a vector <img src="https://render.githubusercontent.com/render/math?math=Y \in \mathbb{R}^{N}"> with filled with zeros or ones, with each zero indicating that the features in the corresponding row of <img src="https://render.githubusercontent.com/render/math?math=X \in \mathbb{R}^{N\times D}"> were extracted from a tone played with <img src="https://render.githubusercontent.com/render/math?math=pp"> dynamics, and ones indicating <img src="https://render.githubusercontent.com/render/math?math=ff"> dynamics.

* You can use the logistic regression formula to find a vector <img src="https://render.githubusercontent.com/render/math?math=w \in \mathbb{R}^{D}"> that allows you to transform the features into values between zero and one <img src="https://render.githubusercontent.com/render/math?math=\hat{y} = \sigma(\theta) = \frac{1}{1+e^{-\theta}} \mathbb{R}^{N}"> where <img src="https://render.githubusercontent.com/render/math?math=\theta = Xw">.

* Once we have transformed our features <img src="https://render.githubusercontent.com/render/math?math=X"> into <img src="https://render.githubusercontent.com/render/math?math=\theta = \hat{y}">, we can define a threshold (usually `0.5`) under (above) which all values in <img src="https://render.githubusercontent.com/render/math?math=\hat{y}"> will be treated as zeros (ones). 

* With this procedure, we can assess the performance of our logistic regression model against the ground truth data <img src="https://render.githubusercontent.com/render/math?math=y">.


## Binary cross-entropy

___

&copy; [Iran R. Roman](https://iranroman.github.io) 2022

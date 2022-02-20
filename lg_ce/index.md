| [Homepage](https://dl4genaudio.github.io) | [Course content](https://dl4genaudio.github.io/#course-content) | [Spanish](https://dl4genaudio-github-io.translate.goog/?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=en-US) |

# Logistic regression and binary cross entropy

## Logistic regression

* Last class we talked about how we can use linear regression to model linear relationships between features <img src="https://render.githubusercontent.com/render/math?math=X \in \\mathbb{R}^{N\times D}"> and target <img src="https://render.githubusercontent.com/render/math?math=Y \in \\mathbb{R}^{N}">.

* But not all relationships between features and targets are linear. Sometimes the relationship is categorical (i.e. different instruments and different musical genres).

* Now picture this scenario:
    * You have <img src="https://render.githubusercontent.com/render/math?math=N"> datapoints, each with <img src="https://render.githubusercontent.com/render/math?math=D"> features, and you have organized them in a matrix <img src="https://render.githubusercontent.com/render/math?math=X \in \\mathbb{R}^{N\times D}">.
    * Half of these datapoints have features extracted from instrument tones that were played with musical <img src="https://render.githubusercontent.com/render/math?math=pp"> dynamics, while the other half were extracted from instrument tones that were played with musical <img src="https://render.githubusercontent.com/render/math?math=ff"> dynamics. 

___

&copy; [Iran R. Roman](https://iranroman.github.io) 2022

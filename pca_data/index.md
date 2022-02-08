| [Homepage](https://dl4genaudio.github.io) | [Course content](https://dl4genaudio.github.io/#course-content) | [Spanish](https://dl4genaudio-github-io.translate.goog/pca_data/?_x_tr_sl=auto&_x_tr_tl=es&_x_tr_hl=en-US&_x_tr_pto=wapp) |

## Audio datasets

* MIR and Deep Learning are "data-driven".

* This means that we "do as the data says", and as a result we need large amounts of "datapoints" (in the order of thousands) to find "the real meaning that the data is trying to convey".

* The definition of a datapoint depends on the goal or research question:
    * it could be as short as a milliseconds-long recording of a vowel (if the goal is, for example, to identify or generate vowels), or 
    * as long as the entire duration of a piece of music (if the goal is, for example, generation of entire songs that closely follow the style of an artist).

* Fortunately, large amounts of data have already been curated by researchers and are easily accesible. 

* [mirdata](https://mirdata.readthedocs.io), [soundata](https://soundata.readthedocs.io), and [micarraylib](https://github.com/micarraylib/micarraylib) are examples of open-source projects that make large amounts of data readily available for data-driven research with audio.

## Dimensionality reduction with principal components analysis (PCA)

* We have discussed how feature extraction can serve as a technique to achieve dimensionality reduction. 

* The audio features we have studied so far are "hand-picked", which can result in a flawed research methodology (why?)

* The [principal components analysis](https://en.wikipedia.org/wiki/Principal_component_analysis) is a method to avoid "hand-picking". It can reduce the dimensionality of high-dimensional datapoints in a dataset by projecting the data onto a few vectors (i.e. dot product) that are orthogonal to each other, and each vector minimizes the mean squared error from the points.

* The steps needed to carry out PCA (assuming all datapoints are stacked as rows in a matrix `X`) can be summarized as:
    1. Standardized the dataset by zero-centering the features and making their variance equal to 1. 
        * In the specific case of audio, sometimes we "standardize" the data differently. How and why?
    2. Calculate the covariance matrix of the standardized data.
    3. Find the eigenvalues and eigenvectors of the resulting covariance matrix and sort them by size of the corresponding eigenvalue.
    4. Define a matrix whose columns are the N eigenvectors that correspond to the principal components that we want to calculate (usually the first 2, 3, 4, etc.).
    5. Project the standardized dataset onto the matrix (via matrix dot product).

# [Homework 3a: mirdata and PCA](https://colab.research.google.com/github/dl4genaudio/assignments/blob/main/pca.ipynb)

# Homework 3b

Next class, during the discussion session (if you come to class), you will tell us about three research papers you have read that relate to your research interests and the course material. 

You will have exactly 5 minutes to talk (if you come to class). You may use visual aids for your presentation (i.e. slides).

You must also write a 500 word post describing the three research papers you identified on the [course subreddit](https://www.reddit.com/r/deeplearningaudio/).

Both due Feb 22nd at 11:59PM ([Eastern Standard Time](https://www.timeanddate.com/time/zones/et))

Find and read research papers that align with your interests in the proceedings of conferneces such as [ISMIR 2021](https://ismir2021.ismir.net/papers/), [CogMIR 2019](http://www.cogmir.org/wp-content/uploads/2019/08/CogMIR-2019-Program-Schedule.pdf), [ICASSP 2021](https://www.2021.ieeeicassp.org/2021.ieeeicassp.org/Papers/AcceptedPapers.html), [DAFX 2021](https://dafx2020.mdw.ac.at/proceedings/Proceedings_of_DAFx20in21.html), or do a search on google scholar for keywords that better match your interests within the scope of this course.

___

&copy; [Iran R. Roman](https://iranroman.github.io) 2022

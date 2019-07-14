# Section 2: -------- Part 1: Data Preprocessing --------
[after downloading]
>> learnt how to import libs in python 
>> (numpy for mathematics, matplotlib for plotting graphs, pandas for importing datasets)
>> importing libs is not req in R

>> importing datasets in python(using pandas) and R
>> **important** index's in R start from 1, unlike other prog languages

>> for python, importing lib module called `sklearn.preprocessing` which has `Imputer` class
>> it can fill in all missing values with mean, median or mode
>> for R, missing values were filled by replacing `na` by average (ave function)
>> `ifelse()` function in R works like ternary operator in other prog languages

>> use `Ctrl+I` in Spyder, `F1` in RStudio to open help docs for any function

>> cols having non-numric values are categorical data
>> they're converted into special cols containing numbers 
>> eventually ML model will run for numberic values
>> for python, using `LabelEncoder` and `OneHotEncoder` of `sklearn.preprocessing` module
>> for R, `factor` function is used
>> text value is replaced with numbers, then additional binary cols are added

>> dataset is divided into 2 parts: `training set` and `test set` in the ratio 80-20 usually
>> `test set` is used to test accuracy of ML model, it needs to be stopped at max accuracy
>> else model will over-train i.e. will work only for test data
>> for python: import `train-test-split` from `sklearn.cross_validation`
>> took test size: 0.2, random seed = 0
>> for R: installed package: `caTools`
>> **important** in R, we define training set ratio, not test-set ratio

>> most ML models are based on euclidean distance
>> since salary has huge values w.r.t. age, it'll dominate the output (we don't want that)
>> all values are then re-scaled such that, their values are from `-1` to `+1`
>> [how it works] mean of values of a col is re-assigned as zero, all others are re-scaled accordingly
>> for python import `StandardScaler` from `sklearn.preprocessing`
>> **important** `training set` is fit_transformed first, `test set` is transformed according to `training set`
>> for R, `scale()` function is used directly
>> **important** scale() won't operate on factors, hence only numeric values are selected

>> 4 important parts are: importing libraries, dataset, splitting training set and test set (and  feature scaling)
>> all others are not much important, hence removed from data preprocessing template


# Section 3: -------- Part 2: Regression --------
>> regression is finding correlation in 2 variables
>> then it can be used to predict values
>> There are 6 regression models in this course:
>> simple linear, multiple linear, polynomial, classifications etc


# Section 4: Simple Linear Regression
>> simple linear regression is where a table with 2 cols is given and one needs to find relation as `y = mx + c`
>> then you plot all the given points on graph and find a best line
>> draw random lines, tak the sum of sq of verticle distances of all the points from that line
>> this sum should be the least, then the line is best

>> **important** X is the `matrix` of features (independent vaiables) y is `vector` of dependent variables
>> X has 2 dimensions *although, iss case me ek hi col thaa*, hence its a matrix
>> y would always have a single dimension, hence its a vector
>> [global ML knowledge] after regression is done, the algo runs for all values in test set, then accurace comes out in form of percentage

>> simple linear regression is done in python using in-built module named `LinearRegression` from `sklearn.linear_model`
>> a prediction is made for test set, stored in a variable
>> `matplotlib` is used for plotting graphs
>> `scatter`, `plot()`, `show()` are imp functions

>> did the same for R, took 2/3 instead of 1/3 (reason in line 35)


# Secion 5: Multiple Linear Regression
>> multiple linear regression is of several types
>> backward elimination is fastest
>> for preprocessing, all algos are picked from various files
>> encoding must be done before splitting the dataset
>> `OneHotEncoder` works after labelencoder (requires numeric values)
>> `p` is a statistical measure, defined for a dependent variable
>> higher value of  `p` means more daviation & less importance
>> generally, we consider a dependent var important, if its `p` is less than 5%


# Section 6: Polynomial Regression
>> in some cases, data is not so linear relation, it might be quadratic, cubic, exponential etc.
>> then we use `Polynomial Linear regression`, still called 'linear'
>> 'coz, relation is of the form `y = b0 + (b1 * x1) + (b2 * x1^2) + (b3 * x1^3) ... (bn * x1^n)` [b has numbers in subscript, x has powers]
>> the coeff are linear, can be represented in simple equation, no denoominator, no log fcn etc.

>> here, X was taken as `dataset[:, 1:2]` not `dataset[:, 1]` because X should be a matrix always (line 58)
>> dataset was not splitted, coz rows in dataset are less
>> `LinearRegressor()` is used to make regressor for polynomial regressor too
>> value of degree is changed for `poly_reg` to see what suits best for the model

>> in R, dataset[2:3] includes 2 and 3 both
>> `lm()` function has 2 params: formula(what is proportional to what) and data(what data to operate on)
>> `ggplot2` in R is similar to `matplotlib` in python
>> `geom_point()` and `geom_line()` functions of ggplot have 2 arg: `aes`, the aesthetic mapping and `color`


# Section 7: Support Vector Regression (SVR)
>> SVR is extension of SLR (simple linear regression), quite literally
>> in SLR, we draw a line that bset passes through all scattered points
>> SVR accepts all points that are within certain `threshold` (called epsilon)
>> `kernal` is used in SVR, it can be linear, polynomial or gaussian

>> in python, `SVR` class is used from `sklearn.svm`
>> kernel used is gaussian a.k.a rbf
>> feature scaling is required, else the regressor gives horizontal line

>> in R, `e1071` library is used to make regressor of SVM
>> `gaussian` kernel is used by default
>> `ggplot2` is used to plot


# Section 8: Decision Tree Regression
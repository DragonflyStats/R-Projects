Ghana R Users (January 2022)
========================================================
author: Kevin O'Brien
date: 14-January-2022
width: 960
height: 800
transition: linear
css: rpres.css

About Me
========================================================

### Kevin O'Brien

- Why R? - Community Team lead & Webinars co-ordinator
- West of Ireland / South London
- Python Ireland - Director
- JuliaCon 2022 - Social Media Chair
- was previously (what is now known) as a "Research Software Engineer" in a University.

Target
=========================================

### Intended Audience

* Career Young Statisticians and Data Scientists.
* Solid Foundation in R and/or Python.
* Machine Learning / Deep Learning
* Github

### What's next?

* Transition to Research Software Engineer?
* Apply skills base to real world problems

Research Software Engineering
=========================================
Research software engineering is the use of software engineering practices in research applications. The term was proposed in a research paper in 2010 in response to an empirical survey on tools used for software development in research projects. 

It started to be used in United Kingdom in 2012, when it was needed to define the type of software development needed in research. This focuses on reproducibility, reusability, and accuracy of data analysis and applications created for research.
(*Wikipedia*)

Sustainable Development Goals 
=========================================

![Sustainable Development Goals](sustainable_development_goals.png)


Sustainable Development Goals 
=========================================

**Sustainable Development Goal 2**
 -  ending hunger, achieving food security, improving nutrition and promoting sustainable agriculture.

**Sustainable Development Goal 3**
 -  ensuring healthy lives and promoting well-being for all, at all ages.

**Sustainable Development Goal 6**
 -  ensuring the availability and sustainable management of water and sanitation for all.

**Sustainable Development Goal 7**
 -  ensuring access to affordable, reliable, sustainable and modern energy for all.


Sustainable Development Goals (more)
=========================================

**Sustainable Development Goal 8**
 -  promoting sustained, inclusive and sustainable economic growth, full and productive employment and decent work for all.


**Sustainable Development Goal 11**
 -  making cities and human settlements inclusive, safe, resilient and sustainable.


**Sustainable Development Goal 12**
 -  ensuring sustainable consumption and production patterns.

**Sustainable Development Goal 13**
 -  taking urgent action to combat climate change and its impacts.



Sustainable Development Goals (more)
=========================================

**Sustainable Development Goal 14**
 -  conserving and using oceans, seas and marine resources sustainably.

**Sustainable Development Goal 15**
 -  protecting, restoring and promoting sustainable use of terrestrial ecosystems; sustainably managing forests; combating desertification, halting and reversing land degradation; and halting biodiversity loss.

**Sustainable Development Goal 16**
 -  promoting peaceful and inclusive societies for ***Sustainable Development, providing access to justice for all and building effective, accountable and inclusive institutions at all levels.



Domain Knowledge 
================================


https://www.linkedin.com/feed/update/urn:li:activity:6765853465861267456/



 * Agriculture and Food
 * Health & Life Sciences
 * Natural Sciences & GIS
 

Mw oen career: Audiology, Equine Science, Water Quality, Milk Production, Sport Science, Forestry
 
 




Machine Learning - types of analysis
========================================================
Many Types of ML Problems
* Clustering 
* Classification
* Regression


#### Focus on Regression

* Predicting a numberic value based on predictors



Life Sciences
=============================================


* Models must scrutinized thoroughly - particularly the effect of "Influential cases" and "outliers".

* Random Forest Models are insufficent in this regards - can deduce important variables, but not important cases


Introduction to Model Validation Procedures with R
===========================================


* Model validation is a vital part of the statistical modelling process, but is often overlooked in statistical courses.
* This process allows the analyst to properly validate the assumptions underlying the model, once applied to the data.
* 
In this presentation, we will look at residual analysis and influence measures for linear models, with some associated topics.



Audience 
===========================================

* The talk is aimed at students and early career data professionals who have already encountered conventional regression analyses, and
are familiar with the model fitting process in R (i.e. the ``lm()`` function). 
* The talke will introduce a mixture of graphical procedures,
statistical measures and hypothesis tests, which the attendees are invited to learn more about beyond the talk.

* The talk will feature the {CAR} R package [1], but all of the other functionality is available in Base R or Tidyverse.


[1] Fox, John, et al. "*The car package.*" R Foundation for Statistical Computing (2007).

R Packages
================================

![Easyverse - (*EasyStats.github.io*)](EasyStats.PNG)





R Packages
================================


```r
library(tidyverse)

# Graphics & Data Inspection
library(inspectdf)
library(WVPlots)


# Statistics & Modelling
library(MASS)   # installed with Base R
library(car)
library(gvlma)
```



cheddar: Taste of Cheddar cheese
==============================================
In **{faraway}**: Functions and Datasets for Books by Julian Faraway

**Description**
In a study of cheddar cheese from the LaTrobe Valley of Victoria, Australia, samples of cheese were analyzed for their chemical composition and were subjected to taste tests. Overall taste scores were obtained by combining the scores from several tasters.


* **taste** - a subjective taste score

* **Acetic** - concentration of acetic acid (log scale)

* **H2S** - concentration of hydrogen sulfice (log scale)

* **Lactic** - concentration of lactic acid


Linear Models
=======================

#### Linear Models
 - `lm()` -
 - `aov()` - analysis of variance
 - ancova models

#### Random Forest



Key Motivations 
=============================

* All statistical models and tests have underlying mathematical assumptions on the types of conditions upon we can generate reliable results (**Hoekstra et al., 2012**). 

* What this means is that before we go off and generate predictions, p-values and correlation coefficients, we need to understand whether our data fits certain assumption criteria in order to avoid Type I or II errors given the technique at hand.




Feature Engineering
========================================================

Not Covering This - but it is important

* Feature Engineering
* Normalisation
* Scaling
* One-hot Encoding

* {caret} package



Exploratory Data Analysis
================================

BE THOROUGH

* Domain Knowledge
* Summary Statistics
* Data Visualization
* Outlier Detection
* Missing Data Analysis


#### Remark: 

Cluster Analysis (e.g. K-means) can be a very useful EDA procedure.



Exploratory Data Analysis
========================================================

#### Data Inspection

* {inspectdf}
* {janitor}

#### Data Visualization

* {WVPlots}
* {ggally}

#### tidyverse

* {broom} and {modelr} (succeeded by {tidymodels})
* `dplyr::tally()`
* `dplyr::distinct()`

Useful Packages (a selection)
========================================================

* {A3}
* {arsenal}
* {analytics}
* {gdata}
* {descriptr}
* {furniture}
* {rockchalk}
* {yardstick}



InspectDF
==============================
#### InspectDF

inspectdf: Inspection, Comparison and Visualisation of Data Frames

inspectdf is collection of utilities for columnwise summary, comparison and visualisation of data frames. Functions are provided to summarise missingness, categorical levels, numeric distribution, correlation, column types and memory usage. 
The package has three aims: to speed up repetitive checking and exploratory tasks for data frames

InspectDF
================================
Key functions
* ``inspect_types()``: summary of column types
* ``inspect_mem()``: summary of memory usage of columns
* ``inspect_na()``: columnwise prevalence of missing values
* ``inspect_cor()``: correlation coefficients of numeric columns
* ``inspect_imb()``: feature imbalance of categorical columns
* ``inspect_num()``: summaries of numeric columns
* ``inspect_cat()``: summaries of categorical columns

InspectDF
================================
class:smaller-75


```r
# Load dplyr for starwars data & pipe
library(dplyr)
# Single dataframe summary
inspect_cat(starwars)
```

```
# A tibble: 8 x 5
  col_name     cnt common    common_pcnt levels           
  <chr>      <int> <chr>           <dbl> <named list>     
1 eye_color     15 brown           24.1  <tibble [15 x 3]>
2 gender         3 masculine       75.9  <tibble [3 x 3]> 
3 hair_color    13 none            42.5  <tibble [13 x 3]>
4 homeworld     49 Naboo           12.6  <tibble [49 x 3]>
5 name          87 Ackbar           1.15 <tibble [87 x 3]>
6 sex            5 male            69.0  <tibble [5 x 3]> 
7 skin_color    31 fair            19.5  <tibble [31 x 3]>
8 species       38 Human           40.2  <tibble [38 x 3]>
```

InspectDF
================================
class:smaller-75


```r
# Paired dataframe comparison
inspect_cat(starwars, starwars[1:20, ])
```

```
# A tibble: 8 x 5
  col_name      jsd fisher_p lvls_1            lvls_2           
  <chr>       <dbl>    <dbl> <named list>      <named list>     
1 eye_color  0.0936 0.750    <tibble [15 x 3]> <tibble [8 x 3]> 
2 gender     0.0387 0.353    <tibble [3 x 3]>  <tibble [2 x 3]> 
3 hair_color 0.261  0.000843 <tibble [13 x 3]> <tibble [10 x 3]>
4 homeworld  0.394  0.359    <tibble [49 x 3]> <tibble [11 x 3]>
5 name       0.573  1.00     <tibble [87 x 3]> <tibble [20 x 3]>
6 sex        0.0526 0.287    <tibble [5 x 3]>  <tibble [4 x 3]> 
7 skin_color 0.288  0.990    <tibble [31 x 3]> <tibble [10 x 3]>
8 species    0.300  0.807    <tibble [38 x 3]> <tibble [6 x 3]> 
```

InspectDF
================================
class:smaller-65


```r
# Grouped dataframe summary
starwars %>% group_by(species) %>% inspect_cat()
```

```
# A tibble: 266 x 6
# Groups:   species [38]
   species  col_name     cnt common        common_pcnt levels          
   <chr>    <chr>      <int> <chr>               <dbl> <named list>    
 1 Aleena   eye_color      1 unknown               100 <tibble [1 x 3]>
 2 Aleena   gender         1 masculine             100 <tibble [1 x 3]>
 3 Aleena   hair_color     1 none                  100 <tibble [1 x 3]>
 4 Aleena   homeworld      1 Aleen Minor           100 <tibble [1 x 3]>
 5 Aleena   name           1 Ratts Tyerell         100 <tibble [1 x 3]>
 6 Aleena   sex            1 male                  100 <tibble [1 x 3]>
 7 Aleena   skin_color     1 grey, blue            100 <tibble [1 x 3]>
 8 Besalisk eye_color      1 yellow                100 <tibble [1 x 3]>
 9 Besalisk gender         1 masculine             100 <tibble [1 x 3]>
10 Besalisk hair_color     1 none                  100 <tibble [1 x 3]>
# ... with 256 more rows
```





WVPlots: Common Plots for Analysis
==============================
Select data analysis plots, under a standardized calling interface implemented on top of 'ggplot2' and 'plotly'. Plots of interest include: 'ROC', gain curve, scatter plot with marginal distributions, conditioned scatter plot with marginal densities, box and stem with matching theoretical distribution, and density with matching theoretical distribution.




```r
set.seed(34903490)
x = rnorm(50)
y = 0.5*x^2 + 2*x + rnorm(length(x))
frm = data.frame(
  x = x,
  y = y,
  yC = y>=as.numeric(quantile(y,probs=0.8)),
  stringsAsFactors = FALSE)
frm$absY <- abs(frm$y)
frm$posY = frm$y > 0
```

Scatterplot
=============

Scatterplot with smoothing line through points.


```r
WVPlots::ScatterHist(frm, "x", "y", title="Example Fit")
```

<img src="Ghana_R_Users-figure/unnamed-chunk-20-1.png" title="plot of chunk unnamed-chunk-20" alt="plot of chunk unnamed-chunk-20" width="100%" />






Mahalanobis Distance
===============================



* Mahalanobis Distance 
* multivariate distance

How to Calculate Mahalanobis Distance in R
The Mahalanobis distance is the distance between a data point and the origin (mean) in a multivariate space. 
It's often used to identify outliers in multivariate statistical analyses.


Step 1: Create the dataset.
===================================
First, we'll create a dataset that displays the exam score of 20 students along with the number of hours they spent studying, the number of prep exams they took, and their current grade in the course:



```r
#create data
df = data.frame(score = c(91, 93, 72, 87, 86, 73, 68, 87, 78, 99, 95, 76, 84, 96, 76, 80, 83, 84, 73, 74),
        hours = c(16, 6, 3, 1, 2, 3, 2, 5, 2, 5, 2, 3, 4, 3, 3, 3, 4, 3, 4, 4),
        prep = c(3, 4, 0, 3, 4, 0, 1, 2, 1, 2, 3, 3, 3, 2, 2, 2, 3, 3, 2, 2),
        grade = c(70, 88, 80, 83, 88, 84, 78, 94, 90, 93, 89, 82, 95, 94, 81, 93, 93, 90, 89, 89))
```

Step 1: Create the dataset.
===================================


```r
#view first six rows of data
head(df) %>%
  kable(format="markdown")
```



| score| hours| prep| grade|
|-----:|-----:|----:|-----:|
|    91|    16|    3|    70|
|    93|     6|    4|    88|
|    72|     3|    0|    80|
|    87|     1|    3|    83|
|    86|     2|    4|    88|
|    73|     3|    0|    84|


Step 2: Calculate the Mahalanobis distance for each observation.
========================================
Next, we'll use the built-in ``mahalanobis()`` function in R to calculate the Mahalanobis distance for each observation, which uses the following syntax:

<pre><code>
mahalanobis(x, center, cov)
</code></pre>

where:

* x: matrix of data
* center: mean vector of the distribution
* cov: covariance matrix of the distribution

Implementation
===========================
class:smaller-90

The following code shows how to implement this function for our dataset:


```r
#calculate Mahalanobis distance for each observation
mahalanobis(df, colMeans(df), cov(df)) %>% 
  head() %>%
  t()
```

```
         [,1]     [,2]     [,3]     [,4]     [,5]     [,6]
[1,] 16.50196 2.639286 4.850797 5.201261 3.828734 4.090563
```

Step 3: Calculate the p-value for each Mahalanobis distance.
=================================
We can see that some of the Mahalanobis distances are much larger than others. To determine if any of the distances are statistically significant, we need to calculate their p-values.

The p-value for each distance is calculated as the p-value that corresponds to the Chi-Square statistic of the Mahalanobis distance with k-1 degrees of freedom, where k = number of variables. So, in this case we'll use a degrees of freedom of 4-1 = 3.

Step 3: Calculate the p-value for each Mahalanobis distance.
=================================
class:smaller-code

```r
#create new column in data frame to hold Mahalanobis distances
df$mahal <- mahalanobis(df, colMeans(df), cov(df))

#create new column in data frame to hold p-value for each Mahalanobis distance
df$p <- pchisq(df$mahal, df=3, lower.tail=FALSE)
```

Step 3: Calculate the p-value for each Mahalanobis distance.
=================================
class:smaller-code

```r
#view data frame
df %>%
  head() %>%
  kable(format="markdown")
```



| score| hours| prep| grade|     mahal|         p|
|-----:|-----:|----:|-----:|---------:|---------:|
|    91|    16|    3|    70| 16.501963| 0.0008946|
|    93|     6|    4|    88|  2.639286| 0.4506437|
|    72|     3|    0|    80|  4.850797| 0.1830542|
|    87|     1|    3|    83|  5.201261| 0.1576393|
|    86|     2|    4|    88|  3.828734| 0.2805615|
|    73|     3|    0|    84|  4.090563| 0.2518495|

Intrepretating the output
=====================================
* Typically a p-value that is less than some threshold (e.g. 0.001) is considered to be an outlier. 
* Here the first observation is an outlier in the dataset because it has a p-value less than 0.001.
* Depending on the context of the problem, you may *omit* this observation from the dataset since it's an outlier and could affect the results of the analysis. (Domain knowledge is vital).





Simple Linear Regression
==============================================

* In simple linear regression, we predict values on one variable from the values of a second variable. 


* The variable we are predicting is called the ***dependent variable*** (or response variable) and is referred to as Y. 

* The variable we are basing our predictions on is called the ***independent variable*** (or predictor variable) and is referred to as X.

* Remark: When there is only one predictor variable, the prediction method is called simple regression. Linear regression can have more than one predictor variable, i.e. Multiple Linear Regression.

Simple Linear Regression
==============================================

* Suppose we construct our model using $n$ observed values of the response variable: $\{y_1, y_2, \ldots y_i \ldots y_n$\}.

* For the original data set, there is a predicted value of each case of $Y$ that corresponds to an observed value of $Y$. 

* The difference between an observed value of the dependent variable ($y_i$) and the corresponding predicted value ($\hat{y}$) is called the residual ($e_i$). Each data point from the data set has one residual.

Residuals
==============================================

Simply put, the values of the residuals are derived as follows: 

\[\mbox{Residual = Observed value - Predicted value}\]

\[e_i = y_i - \hat{y_i} \]

* Important theoretical assumption underlying the OLS model: the sum of the residuals should equal to zero. 

\[\sum e_i = 0\]

* An extension of this is that the expected value of the residuals is 0: $\mathrm{E}(e) = 0$.
* Another Important Theoretical Assumption - The residuals are normally distributed. (more on that later)


Residual Plots
===================================
* A residual plot is a graph that shows the residuals on the vertical axis and the independent variable on the horizontal axis. 
* If the points in a residual plot are randomly dispersed around the horizontal axis, a linear regression model is appropriate for the data; otherwise, a non-linear model is more appropriate.

Summary of Important Terms
==============================
Some important terms in model diagnostics, essentially a plan for this talk.

*  ***Residual:*** The difference between the predicted value (based on the regression equation) and the actual, observed value.
*  ***Outlier:***  In linear regression, an outlier is an observation with large residual.  In other words, it is an observation whose dependent-variable value is unusual given its value on the predictor variables.  An outlier may indicate a sample peculiarity or may indicate a data entry error or other problem. 

Summary of Important Terms
==============================
*  ***Leverage:***  An observation with an extreme value on a predictor variable is a point with high leverage.  Leverage is a measure of how far an independent variable deviates from its mean.  High leverage points can have a great amount of effect on the estimate of regression coefficients. 
*  ***Influence:***  An observation is said to be influential if removing the observation substantially changes the estimate of the regression coefficients.  Influence can be thought of as the product of leverage and outlierness.  

Summary of Important Terms
==============================
*  ***Cook's distance (or Cook's D):*** A measure that combines the information of leverage and residual of the observation.  

MultiCollinearity
==============================
* An important aspect in model diagnostics is checking for multicollinearity. We are not going to cover this in this talk - but rather include in a talk about variable selection procedure.




Linear modelling with R (Cheeses)
======================================================

#### Cheddar Cheese Taste

* As cheese ages, various chemical processes take place that determine the taste of the final product. 
* This dataset contains concentrations of various chemicals in 30 samples of mature cheddar cheese, and a subjective measure of taste for each sample. 
*The variables "Acetic" and "H2S" are the natural logarithm of the concentration of acetic asid and hydrogen sulfide respectively. 
* The variable "Lactic" has not been transformed.

#### Reference: 

* Moore, David S., and George P. McCabe (1989). Introduction to the Practice of Statistics.



Linear modelling with R (Cheeses)
======================================================

* Number of cases: 30

#### Variable Names:

* **Case**: Sample number
* **Taste**: Subjective taste test score, obtained by combining the scores of several tasters
* **Acetic**: Natural log of concentration of acetic acid
* **H2S**: Natural log of concentration of hydrogen sulfide
* **Lactic**: Concentration of lactic acid




Linear modelling with R (Cheeses)
======================================================



```r
CheesesData <- read_csv("C:/Users/Kevin/Documents/Ghana_R_Users/Cheeses.csv")

head(CheesesData)
```

```
# A tibble: 6 x 5
   Case Taste Acetic   H2S Lactic
  <dbl> <dbl>  <dbl> <dbl>  <dbl>
1     1  12.3   4.54  3.14   0.86
2     2  20.9   5.16  5.04   1.53
3     3  39     5.37  5.44   1.57
4     4  47.9   5.76  7.50   1.81
5     5   5.6   4.66  3.81   0.99
6     6  25.9   5.70  7.60   1.09
```

Linear modelling with R (Cheeses)
======================================================




```r
Fit_1 <- lm(Taste ~ Acetic + Lactic, data = CheesesData)
Fit_2 <- lm(Taste ~ Acetic + H2S, data = CheesesData)
Fit_3 <- lm(Taste ~ H2S + Lactic, data = CheesesData)

Fit_4 <- lm(Taste ~ Acetic + H2S + Lactic, data = CheesesData)
```

Linear modelling with R (Cheeses)
======================================================
class:smaller-95

#### Aikaike Information Criterion


```r
AIC(Fit_1)
```

```
[1] 237.3884
```

```r
AIC(Fit_2)
```

```
[1] 233.2438
```

```r
AIC(Fit_3)
```

```
[1] 227.7838
```

```r
AIC(Fit_4)
```

```
[1] 229.7775
```



{modelr}
=======================
Compute model quality for a given dataset

Three summaries are immediately interpretible on the scale of the response variable:

* ``rmse()`` is the root-mean-squared-error
* ``mae()`` is the mean absolute error
* ``qae()`` is quantiles of absolute error.

{modelr}
=======================

### Root Mean Square Error


```r
library(modelr)
rmse(Fit_4,CheesesData)
```

```
[1] 9.431174
```


### mean absolute error


```r
mae(Fit_4,CheesesData)
```

```
[1] 7.586727
```


{modelr}
=======================


```r
qae(Fit_4,CheesesData)
```

```
       5%       25%       50%       75%       95% 
 1.051164  4.087882  5.238398 10.848030 16.609669 
```

{modelr}
=======================
Other summaries

* ``mape()`` mean absolute percentage error.
* ``rsae()`` is the relative sum of absolute errors.
* ``mse()`` is the mean-squared-error.
* ``rsquare()`` is the variance of the predictions divided by the variance of the response.

{modelr}
=======================


```r
rsquare(Fit_4,CheesesData)
```

```
[1] 0.6517747
```





Diagnostic Plots for Linear Models with R
===================================================

### Plot Diagnostics for an `lm()` Object

There are six plots (selectable by `which=`) are currently available: 

*  a plot of residuals against fitted values, 
*  a Normal Q-Q plot, 
*  a Scale-Location plot of *sqrt( $\|$ residuals $\|$ })* against fitted values, 

*  a plot of Cook's distances versus row labels, 
*  a plot of residuals against leverages, 
*  a plot of Cook's distances against *leverage/(1-leverage)*.

* By default, the first three and 5 are provided, if you just type something like `plot(fit)`.


Diagnostic Plots
======================================================
class:smaller-95

### Diagnostic Plot 1

* The first one displays the residuals vs. the fitted values we use this to evlauate the mean, variance and correlation of residuals.

* If our assumptions of constant variance and uncorrelated residuals are violated we **may** be able to correct this with a variance-stabilizing transformation.

* see ``ncevTest()``


Diagnostic Plots
======================================================
class:smaller-95

### Diagnostic Plot 1


  plot(Fit_4,
     which=1,
     pch=16,lwd=1.2)
   

Just increment the "``which=``" argument with any integer between 1 and 6


Diagnostic Plots
======================================================
class:smaller-95

Diagnostic Plot 1

<img src="Ghana_R_Users-figure/unnamed-chunk-34-1.png" title="plot of chunk unnamed-chunk-34" alt="plot of chunk unnamed-chunk-34" width="80%" />




Diagnostic Plots
======================================================

#### Diagnostic Plot 2

* The second plot helps us check the normality of the residuals. If the
residuals are indeed normal, they should fall along the dashed line.
* Remember that the normality assumption for our errors allows us to determine
the standard errors of our coefficients and predictions.

Diagnostic Plot 2
======================================================
class:smaller-95


<img src="Ghana_R_Users-figure/unnamed-chunk-35-1.png" title="plot of chunk unnamed-chunk-35" alt="plot of chunk unnamed-chunk-35" width="80%" />



 

Diagnostic Plots
======================================================

#### Diagnostic Plot 3

* The ***Scale-Location*** plot, also called 'Spread-Location' (or 'S-L' plot), takes the square root of the absolute residuals in order to diminish skewness (sqrt($|E|$)) is much less skewed than $| E |$ for Gaussian zero-mean E).
 
 
Diagnostic Plots 3
======================================================
class:smaller-95


<img src="Ghana_R_Users-figure/unnamed-chunk-36-1.png" title="plot of chunk unnamed-chunk-36" alt="plot of chunk unnamed-chunk-36" width="80%" />

Diagnostic Plots
======================================================

#### Diagnostic Plot 4

* This plot details the Cook's Distance for each observation. 
* We will revert to this later.
 
 
Diagnostic Plots 4
======================================================
class:smaller-95


<img src="Ghana_R_Users-figure/unnamed-chunk-37-1.png" title="plot of chunk unnamed-chunk-37" alt="plot of chunk unnamed-chunk-37" width="80%" />

Extracting Cook's Distance
======================================================


```r
cooks.distance(Fit_4) %>% 
  head(5) %>% 
  round(4) %>%
  t()
```

```
          1     2      3      4     5
[1,] 0.0693 7e-04 0.0322 0.0257 8e-04
```

Diagnostic Plots
======================================================

#### Diagnostic Plot 5

* The ***Residual-Leverage*** plot shows contours of equal Cook's distance, for values of `cook.levels` (by default 0.5 and 1) and omits cases with leverage one with a warning. 
* If the leverages are constant the plot uses factor level combinations instead of the leverages for the x-axis. 
* **(The factor levels are ordered by mean fitted value.)**

Diagnostic Plot 5
======================================================
class:smaller-95


<img src="Ghana_R_Users-figure/unnamed-chunk-39-1.png" title="plot of chunk unnamed-chunk-39" alt="plot of chunk unnamed-chunk-39" width="80%" />


Diagnostic Plots
=====================================================

#### Diagnostic Plots 6

* The final plot will display our residuals vs. their leverage. 
* The dashed red lines are level curves that denote a particular value of Cook's distance.
* We will pay attention to points lying beyond the distance of 1. 
* Notice that when we have data with row labels, the points will be labeled with their names. Otherwise, the row number will be shown.

Diagnostic Plot 6
======================================================
class:smaller-95



<img src="Ghana_R_Users-figure/unnamed-chunk-40-1.png" title="plot of chunk unnamed-chunk-40" alt="plot of chunk unnamed-chunk-40" width="80%" />










{broom} R package
=======================

* ``tidy()`` summarizes information about model components such as coefficients of a regression. 
* ``glance()`` reports information about an entire model, such as goodness of fit measures like AIC and BIC. 
* ``augment()`` adds information about individual observations to a dataset, such as fitted values or influence measures.


`tidy()`
=======================


```r
library(broom)
tidy(Fit_4)  %>%
  kable( format = "markdown",digits=4)
```



|term        | estimate| std.error| statistic| p.value|
|:-----------|--------:|---------:|---------:|-------:|
|(Intercept) | -28.8768|   19.7354|   -1.4632|  0.1554|
|Acetic      |   0.3277|    4.4598|    0.0735|  0.9420|
|H2S         |   3.9118|    1.2484|    3.1334|  0.0042|
|Lactic      |  19.6705|    8.6291|    2.2796|  0.0311|



`glance()`
=======================


```r
glance(Fit_4) %>%
  kable( format = "markdown",digits=4)
```



| r.squared| adj.r.squared|   sigma| statistic| p.value| df|    logLik|      AIC|      BIC| deviance| df.residual| nobs|
|---------:|-------------:|-------:|---------:|-------:|--:|---------:|--------:|--------:|--------:|-----------:|----:|
|    0.6518|        0.6116| 10.1307|   16.2214|       0|  3| -109.8888| 229.7775| 236.7835| 2668.411|          26|   30|



`augment()`
=======================


```r
augment(Fit_4) %>%
  head() %>%
  kable( format = "markdown",digits=4)
```



| Taste| Acetic|   H2S| Lactic| .fitted|  .resid| .std.resid|   .hat|  .sigma| .cooksd|
|-----:|------:|-----:|------:|-------:|-------:|----------:|------:|-------:|-------:|
|  12.3|  4.543| 3.135|   0.86|  1.7924| 10.5076|     1.1421| 0.1753| 10.0688|  0.0693|
|  20.9|  5.159| 5.043|   1.53| 22.6374| -1.7374|    -0.1784| 0.0759| 10.3250|  0.0007|
|  39.0|  5.366| 5.438|   1.57| 25.0372| 13.9628|     1.4215| 0.0599|  9.9217|  0.0322|
|  47.9|  5.759| 7.496|   1.81| 37.9375|  9.9625|     1.0299| 0.0883| 10.1184|  0.0257|
|   5.6|  4.663| 3.807|   0.99|  7.0177| -1.4177|    -0.1499| 0.1288| 10.3269|  0.0008|
|  25.9|  5.697| 7.601|   1.09| 24.1652|  1.7348|     0.1952| 0.2304| 10.3238|  0.0029|



Definitions: Leverage and Influence
===========================================================



*  ***Studentized Residuals*** :  Residuals divided by their estimated standard errors (like t-statistics). Observations with values larger than 3 in absolute value are considered outliers.
*  ***Leverage Values (Hat Diag)*** :  Measure of how far an observation is from the others in terms of the levels of the independent variables (not the dependent variable). Observations with values larger than $2(k+1)/n$ are considered to be potentially highly influential, where k is the number of predictors and n is the sample size.

Definitions: DFFITS and DFBETAs
===========================================================

*  ***DFFITS*** :  Measure of how much an observation has effected its fitted value from the regression model. Values larger than $2\sqrt{(k+1)/n}$ in absolute value are considered highly influential. 

*  ***DFBETAS*** :  Measure of how much an observation has effected the estimate of a regression coefficient (there is one DFBETA for each regression coefficient, including the intercept). 
* Values larger than ***2/sqrt(n)*** in absolute value are usually considered highly influential.


Definitions: DFFITS and DFBETAs
===========================================================

* The measure that measures how much impact each observation has on a particular predictor is DFBETAs The DFBETA for a predictor and for a particular observation is the difference between the regression coefficient calculated for all of the data and the regression coefficient calculated with the observation deleted, scaled by the standard error calculated with the observation deleted. 


Definitions: Leverage and Influence
===========================================================

*  ***Cook's D*** :  Measure of aggregate impact of each observation on the group of regression coefficients, as well as the group of fitted values. Values larger than 4/n are considered highly influential.

The studentized residual
=============================================================

* The studentized residual RSTUDENT is estimated by $s(i)^2$ without the ith observation, not by $s^2$. For example,

\[\mbox{RSTUDENT} = \frac{r_i}{s_{(i)} \sqrt{(1 - h_i)}} \]
* Observations with RSTUDENT larger than 2 in absolute value may need some attention.



Regression Diagnostics
===================================

An excellent review of regression diagnostics is provided in ***Overview of Regression Diagnostics***. 

Dr. John Fox's {car} package provides advanced utilities for regression modeling. The prestige data set comes with the car package



{gvlma}
========================

* The {gvlma} package is a comprehensive, automatic testing suite for many of the assumptions of general linear models. 
* It does both statistical tests and diagnostic plots using an extremely simple implementation for powerful results.


{gvlma}
========================

The package is an implementation of a paper by Pena & Slate called ***Global Validation of Linear Model Assumptions*** and allows you to quickly check for:

* ***Linearity*** - the Global Stat tests for the null hypothesis that our model is a linear combination of its predictors.

* ***Homoscedasticity*** - the respective stat tests for the null that the residial variance is relatively constant over the range of values.

* ***Normality*** - skewness and kurtosis tests help you understand if the residuals fits a normal distribution. 

* If the null is rejected you probably need to transform your data in some way (like a log transform). 
This can also be assessed by looking at the normal probability plot it generates.	

{gvlma}
========================




```r
  library("gvlma")

  # model <- lm(y ~ x, data)
  
  
  summary(gvlma(model))
```

```

Call:
lm(formula = Taste ~ Acetic + H2S + Lactic, data = CheesesData)

Residuals:
    Min      1Q  Median      3Q     Max 
-17.390  -6.612  -1.009   4.908  25.449 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)   
(Intercept) -28.8768    19.7354  -1.463  0.15540   
Acetic        0.3277     4.4598   0.073  0.94198   
H2S           3.9118     1.2484   3.133  0.00425 **
Lactic       19.6705     8.6291   2.280  0.03108 * 
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 10.13 on 26 degrees of freedom
Multiple R-squared:  0.6518,	Adjusted R-squared:  0.6116 
F-statistic: 16.22 on 3 and 26 DF,  p-value: 3.81e-06


ASSESSMENT OF THE LINEAR MODEL ASSUMPTIONS
USING THE GLOBAL TEST ON 4 DEGREES-OF-FREEDOM:
Level of Significance =  0.05 

Call:
 gvlma(x = model) 

                     Value p-value                Decision
Global Stat        1.33099  0.8561 Assumptions acceptable.
Skewness           1.12180  0.2895 Assumptions acceptable.
Kurtosis           0.02119  0.8843 Assumptions acceptable.
Link Function      0.02906  0.8646 Assumptions acceptable.
Heteroscedasticity 0.15894  0.6901 Assumptions acceptable.
```


{gvlma}
========================
* The diagnostic plots also let you understand the relation between your data and these assumptions visually. 
* Other useful capabilities are the link function test which is used for understanding whether the underlying data is categorical or continuous.


{gvlma}
========================
class:smaller-95




```r
  plot(gvlma(model))
```

<img src="Ghana_R_Users-figure/unnamed-chunk-47-1.png" title="plot of chunk unnamed-chunk-47" alt="plot of chunk unnamed-chunk-47" width="80%" />
















olsrr
===================================
###{olsrr} 

#### Tools for Building OLS Regression Models

* Tools designed to make it easier for users, particularly beginner/intermediate R users to build ordinary least squares regression models.
* Includes comprehensive regression output, heteroskedasticity tests, collinearity diagnostics, residual diagnostics, measures of influence, model fit assessment and variable selection procedures.
* Author: Aravind Hebbali 

(Source: CRAN)


Diagnostics panel
=============================================
 
Panel of plots for regression diagnostics.

<pre><code>

ols_plot_diagnostics(model)

</code></pre>

#### Arguments 
 
* ``model``: An object of class lm.


Diagnostics panel
=============================================



```r
model <- Fit_4
ols_plot_diagnostics(model)
```

![plot of chunk unnamed-chunk-50](Ghana_R_Users-figure/unnamed-chunk-50-1.png)![plot of chunk unnamed-chunk-50](Ghana_R_Users-figure/unnamed-chunk-50-2.png)![plot of chunk unnamed-chunk-50](Ghana_R_Users-figure/unnamed-chunk-50-3.png)




``Residual QQ plot``
=============================================
#### Description 
 
Graph for detecting violation of normality assumption.

 
<pre><code>
ols_plot_resid_qq(model)
</code></pre>


Residual QQ plot
=============================================


```r
ols_plot_resid_qq(model)
```

![plot of chunk unnamed-chunk-51](Ghana_R_Users-figure/unnamed-chunk-51-1.png)


***ols_plot_resid_box()***
=================================================
 
Box plot of residuals to examine if residuals are normally distributed.

 

<pre><code>
ols_plot_resid_box(model)
</code></pre>


***ols_plot_resid_box()***
=================================================


```r
ols_plot_resid_box(model)
```

![plot of chunk unnamed-chunk-52](Ghana_R_Users-figure/unnamed-chunk-52-1.png)


Breusch pagan test
=================================================

#### Description 
 
Test for constant variance. It assumes that the error terms are normally distributed.

 
<pre><code>

ols_test_breusch_pagan(model, fitted.values = TRUE, rhs = FALSE,
                       multiple = FALSE, 
                       p.adj = c("none", "bonferroni", "sidak", "holm"),
                       vars = NA)
</code></pre>

Breusch pagan test
=================================================

* Breusch Pagan Test was introduced by Trevor Breusch and Adrian Pagan in 1979. 
* It is used to test for heteroscedasticity in a linear regression model. 
* It tests whether variance of errors from a
regression is dependent on the values of a independent variable.

Breusch pagan test
=================================================

* Null Hypothesis: Equal/constant variances
* Alternative Hypothesis: Unequal/non-constant variances
Computation
* Fit a regression model
* Regress the squared residuals from the above model on the independent variables
* Compute the test statistic. It follows a chi square distribution with $p -1$ degrees of freedom, where $p$ is
the number of independent variables, n is the sample size and $R^2$ is the coefficient of determination.

Breusch pagan test
=================================================


#### Value
An object of
class "``ols_test_breusch_pagan``" is a list containing the following components:

* bp : breusch pagan statistic
* p : p-value of bp
* fv : fitted values of the regression model
* rhs : names of explanatory variables of fitted regression model
* multiple logical value indicating if multiple tests should be performed
* padj : adjusted p values
* vars : variables to be used for heteroskedasticity test
* resp : response variable
* preds : predictors


Breusch pagan test
=================================================


```r
# model

# use fitted values of the model

ols_test_breusch_pagan(model)
```

```

 Breusch Pagan Test for Heteroskedasticity
 -----------------------------------------
 Ho: the variance is constant            
 Ha: the variance is not constant        

              Data                
 ---------------------------------
 Response : Taste 
 Variables: fitted values of Taste 

        Test Summary         
 ----------------------------
 DF            =    1 
 Chi2          =    1.157465 
 Prob > Chi2   =    0.2819919 
```


Breusch pagan test
=================================================


```r
# use independent variables of the model
ols_test_breusch_pagan(model, rhs = TRUE)
```

```

 Breusch Pagan Test for Heteroskedasticity
 -----------------------------------------
 Ho: the variance is constant            
 Ha: the variance is not constant        

            Data             
 ----------------------------
 Response : Taste 
 Variables: Acetic H2S Lactic 

        Test Summary         
 ----------------------------
 DF            =    3 
 Chi2          =    4.493994 
 Prob > Chi2   =    0.2128266 
```

Breusch pagan test
=================================================



```r
# use independent variables of the model and perform multiple tests
ols_test_breusch_pagan(model, rhs = TRUE, multiple = TRUE)
```

```

 Breusch Pagan Test for Heteroskedasticity
 -----------------------------------------
 Ho: the variance is constant            
 Ha: the variance is not constant        

            Data             
 ----------------------------
 Response : Taste 
 Variables: Acetic H2S Lactic 

        Test Summary (Unadjusted p values)        
 -----------------------------------------------
  Variable           chi2       df        p      
 -----------------------------------------------
  Acetic           3.8855767     1    0.04870253 
  H2S              0.5192075     1    0.47117994 
  Lactic           1.6874864     1    0.19393265 
 -----------------------------------------------
  simultaneous     4.4939942     3    0.21282661 
 -----------------------------------------------
```

Breusch pagan test
=================================================



```r
# bonferroni p value adjustment
ols_test_breusch_pagan(model, rhs = TRUE, multiple = TRUE, p.adj = 'bonferroni')
```

```

 Breusch Pagan Test for Heteroskedasticity
 -----------------------------------------
 Ho: the variance is constant            
 Ha: the variance is not constant        

            Data             
 ----------------------------
 Response : Taste 
 Variables: Acetic H2S Lactic 

        Test Summary (Bonferroni p values)       
 ----------------------------------------------
  Variable           chi2       df        p     
 ----------------------------------------------
  Acetic           3.8855767     1    0.1461076 
  H2S              0.5192075     1    1.0000000 
  Lactic           1.6874864     1    0.5817979 
 ----------------------------------------------
  simultaneous     4.4939942     3    0.2128266 
 ----------------------------------------------
```

Breusch pagan test
=================================================



```r
# sidak p value adjustment
ols_test_breusch_pagan(model, rhs = TRUE, multiple = TRUE, p.adj = 'sidak')
```

```

 Breusch Pagan Test for Heteroskedasticity
 -----------------------------------------
 Ho: the variance is constant            
 Ha: the variance is not constant        

            Data             
 ----------------------------
 Response : Taste 
 Variables: Acetic H2S Lactic 

          Test Summary (Sidak p values)          
 ----------------------------------------------
  Variable           chi2       df        p     
 ----------------------------------------------
  Acetic           3.8855767     1    0.1391073 
  H2S              0.5192075     1    0.8521151 
  Lactic           1.6874864     1    0.4762621 
 ----------------------------------------------
  simultaneous     4.4939942     3    0.2128266 
 ----------------------------------------------
```

```r
# holm's p value adjustment
ols_test_breusch_pagan(model, rhs = TRUE, multiple = TRUE, p.adj = 'holm')
```

```

 Breusch Pagan Test for Heteroskedasticity
 -----------------------------------------
 Ho: the variance is constant            
 Ha: the variance is not constant        

            Data             
 ----------------------------
 Response : Taste 
 Variables: Acetic H2S Lactic 

          Test Summary (Holm's p values)         
 ----------------------------------------------
  Variable           chi2       df        p     
 ----------------------------------------------
  Acetic           3.8855767     1    0.1461076 
  H2S              0.5192075     1    0.4711799 
  Lactic           1.6874864     1    0.3878653 
 ----------------------------------------------
  simultaneous     4.4939942     3    0.2128266 
 ----------------------------------------------
```

``ols_aic`` Akaike information criterion
=================================================
#### Description 

Akaike information criterion for model selection.

 
<pre><code>
  
  ols_aic(model, method = c("R", "STATA", "SAS"))

</code></pre>

``ols_aic`` Akaike information criterion
=================================================
#### Arguments 
  
* model An object of class lm.
* method A character vector; specify the method to compute AIC. Valid options include R, STATA and SAS.

#### Details 

* AIC provides a means for model selection. Given a collection of models for the data, AIC estimates the quality of each model, relative to each of the other models. 
* R and STATA use loglikelihood to compute AIC. SAS uses residual sum of squares.



``ols_sbc`` Bayesian information criterion
=================================================
#### Description 
 
Bayesian information criterion for model selection.

 
<pre><code>
ols_sbc(model, method = c("R", "STATA", "SAS"))
</code></pre>

#### Arguments
* ``model``: An object of class lm.
* ``method``: A character vector; specify the method to compute BIC. Valid options include
R, STATA and SAS.

ols_sbc Bayesian information criterion
=================================================


```r
# using R computation method
ols_sbc(model)
```

```
[1] 236.7835
```

```r
# using STATA computation method

# ols_sbc(model, method = 'STATA')

# using SAS computation method

# ols_sbc(model, method = 'SAS')
```



Cook's Distance
================================================= 

* Cook's distance was introduced by American statistician R Dennis Cook in 1977. 
* It is used to
identify influential data points. 
* It depends on both the residual and leverage .


Cook's Distance
=================================================

Steps to compute Cook's distance:

*  Delete observations one at a time.
*  Refit the regression model on remaining $n-1$ observations??? 1 observations
*  examine how much all of the fitted values change when the ith observation is deleted.


A data point having a large cook's d indicates that the data point strongly influences the fitted values.



Cooks' D bar plot
=================================================
#### Description 
 
Bar Plot of cook's distance to detect observations that strongly influence fitted values of the model.

 
<pre><code>

ols_plot_cooksd_bar(model)

</code></pre>



Cook's distance:
=================================================

``ols_plot_cooksd_bar`` returns a list containing the following components:

*  ***outliers***: a tibble with observation number and cooks distance that exceed threshold
* ***threshold***: threshold for classifying an observation as an outlier

Cook's distance:
=================================================


 

```r
ols_plot_cooksd_bar(model)
```

<img src="Ghana_R_Users-figure/unnamed-chunk-59-1.png" title="plot of chunk unnamed-chunk-59" alt="plot of chunk unnamed-chunk-59" width="80%" />

Cook's distance:
=================================================


```r
ols_plot_cooksd_chart(model)
```

<img src="Ghana_R_Users-figure/unnamed-chunk-60-1.png" title="plot of chunk unnamed-chunk-60" alt="plot of chunk unnamed-chunk-60" width="80%" />

DFBETa:
=================================================


#### Description 
 
Panel of plots to detect influential observations using DFBETAs.

 
<pre><code>

ols_plot_dfbetas(model)

</code></pre>

#### Arguments 
 
* ``model``: An object of class lm.

#### Details 
 
* DFBETA measures the difference in each parameter estimate with and without the influential point.
* There is a DFBETA for each data point i.e if there are n observations and k variables, there will be $n - k$ DFBETAs. 
* In general, large values of DFBETAS indicate observations that are influential in estimating a given parameter. 
* Belsley, Kuh, and Welsch recommend 2 as a general cutoff value toindicate influential observations and well as an alternative size-adjusted cutoff.




```r
ols_plot_dfbetas(model)
```

<img src="Ghana_R_Users-figure/unnamed-chunk-61-1.png" title="plot of chunk unnamed-chunk-61" alt="plot of chunk unnamed-chunk-61" width="80%" />


olsrr: Leverage
===========================================
 
The leverage of an observation is based on how much the observation's value on the predictor variable differs from the mean of the predictor variable. The greater an observation's leverage, the more potential it has to be an influential observation.

 
<pre><code>

ols_leverage(model)

</code></pre>

#### Arguments 
 
* ``model``: An object of class lm.

 


```r
ols_leverage(model)
```

```
 [1] 0.17525784 0.07593130 0.05994339 0.08829409 0.12879533 0.23036705
 [7] 0.20709897 0.08333780 0.08291114 0.12013909 0.06531941 0.14929496
[13] 0.14821335 0.04332811 0.09000337 0.15153827 0.08934443 0.06198950
[19] 0.08249992 0.26029095 0.14521419 0.03912430 0.20545696 0.23343680
[25] 0.08406925 0.26606306 0.14973461 0.07036401 0.19818511 0.21445340
```



 Studentized residuals vs leverage plot
=============================================================
#### Description 
 
Graph for detecting outliers and/or observations with high leverage.

 
<pre><code>

ols_plot_resid_lev(model)

</code></pre>


Studentized residuals vs leverage plot
=============================================================

 


```r
ols_plot_resid_lev(model)
```

<img src="Ghana_R_Users-figure/unnamed-chunk-63-1.png" title="plot of chunk unnamed-chunk-63" alt="plot of chunk unnamed-chunk-63" width="80%" />



olsrr: PRESS
===========================================
#### Description 
 
PRESS (prediction sum of squares) tells you how well the model will predict new data.


* The prediction sum of squares (PRESS) is the sum of squares of the prediction error.
* Each fitted
to obtain the predicted value for the ith observation. 
* Use PRESS to assess your model's predictive
ability. 
* Usually, the smaller the PRESS value, the better the model's predictive ability.


#### Usage 
<pre><code>

ols_press(model)
</code></pre>




Collinearity diagnostics
===============================================================
#### Collinearity

Variance inflation factor, tolerance, eigenvalues and condition indices.


#### Details 

* Collinearity implies two variables are near perfect linear combinations of one another. 
* Multicollinearity
involves more than two variables.
* In the presence of multicollinearity, regression estimates
are unstable and have high standard errors.

Collinearity diagnostics
===============================================================
 


* ``ols_coll_diag(model)``
* ``ols_vif_tol(model)``
* ``ols_eigen_cindex(model)``


 Collinearity diagnostics
===============================================================



```r
# vif and tolerance
ols_vif_tol(model)
```

```
  Variables Tolerance      VIF
1    Acetic 0.5459740 1.831589
2       H2S 0.5019577 1.992200
3    Lactic 0.5160194 1.937912
```

Collinearity diagnostics
==============================================================



```r
# eigenvalues and condition indices

ols_eigen_cindex(model) %>%
  kable( format = "markdown",digits=4)
```



| Eigenvalue| Condition Index| intercept| Acetic|    H2S| Lactic|
|----------:|---------------:|---------:|------:|------:|------:|
|     3.9154|          1.0000|    0.0006| 0.0004| 0.0034| 0.0014|
|     0.0646|          7.7878|    0.0347| 0.0072| 0.5673| 0.0000|
|     0.0165|         15.3968|    0.0698| 0.0154| 0.2826| 0.9483|
|     0.0036|         33.1344|    0.8950| 0.9770| 0.1466| 0.0504|

Collinearity diagnostics
===============================================================



```r
# collinearity diagnostics
ols_coll_diag(model)
```

```
Tolerance and Variance Inflation Factor
---------------------------------------
  Variables Tolerance      VIF
1    Acetic 0.5459740 1.831589
2       H2S 0.5019577 1.992200
3    Lactic 0.5160194 1.937912


Eigenvalue and Condition Index
------------------------------
   Eigenvalue Condition Index    intercept       Acetic        H2S       Lactic
1 3.915360446         1.00000 0.0005615356 0.0003642985 0.00344925 1.365207e-03
2 0.064557155         7.78778 0.0347152460 0.0072159623 0.56732059 2.694277e-05
3 0.016516138        15.39684 0.0697512251 0.0154437761 0.28263569 9.482560e-01
4 0.003566261        33.13441 0.8949719933 0.9769759631 0.14659447 5.035184e-02
```





Assumption of Constant Variance
============================================

#### Homoscedasticity

* ***Homoscedascity*** is the technical term to describe the variance of the residuals being constant across the range of predicted values. 

* ***Heteroscedascity*** is the converse scenario : the variance differs along the range of values.



Suppose you plot the individual residuals against the predicted value, the variance of the residuals predicted value should be constant (Diagnostic Plot 1). 






Using R
=====================================

```r
# Evaluate homoscedasticity

# non-constant error variance test

library(car)
ncvTest(fit)
```

```
Non-constant Variance Score Test 
Variance formula: ~ fitted.values 
Chisquare = 1.157465, Df = 1, p = 0.28199
```

component+residual plots
==================================

* component+residual plots, also called partial-residual plots, for linear and generalized linear models.
* a graphical technique that attempts to show the relationship between a given independent variable and the response variable given that other independent variables are also in the model.
* Ceres plots are a generalization of component+residual (partial residual) plots that are less prone to leakage of nonlinearity among the predictors. 


Nonlinearity
=============================================================

#### component + residual plot 


```r
# Evaluate Nonlinearity

# component + residual plot 


crPlots(fit)
```

<img src="Ghana_R_Users-figure/unnamed-chunk-69-1.png" title="plot of chunk unnamed-chunk-69" alt="plot of chunk unnamed-chunk-69" width="80%" />


Nonlinearity
=============================================================

#### ceres plot


```r
# Ceres plots 

ceresPlots(fit)
```

<img src="Ghana_R_Users-figure/unnamed-chunk-70-1.png" title="plot of chunk unnamed-chunk-70" alt="plot of chunk unnamed-chunk-70" width="80%" />

Nonlinearity
=============================================================


Test for Autocorrelated Errors


```r
# Test for Autocorrelated Errors

durbinWatsonTest(fit)
```

```
 lag Autocorrelation D-W Statistic p-value
   1       0.1692325       1.57513    0.18
 Alternative hypothesis: rho != 0
```


avplot & av plots
==================================
* The avplot command is short for added-variable plot and draws exactly that. 
* The other name for added variable plot is a partial-regression leverage plot. 


Outliers
===========================================

* *"Outliers are sample values that cause surprise in relation to the majority of the sample"* 

* (W.N. Venables and B.D. Ripley. 2002. Modern applied statistics with S. New York: Springer, p.119).


* Crucially, surprise is in the mind of the beholder and is dependent on some explicit model of the data. 

* Importantly, Normality is only an assumption:There may be another model under which the outlier is not surprising at all, say if the data really are lognormal or 
gamma rather than normal. 

Outliers
===========================================

* Data points that diverge in a big way from the overall pattern are referred to as ``outliers".

* In the case of Simple Linear Regression, there are four ways that a data point might be considered an outlier.


  *  It could have an extreme X value compared to other data points.
  *  It could have an extreme Y value compared to other data points.
  *  It could have extreme X and Y values.
  *  It might be distant from the rest of the data, even without extreme X or Y values.


Outliers
===========================================

*  After a regression line has been computed for a group of data, a point which lies far from the line 
(and thus has a large residual value) is known as an outlier. 
* Such points may represent erroneous data, or may indicate a poorly fitting regression line. 

*  If a point lies far from the other data in the horizontal direction, it is known as an ***influential observation***. 
* The reason for this distinction is that these points have may have a significant impact on the slope of the regression line.

Outliers
===========================================


#### ``outlierTest()``
* Suppose we have some fitted models and we would like to see if there are any outliers. 

* For this purpose, we can use ``outlierTest()`` from {car} R package. 


Outliers
===========================================




```r
library(car)
outlierTest(Fit_1)   
```

```
No Studentized residuals with Bonferroni p < 0.05
Largest |rstudent|:
   rstudent unadjusted p-value Bonferroni p
15   2.3563           0.026274      0.78821
```


```r
outlierTest(Fit_2)   
```

```
No Studentized residuals with Bonferroni p < 0.05
Largest |rstudent|:
   rstudent unadjusted p-value Bonferroni p
15  2.48439           0.019742      0.59225
```

Outliers
===========================================




```r
outlierTest(Fit_3)   
```

```
No Studentized residuals with Bonferroni p < 0.05
Largest |rstudent|:
   rstudent unadjusted p-value Bonferroni p
15  2.98867          0.0060495      0.18148
```


```r
outlierTest(Fit_4)   
```

```
No Studentized residuals with Bonferroni p < 0.05
Largest |rstudent|:
   rstudent unadjusted p-value Bonferroni p
15  3.01547          0.0058177      0.17453
```



Regression Diagnostics:avPlots
==========================

#### `avPlots`

*  Graphs outcome vs predictor variables holding the rest constant (also called partial-regression plots)
*  Help identify the effect(or influence) of an observation on the regression coefficient of the predictor variable

Regression Diagnostics: avPlots
===================================


```r
library(car)
reg1 <-lm(prestige ~ education + income + type, data = Prestige)
avPlots(reg1)
```

![plot of chunk unnamed-chunk-76](Ghana_R_Users-figure/unnamed-chunk-76-1.png)
Regression Diagnostics: `influenceIndexPlot()`
===================================

#### `influenceIndexPlot`

*  Cook's distance measures how much an observation influences the overall model or predicted values
*  Studentizided residuals are the residuals divided by their estimated standard deviation as a way to standardized
*  Bonferronitest to identify outliers
*  Hat-points identify influential observations (have a high impact on the predictor variables)


Regression Diagnostics :`influenceIndexPlot()`
===================================


```r
library(car)
reg1 <-lm(prestige ~ education + income + type, data = Prestige)
influenceIndexPlot(reg1)
```

![plot of chunk unnamed-chunk-77](Ghana_R_Users-figure/unnamed-chunk-77-1.png)




#### `influencePlot`

*  `influencePlot()` creates a bubble-plot combining the display of Studentizedresiduals, hat-values, and Cook's distance (represented in the circles).




```r
library(car)
reg1 <-lm(prestige ~ education + income + type, data = Prestige)
influencePlot(reg1)
```

<img src="Ghana_R_Users-figure/unnamed-chunk-78-1.png" title="plot of chunk unnamed-chunk-78" alt="plot of chunk unnamed-chunk-78" width="80%" />

```
                       StudRes        Hat       CookD
general.managers    -1.3134574 0.33504477 0.172503975
physicians          -0.3953204 0.22420309 0.009115491
medical.technicians  2.8210910 0.06858836 0.109052582
electronic.workers   2.2251940 0.02701237 0.026372394
```


Alcohol and Tobacco Data
========================================
This example is for exposition only. We will ignore the fact that this may not be a great way of modeling the this particular set of data!



```r
alctob <- data.frame( cbind(
Alcohol = c(6.47, 6.13, 6.19, 4.89, 5.63, 4.52, 
            5.89, 4.79, 5.27, 6.08, 4.02),
Tobacco = c(4.03, 3.76, 3.77, 3.34, 3.47, 2.92, 
            3.20, 2.71, 3.53, 4.51, 4.56)),
row.names = c("North", "Yorkshire", "Northeast", 
"East Midlands", "West Midlands", "East Anglia", 
"Southeast", "Southwest", "Wales", 
"Scotland", "N. Ireland"))
```





```r
alctobwo <- subset(alctob,rownames(alctob)!="N. Ireland") 
#without North Ireland

plot(alctob$Tobacco, alctob$Alcohol,
main="Weekly Household Spending on Alcohol vs. Tobacco",
xlab="Tobacco Spending (GBP)",
ylab="Alcohol Spending (GBP)",
pch=16,col="red",cex=1.5,font.lab=2) 
```

<img src="Ghana_R_Users-figure/unnamed-chunk-80-1.png" title="plot of chunk unnamed-chunk-80" alt="plot of chunk unnamed-chunk-80" width="80%" />

```r
#note N. Ireland in the bottom-right
```



```r
fit1 <- lm( Alcohol ~ Tobacco, data = alctob)
fit2 <- lm( Alcohol ~ Tobacco, data = alctobwo)
```
All Observations
=================================================


```r
summary(fit1)
```

```

Call:
lm(formula = Alcohol ~ Tobacco, data = alctob)

Residuals:
    Min      1Q  Median      3Q     Max 
-1.7080 -0.4245  0.2311  0.6081  0.9020 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)  
(Intercept)   4.3512     1.6067   2.708   0.0241 *
Tobacco       0.3019     0.4388   0.688   0.5087  
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.8196 on 9 degrees of freedom
Multiple R-squared:  0.04998,	Adjusted R-squared:  -0.05557 
F-statistic: 0.4735 on 1 and 9 DF,  p-value: 0.5087
```


Outlier Removed
============================================

```r
summary(fit2)
```

```

Call:
lm(formula = Alcohol ~ Tobacco, data = alctobwo)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.51092 -0.42434  0.06056  0.34406  0.62991 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)   
(Intercept)   2.0412     1.0014   2.038  0.07586 . 
Tobacco       1.0059     0.2813   3.576  0.00723 **
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 0.446 on 8 degrees of freedom
Multiple R-squared:  0.6151,	Adjusted R-squared:  0.567 
F-statistic: 12.78 on 1 and 8 DF,  p-value: 0.007234
```



Outliers
==============



The conservative outlier test that we talked about in class uses the
Bonferonni inequality to calculate the p-values we associate with the
Student's-t test. 

In R, we can use the `outlierTest()`` command to perform this
test on our model. Remember that when we test for influence, we are testing
the effect of an observation on model coefficients. 

Therefore we need to
give the outlierTest command a linear model as its input.


```r
outlierTest(fit1)
```

```
            rstudent unadjusted p-value Bonferroni p
N. Ireland -4.732091          0.0014789     0.016268
```

We can also use R to calculate Cook's distance. 
Here we label any observation with Cook's distance greater than 1 as influential.


```r
cooks.distance(fit1)
```

```
        North     Yorkshire     Northeast East Midlands West Midlands 
  0.114101051   0.036517838   0.043728951   0.023600304   0.004740759 
  East Anglia     Southeast     Southwest         Wales      Scotland 
  0.147326647   0.046646563   0.077488350   0.001821694   0.068921892 
   N. Ireland 
  1.747233521 
```

Influence Plots
============

Finally, one of the easier ways to evaluate our residuals and look for
for influential points is through plots. 



```r
#qq plot for studentized resid 
qqPlot(fit1, main="QQ Plot",pch=18, lim=c(-3,2)) 
```

<img src="Ghana_R_Users-figure/unnamed-chunk-86-1.png" title="plot of chunk unnamed-chunk-86" alt="plot of chunk unnamed-chunk-86" width="80%" />

```
     North N. Ireland 
         1         11 
```

Influence Plots
============



```r
# leverage plots
leveragePlots(fit1) 
```

<img src="Ghana_R_Users-figure/unnamed-chunk-87-1.png" title="plot of chunk unnamed-chunk-87" alt="plot of chunk unnamed-chunk-87" width="80%" />








Influence Plots
============



```r
# Influential Observations
# Influential Observations
# added variable plots 
avPlots(fit1)
```

![plot of chunk unnamed-chunk-89](Ghana_R_Users-figure/unnamed-chunk-89-1.png)

Influence Plots
============


```r
# Cook's D plot
# identify D values > 4/(n-k-1) 
cutoff <- 4/((nrow(mtcars)-length(fit1$coefficients)-2)) 
plot(fit, which=4, cook.levels=cutoff)
```

![plot of chunk unnamed-chunk-90](Ghana_R_Users-figure/unnamed-chunk-90-1.png)

Influence Plots
============


```r
# Influence Plot 
influencePlot(fit1,id.method="identify", 
main="Influence Plot", 
col="red",
sub="Circle size is proportial to Cook's Distance" )
```

![plot of chunk unnamed-chunk-91](Ghana_R_Users-figure/unnamed-chunk-91-1.png)

```
               StudRes       Hat      CookD
North        1.2178081 0.1395123 0.11410105
East Anglia -0.9904538 0.2306073 0.14732665
Southwest   -0.5417970 0.3272829 0.07748835
N. Ireland  -4.7320908 0.3451163 1.74723352
```

Non-normality
=============


```r
# Normality of Residuals
# qq plot for studentized resid
qqPlot(fit1, main="QQ Plot")
```

![plot of chunk unnamed-chunk-92](Ghana_R_Users-figure/unnamed-chunk-92-1.png)

```
     North N. Ireland 
         1         11 
```



```r
# distribution of studentized residuals
library(MASS)
sresid <- studres(fit) 
hist(sresid, freq=FALSE, 
main="Distribution of Studentized Residuals")
xfit<-seq(min(sresid),max(sresid),length=40) 
yfit<-dnorm(xfit) 
lines(xfit, yfit)
```

![plot of chunk unnamed-chunk-93](Ghana_R_Users-figure/unnamed-chunk-93-1.png)

Non-constant Error Variance
==================================


```r
# Evaluate homoscedasticity
# non-constant error variance test
ncvTest(fit)
```

```
Non-constant Variance Score Test 
Variance formula: ~ fitted.values 
Chisquare = 3.311276, Df = 1, p = 0.068806
```

Non-constant Error Variance
==================================


```r
# plot studentized residuals vs. fitted values 
spreadLevelPlot(fit)
```

![plot of chunk unnamed-chunk-95](Ghana_R_Users-figure/unnamed-chunk-95-1.png)

```

Suggested power transformation:  -5.624329 
```






---
layout: post
title: Regression Project
---


My Dataset that I choose is Happiness score in each countries. From this dataset contain Happiness Score, Family index, Freedom, Economy (GDP Per Capita), Health (Life Expectancy), Trust (Government Corruption),
Dystopia Residual, Standard Error, Generousity, Country, and Happiness Rank.
My goal is to predict the Happiness score from those parameter. Which is very interesting!

<h1> Cleaning our Data </h1>
<p>If we take a look at my dataset. We will found some excessive type of data that we don't have to include it when we are going to predict it.
<h2> Standard Error and Generousity </h2>
  <p>These data have absolute correlation less than 0.2. In my opinion, I think it would be better to cut it out.
<h2>Country and Happiness Rank</h2>
  <p>These data are kind of excessive data that we don't have to include. For the country name data, we don't have to use that because it's categorical data which have unique value and this might not be good if we use dummies columns. In addition, we can guess the country from the remain data. For the Happiness Rank, we can observe that they have the correlation about 0.99 which is closed to 1. Basically, we can imply intuitively that Happiness Rank is based on Happiness Score. So we can remove it.
 <h2> The one categorical data left : Region </h2>
   <p>After we cut the redundant data out. We have one categorical data left -- Region. So we keep 2 data that is important : one_hot DataFrame which we get from get_dummies() , hot_columns (List of columns in one_hot DataFrame) -- This part will be very important to next amazing method that I've write by myself.
<h1> Correlation After Cleaning Data </h1>
<code>
    Trust (Government Corruption)    0.395199
    
    Dystopia Residual                0.530474<br>
    Freedom                          0.568211<br>
    Health (Life Expectancy)         0.724200<br>
    Family                           0.740605<br>
    Economy (GDP per Capita)         0.780966<br>
</code>
<p>From this correlation list which related to the Happiness Score. We don't have any negative correlation here. That means all of these parameter will encourage the Happiness Score in the same way. Additionally, even if the minimum correlation is 0.395199. I don't want to delete it. Because I think it enough to contain, I might encourage the prediction in a good significant.

<h1> How's about the PAIRPLOT! </h1>

<img src="/images/regression_pairplot.png"/>

<p>According to the image above, We might see some skew values from some parameters. I already tried to approach with the log method, I found that it going to be -inf. In my assumption, because the most of value in my dataset is close to 0 or 1 which they can lead to the huge negative value when they applied to log. So we decided to keep in that way.

<h1> Let's Determine the Polynomial Degree! </h1>
   In this process, there are two big interesting issue to disscuss.

   <h2> 1. Tradeoff of Variance and Bias </h2>
    <p>In this scheme, we are gonna find the best degree for polynomial to
    do some regression on the data. So we would apply the PolynomialFeatures and apply all of them to data, and find the most feasible one. Sometimes,It might be fluctuate, but the degree which gives minimum mean squared error is consistent. So we prefer to use 1 degree polynomial regression on the data -- Linear Regression.

<img src = "/images/regression_deg_plot.png"/>

<h2> 2. Don't normalize all of them! </h2>
    <p>At first we have to scale the data to normalize the distribution of the data. The important key is we shouldn't scale to the whole dataset, because we are going to pretend like we haven't seen the test set before. To do like that when we split the dataset -- which we already joined one_hot dataframe before -- by 80:20 ratio (train:test). and we fit the Scaler on the train dataset, and transform on the test dataset. The important thing is we don't have to scale on dummies column that we changed from the categorical variable. So we will temporarily split by the "hot_columns" that we collected it before, and then we join it back together after we scaled. 
    !!PLEASE USE StandardScaler CAREFULLY!! 
    (Because it would give you numpy array not DataFrame, and index would be change!)
    After all above process, it would be a little bit complicated, 
    So I would like to write my own function called split_scale() which can be used instead of train_test_split(), which is more flexible to do seperate scaling.


<h1> Model Tournament!! </h1>
    <p>In this scenario, I prefer to choose 4 different possible method to approach this problem: Linear Regression with StandardScaler and Train_test_split, Linear Regression with just Train_test_split, Ridge and Cross Validation with StandardScaler, and Ridge and just Cross Validation. When we compete R^2 and Adjust R^2 value we got this values:
    <br>
    <code>
    1.Linear Regression with StandardScaler and Train_test_split<br>
        0.9926908343950043<br>
        0.9838154190175095<br>
        <br>
    2. Linear Regression with just Train_test_split<br>
        0.9919631136399509<br>
        0.9822040373456057<br>
        <br>
    3.Ridge and Cross Validation with StandardScaler<br>
        0.9931769996497433 <br>
        0.992348492464355 <br>
        <br>
    4.Ridge and just Cross Validation<br>
        0.9931203201266213<br>
        0.992284930427711 <br>
</code>

    We can implied that StandardScaler might make the data more intuitive to predict. 
    The winner of this Tournament is "Ridge and Cross Validation with StandardScaler!"

<h1> Summary </h1>
   <p>The model that we got is RidgeCV with StandardScaler. which alpha is 1.0 and the Equation is 
     <img src= "/images/regression_equation.png">
     And you can see what I did by clicking <a href="https://github.com/kimmypracha/RegressionProject">here.</a>
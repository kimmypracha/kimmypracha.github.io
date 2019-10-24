---
layout: post
title: Regression Project
---

Summary of the Regression Project

My Dataset that I choose is Happiness score in each countries. From this dataset contain Happiness Score, Family index, Freedom, Economy (GDP Per Capita), Health (Life Expectancy), Trust (Government Corruption),
Dystopia Residual, Standard Error, Generousity, Country, and Happiness Rank.
My goal is to predict the Happiness score from those parameter. Which is very interesting!

<h1> Cleaning our Data </h1>
If we take a look at my dataset. We will found some excessive type of data that we don't have to include it when we are going to predict it.
<h2> Standard Error and Generousity </h2>
  These data have absolute correlation less than 0.2. In my opinion, I think it would be better to cut it out.
<h2>Country and Happiness Rank</h2>
  These data are kind of excessive data that we don't have to include. For the country name data, we don't have to use that because it's categorical data which have unique value and this might not be good if we use dummies columns. In addition, we can guess the country from the remain data. For the Happiness Rank, we can observe that they have the correlation about 0.99 which is closed to 1. Basically, we can imply intuitively that Happiness Rank is based on Happiness Score. So we can remove it.
 <h2> The one categorical data left : Region </h2>
   After we cut the redundant data out. We have one categorical data left -- Region. So we keep 2 data that is important : one_hot DataFrame which we get from get_dummies() , hot_columns (List of columns in one_hot DataFrame) -- This part will be very important to next amazing method that I've write by myself.
<h1> Correlation After Cleaning Data </h1>
    Trust (Government Corruption)    0.395199
    Dystopia Residual                0.530474
    Freedom                          0.568211
    Health (Life Expectancy)         0.724200
    Family                           0.740605
    Economy (GDP per Capita)         0.780966

    From this correlation list which related to the Happiness Score. We don't have any negative correlation here. That means all of these parameter will encourage the Happiness Score in the same way. Additionally, even if the minimum correlation is 0.395199. I don't want to delete it. Because I think it enough to contain, I might encourage the prediction in a good significant.

<h1> How's about the PAIRPLOT! <h1>

![_config.yml]({{ site.baseurl }}/images/regression_pairplot.png)

According to the image above, We might see some skew values from some parameters. I already tried to approach with the log method, I found that it going to be -inf. In my assumption, because the most of value in my dataset is close to 0 or 1 which they can lead to the huge negative value when they applied to log. So we decided to keep in that way.

<h1> Let's Determine the Polynomial Degree! </h1>

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.
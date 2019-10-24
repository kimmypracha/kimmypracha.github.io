---
layout: post
title: RollerCaster Project
---

This is the project that I've collaborate with Ethan and Sophie. It is about the rollercaster data. 
<h1> Cleaning Data </h1>
When we clean the data.We first stripped the data frame. Then, we cleaned the data by dropping rows without values in what we thought were the most important categories, height and speed. We dropped the Vertical Angle column. We replaced a value of 200 ft with just 200 and changed the variable type to float. We fill na value with 0. and then we change each category to a number that we determined

<h1> Using Indicator to rank the score </h1>
    We use the formula x_new = (x_old - X_min)/X_max which can use to rank the data well. 
    and then we weight these score properly by intuition. From that formula we got this rank.
    <img src = "/images/rollercoaster_rank.png">

<a href = "https://github.com/kimmypracha/Rollercoaster"> You can see what we have done here! </a>

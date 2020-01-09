---
layout: post
Title: Final Project Daily Log
---

Below is a log of my daily progress, including:

1.) What I worked on today

2.) What I learned

3.) Any road blocks or questions that I need to get answered

4.) What my goals are for tomorrow

**January 7th**
Today, I construct a datafrome from the movie dataset containing about 30000 movies. My plan is to use TFIDF vector and to predict the genre of movies. but when I run the program, everything stop, and I can’t continue my project. I think I should start on the cloud to make it more stable. So I would like to start to build on cloud tomorrow.
 I also learned that there are many way to change word to vector. Here's the different:
 TFIDF Vector : It is the vector that get from the linear algebra calculation. This also show how most important for each word. 
 Word2Vec : It is the vector that get from neural network to illustrate how it relate to the other words. This might be used for finding some relationship between word, or information retrieving.
**January 8th**
Today, I worked on the text preprocessing before we convert text to vector and then use vector with several algorithm that we are going to use in the future. I also found something interesting about "Chunking" and "POS_tagging". 
POS Tagging is from Part Of Speech tagging. We can detect the part of speech of each word by using pos_tag() method from nltk library. I found this while I was looking for proper noun detection.
Chunking is the method that we used for divide chunks of words by regular expression of tag, which came from pos_tag() method. So we can construct the grammar structure and use regular expression to capture sentence corresponding to our grammar structure. In this day, I'm still having a problem with google cloud that I don't have enough quota for upgrading gpu in the google cloud platform in my old gmail. OES email also has a permission issue that I cannot solve. I also take an enormous of time when I reduce stopwords and cut out Proper Noun on the movie plot text. I cannot even show the text. So I think something might went wrong. I'll figure it out as soon as possible. 
If I have time, I'm going to bring vector from GloVe, Word2Vec, and TFIDF vectorizor algorithm to used on movie genres classification on several algorithms such as GradientBoostingClassifier, KNN, RandomForest By picking just 40% or 20% of the whole dataset first due to the huge data handling problem. 

**January 9th**

**January 10th**

**January 13th**

**January 15th**

**January 16th**

**January 17th**
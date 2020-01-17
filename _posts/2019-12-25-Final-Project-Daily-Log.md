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
   Today, I worked on the train_test_split method. I hope that this would help to reduce the data. However, it still took a time. So I would do on the Text Summarization on the plot to reduce the plot into 1-2 sentence or reduce into a couple of word that have impact enough on the genre. I also learned about Gensim library for Word2Vec Algorithm and how to use it but I'm still confusing about the implementation and application. I'm going to used it after I figured out on the TFIDF Vector issue. Also, I'm also learning about GloVe and Fastext which are going to be an alternative for Word Vectorization too. Tomorrow, I'm going to add Text Summarization on the movie plot data to reduce the text and increase computational speed. I also have a problem on the dataset about the genre. The dataset contained the multiple type of genre such as "horror, science fiction", "drama, science, fiction." I'm figuring it out for the best way to clean this data. If I keep this kind of movie genre, there are 2267 type of movie. It is too much. So I would like to simplify type of movie. 
**January 10th**
   I'm trying to figure out thw way to simplify the classification. According to the dataset, the movie that contain multilabel is 11% of the whole dataset. Moreover, each category is redundant. For example, the dataset contains "animation", "animated flims", "animated movies", or "egypt documentary". So I prefer to search for another specific movies genres dataset. I finally end up with IMDB dataset. The dataset is csv file. At the first time, I cannot open the csv file by the read_csv() method of Pandas library due to the tricky of the word tokenization. The movie plot in the dataset have a lot of space, so when we tokenized them, we will got unequal column of each row in the dataframe. So I use regular expression to solve this problem. I read the csv file as the text file. In each line, I used regex to capture topic and substitute with blank space first. Then I used regex again to capture the genre part (which is have a lot of columns , they used number 0 or 1 to tell the related genres) and substituted with blank space again. So I finally got a list of topic, a list of movie plot and a list of vector of genres (I will explain it later.)
   Today, I learned to use the regular expression to capture the word to the list. I also learned how to using the word2vec in python. but I just start to use it, and it is still loading, so I will talk about the result later. Next time, we will compare the result of each algorithm after we finish the preprocessing part.
**January 13th**
  Today, I put my work on convert text to vector with Word2Vec algorithm. It takes some time. Finally, I got the vector from word2vec. The interesting thing is we can choose dimension for the result vector. However, I also stuck on put some vector into the LogisticRegression. I tried to classify on 1 genre first (to be simple). but it still took a time, I think there were something wrong. Now, I still can not diagnose the problem.
  Next time, I will try many possible way do deal with LogisticRegression to make it work. and then continue on my main goal which is comparing to other algorithm.
**January 15th**
  Today, I start to clean my text data, which is word tokenization, getting only word(no number and symbol),deleting stopwords, and stemming, and save it in the pickle file to avoid repetitive loading. So I can save my time. I store both vector and movie plot that I've got in the pickle file and load it when I restart the kernel. After this, I can go further than waiting for the same calculation to find a way to train the model and predict. So I finally did the prediction. 
  1. Use word2vec algorithm to create vector dictionary from train dataset, and here is what I got.
  Accuracy 
  MultiLabel K-NearestNeighbor : 0.2861
  Decision Tree : 0.1898
  Extra Tree : 0.1629
  Random Forest : 0.2226
  2. Use CountVectorizer and TfidfTransformer to create a word vector and predict with the same algorithm.
  Accuracy
  Multi-Label K-NearestNeighbor : 0.5726
  Decision Tree : 0.2117
  Extra Tree : 0.1608
  Random Forest : 0.1615
  However, Multi-Label KNN is very slow for processing. We are looking for BinaryRelevance Technique to apply to other faster and more efficient algorithm that cannot apply to multi-label classification directly. but we cannot split the data evenly. Tomorrow, I will figure out about how to split the dataset evenly that we can have data enough to predict test dataset with trainning on the train dataset. 

**January 16th**
   Today, I learned on stratified sampling and looking for the percent of 0 and 1 in each genres. To avoid single-class classification. I cut 14 genres out, which have 95-100% containing zero value in that genre. So now I can applied BinaryRelevance Technique for Multi-Label classification. So I can run svm for this dataset, but it still took too long time. So we might find other algorithm that might be more interesting than svm. 
   The result that I got from this time is better than the previous version if we compared to the same algorithm. If I have more time, I will write the whole comparation to each algorithm and use %%timeit module to measure time that they might take and then decide for putting into cross_validation to optimize the quality of the text classification model.
**January 17th**
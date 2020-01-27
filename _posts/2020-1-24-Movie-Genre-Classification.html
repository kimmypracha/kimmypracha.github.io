---
layout: post
title: Movie Genre Classification Project
---

This is the first NLP project for me. I choose to do the Text Classification Project which is the most interesting topic to me. I've found the interesting dataset, which is 'Movie Dataset'  
<h1> About the dataset</h1>
   The Dataset is from IMDB Movie Dataset which is reinterpreted by 
            http://www.davidsbatista.net/blog/2017/04/01/document_classification/
    which contain the data from the movie more than 160000 movies.
    so I don't have to take a lot of time on searching for the movie category and movie plot because IMDB have several kind of movie dataset.  Thank you to 'DavidBatista' for a well-interpreted dataset. However, this file might have something wrong that I cannot open like him. I thought this file might corrupt in some ways, so I cannot read this file with read_csv method from pandas library.
            So I go to look at the file if there are something wrong, and this is how the file look like
            <img src='dataset.png'>
            It looks messy right? This dataset contain this format:
            (Topic) (Movie Plot) (Binary Representation of each category - 0 No, 1 Yes)
            The topic part will cover with 3 quotation marks (Such as """Avenger"" Endgame") and the genre parts (Binary representation part) will have only 0 or 1 separate by space which the position of each number will correspond to the columns of genres. 
            My assumption is "Movie plots at some lines are not covered by quotation mark, but some of them are covered by quotation mark." If it's true, this can cause the table have inequal columns in each row. As a result, the read_csv() method didn't work.
    <h2> Start to extract the dataset </h2>
            I started to read file with as a text file on each line, and put it into a list of sentence of each line. Of course, more than 160,000 lines. 
                1. Capture 'Topic' First
                    Since Topic is the most part that has pattern, so I use regular expression to extract the text that covered by three quotation marks. I capture that data to append to topic_list and delete it from the text in the main list.
                2. Capture 'Number'
                    Since the another part that is easily to capture is binary representation part. So I use regular expression to capture the text that have 0 or 1 with space repetition for 28 times. So I can capture the binary representation part. I append this part as a list of number to vector_list. So I'll have vector_list as a list of list containing binary representation of movie category. Afterward, I deleted the binary representation from the main text. 
                3. The remaining text is movie plot!
                    Finally, we have movie plot, I will put it into plot_list which is the list that we will use later. 
    <h2>Cleaning the dataset</h2>
                Since this dataset has many restriction and very messy as I said below.
                1. The data is very messy, there are a lot of # and number and ‘ (aphostophe)
                    I solved this problem  with isalpha() method to classify the word. 
                2. The data doesn’t include only movie plot in english language.
                    I used ‘detect’ method from ‘langdetect’ library to classified only english movie plot
                3. There are 28 columns of genre which each cell represent number 0 or 1 (0 means that movies are not that genre, and 1 means that movies is that genre.)
                    I drop 14 columns which each of them has 0 value more than 93%
                4. There are a column containing only zero value
                    I drop that column.
    <h2>Cleaning the text</h2>
                Since we have to do a calculation, we have to simplify the text as much as possible, avoid unneccessary action in the classification process. This is a process to clean the text data. 
                    1. Tokenize 
                    2. Word only
                    3. No Stopword
                    4. Make it all lowercase
                    5. Stemming 
                You can see all of these method that I did in the picture below. 
                <img src='cleaningdata.png'>
<h1>Classification</h1>
    Text Representation
        Since the data that I'm dealing with is text data. So I have to convert the text into the type of data that can be calculated. So I brought to choice to consider: Word2Vec vector and Tf-idf Vector. Let's see what is the difference between these vectors.
        1. Vector from Word2Vec algorithm 
            Word2Vec algorithm is a group of model that are used to produce text embedding. These models are shallow, two-layer neural network that are trained to reconstruct linguistic context of words. These vectors is suited for information retrieving, or understanding some information.
        2. Vector from TF-IDF algorithm
            TF-IDF is the score value to evaluate how probably-important it is based on the frequency of word and the uniqueness of word. TF-IDF comes from both values TF and IDF, and this is how we can calculate these values.
            Let w is a word that we would like to find tf, and idf value.
            TF :
                tf(w) =  number of word w in the document/total number of word in the document
            IDF:
                idf(w) = log(total numbers of documents/number of documents containing word w)
            and this is how tf-idf values come up:
            TF-IDF:
                tf-idf(w) = tf(w)*idf(w)
            TF-IDF vector is suited for text classification, topic modeling, or stop word filtering, because this vector can do well on selecting the word that is the most important.
    Classifier
        In this project, these are classifier models that I used.
            1. Decision Tree
            2. Extra Tree
            3. Random Forest
            4. MLkNN (Multi-label K-Nearest Neighbor)
        To be simple, I used the same splitted dataset on those model and judged by the accuracy from each model. I did this two times. First time I trained model with Word2Vec vector to get measure the accuracy, and then I trained model with TF-IDF vector afterward.
    The result and analysis
        After we run all of those model, this is the result that we got. 
        <img src='result.png'>
        MLkNN is obviously better than other model, especially the model trained from TF-IDF vector. 
        This is the other indicators from MLkNN trained from TF-IDF vector.
        <img src='indicator.png'>
        According to this table, there are both micro-average precision and macro-average precision to consider. Let's talk about the difference of both of them first. 
        1. Micro-Average
            A micro average will agregate the all contributions (True Positive, False Positive, etc.) of all class to compute the average metric.
        2. Macro-Average
            A macro average will compute the metric independently for each class and then takes the average.
        In the result, both the micro-average precision and recall are more than the macro-average precision and recall. That means the small label are poorly classified. That's mean if we drop more columns, the accuracy might increase.
        However, I gave some inputs, and the result is incredible!
        <img src='lastone.png'>
<h1>Future Plan</h1>
        If I have more time, I will looking for some virtual machine having more than 1 GPU. So I can do GridSearchCV with various parameter to find the best score that I can make. Also, I will try every possible number of columns(genre) that we can have to makes data more accurate.



<a href = "https://github.com/kimmypracha/movie-genre-classification"> You can see what we have done here! </a>

# NLP-Project-Programming-II

Aspect Based Sentiment Analysis (ABSA) is the task of mining and summarizing opinions from text about specific entities (e.g. a restaurant). Typically, an ABSA system attempts to detect the main aspects that are discussed and estimate the polarity for each of them.
In this setting one approach is to define an inventory (a closed set) of aspects for a domain and then build a system that can identify these aspects in text and make a decision about polarity. For the restaurant domain an aspect inventory has been defined in the context of SemEval conferences; e.g., the inventory contains FOOD#QUALITY, RESTAURANT#GENERAL, RESTAURANT#PRICES etc. 

The goal of this assignment is to build a system that decides the polarity of a given aspect. For this you have to:

1.Register and login to http://metashare.ilsp.gr/. Download this dataset: http://metashare.ilsp.gr:8080/repository/browse/semeval-2016-absa-restaurant-reviews-english-train-data-subtask-1/cd28e738562f11e59e2c842b2b6a04d703f9dae461bb4816a5d4320019407d23/. It is an XML file that contains 350 restaurant reviews split into 2000 sentences. Each sentence has been manually annotated with aspects (“category” attribute) and for each aspect a “polarity” label has been assigned (positive, neutral, negative)  

2.Write a python program (split.py) that is able to read/parse the XML file and split it to 10 parts (35 reviews per part). Each part should be stored in a separate file (part1.xml, part2.xml, … part10.xml)


3.Write a python function (in a train.py) that trains a model and saves it to disk. The function should take as parameter an array that indicates which parts will be used for training. 

  a.	As a ML model do not used k-NN but select another, e.g. Support Vector Machines, Logistic Regression.

  b.	Use a large set of features, e.g. unigrams, bigrams, trigrams, POS tags, bigrams of POS, number of named entities, TF-IDF scores, counts, sentiment lexica. Whatever you think is more appropriate.


4.Write a python function (in a test.py) that loads a saved model and uses it for predicting the polarities for the sentence aspects of a part. A parameter of the function should specify which part will be used.


5.Write an experiments.py that uses the functions of train.py and test.py. The experiments.py should do

  a.	10-fold cross validation. In each iteration 9 parts will be used for training and 1 for testing/evaluation. Estimate accuracy for each of the 10 folds/iterations and calculate an average of them.

  b.	Repeat the experiments of 5.a but use only the 1/3 and 2/3 of the training parts; i.e., 3 parts, 6 parts. Comment the results.


6.Use a feature selection technique and assess if all the features that you have used are important. For example,  if you have 1000 features you can keep the n most important and re-run your experiments (using all the 9 training parts). Report results with various n values.


7.The results of your experiments should be described in a report.docx. Your code should contain comments that explain what you are doing. 

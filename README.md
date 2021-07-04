Fake news detection
==============================

With all the available technology and access to the internet information is easily accessible everywhere. This can also have negative impacts, one of which being the rapid spread of disinformation through fake news.  
<br/>
The aim of this project is to **provide an example of fake news detection** using several machine learning algorithms and a multi layer perceptron neural network.
In my first set of experiments I have used for training a dataset that can be found on [Kaggle](https://www.kaggle.com/clmentbisaillon/fake-and-real-news-dataset). It contains **23 481 fake** and **21 417 true news articles**. The great majority of true news articles have been retrieved from [reuters.com](https://www.reuters.com/). Fake news data has been collected from various unreliable websites that have been labeled as such by [Politifact](https://www.politifact.com/), a website devoted to fact-checking. However, I noticed that this dataset is biased and even if I tried to remove some of the biases I have identified (i.e. removing the word "Reuters" that used to appear in most of the real articles), good and very good scores were achieved by all the algorithms I experimented (~99% F1-scores were obtained by SVC and neural net). 
<br/>
<br/>
This is why I wanted to experiment with a more challenging dataset that can also be retrieved from [Kaggle](https://www.kaggle.com/hassanamin/textdb3). After data cleaning, I obtained a balanced dataset, having around **3150 examples for each class**. SVC proved to be, once again, the best choice for fake news classification task on this dataset, achieving an F1-score of ~93.1%. This is a more reasonable score than the one obtained for the first dataset.  
<br/>
Most of this dataset information lies in the political sphere and is mainly related to 2016 US election.
![True and fake wordclouds](images/fake_true_word_cloud.png)


The project consists in a series of Jupyter notebooks and python scripts structured in the following way:
1. `src/dataset_1/data/initial_exploration.ipynb` (for the first dataset) and
   `src/dataset_2/data/initial_exploration.ipynb` (for the second dataset): explores the dataset in order to obtain valuable insights that will later be used in the data cleaning and training steps
2. `src/dataset_1/data/data_cleaning.ipynb` (for the first dataset) and
   `src/dataset_2/data/data_cleaning.ipynb` (for the second dataset): based on observations obtained in the previous step, the initial data is cleaned and prepared for training.
3. `src/dataset_1/training.ipynb`(for the first dataset) and
   `src/dataset_2/training.ipynb`(for the second dataset): uses the preprocessed data from the step before and feeds it to a series of classification algorithms: logistic regression, multinomial Naive Bayes, random forest, support vector machines and multi-layer perceptron neural net. Classification reports are shown and compared

## Install
Run `pip install -r requirements.txt` to install dependencies.




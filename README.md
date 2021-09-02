# Counterfactual-generation-using-Wachter-paper

This is an implementation of basic CFs generation using Wachter paper. 
The paper uses a basic loss function to generate CFs which may or may not generate explainable CFs. 

The loss function minimizes distance between query and CF as well as also minimizes classification loss of CF to other class

In this notebook we use FashionMNIST dataset to generate CFs. 

First we train a CNN based classifier to classify FashionMNIST dataset, then we use this classifier to generate CF with the help of Wachter loss function.

We try 3 different experiements

1. We have a query data and randomly selected data which we will optimize to be the CF of the query data. In this we minimize distance between query and 
other data along with maximizing distance between classification error of other data to class of initial class of *other data*(i.e. other data should not be in same class as it started with)

2. We have a query data and randomly selected data which we will optimize to be the CF of the query data. In this we minimize distance between query and 
other data along with maximizing distance between classification error of other data to class of initial class of *query data* (i.e. other data should not be in same class as of query data)

3. Here instead of randomly selecting other data and make it to a CF of query data, we initialize the other data with that of query data and in loss function we minimize distance between query
 data and cf vector along with minimizing the classification error of cf vector being classified to other class. 
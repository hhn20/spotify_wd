# Western Digital Internship (July - August 2020)

#### By Harshaa Narayan and Dhruva Narayan
#### Guided by: Hanumanth Mannur
---

## Objective

Handling Model evolution with transfer learning: 
The aim is to build a workflow for handling constantly evolving data and auto retrain/evolve model with the new data and maintain a consistent performance.

## Requirement

Once ML models are trained, they risk becoming obsolete due to changes in the data that they analyse. Data drift could be due to changes in tastes (for example with music) or changes in external conditions.
To keep ML models up to date and as accurate as possible, we need to keep retraining the models with the latest data available. 
This process needs to happen continuously and so we need to constantly monitor the data we receive and decide whether to retrain the model or not. To do this we can use various metrics such as divergence in the distribution of the data. 


## Transfer Learning

Transfer learning is a machine learning method where a model developed for a task is reused as the starting point for a model on a second task.
It is a popular approach in deep learning where pre-trained models are used as the starting point on computer vision and natural language processing tasks. This is very helpful given the vast amount of computation resources and time required to develop neural network models on these problems. 


## Methodology 

For this project we have used the data from <a href= "https://developer.spotify.com/documentation/">Spotify Developer API</a>
We are trying to predict the popularity of songs by taking into account several features such as danceability, artist name.etc.
We felt that this would be a good dataset because:
1. We keep getting new data every year
2. Tastes may change over time, causing model drift

We have created a neural network comprising of 5 layers. We train the neural network on the data from the years 2008 to 2014.
Then we test our model with new incoming data every year. If our prediction is not accurate (i.e having a loss that is higher than a certain threshold), then we retrain our model on that year’s data. We use the concept of transfer learning here. We use the same weights we found from the initial training, in the first three layers of the NN. For the last 2 layers we retrain the model with the weights initialised to the weights in the previous iteration. 
This way our model stays up to date even when there is a drift in the kind of data we receive over time. 

This is the flow of execution that has been implemented by us:

<img src = "/flowchart.png">

Download the "Results and Discussions" word document to see the results

# Western Digital Internship

#### By Harshaa Narayan and Dhruva Narayan (July - August 2020)
#### Guided by: Hanumanth Mannur
---

## Objective

Handling Model evolution with transfer learning: 
The aim is to build a workflow for handling constantly evolving data and auto retrain/evolve model as per the new data and maintain a consistent performance.

## Requirement

Once ML models are trained, they risk becoming obsolete due to changes in the data that they analyse. Changes could be due to changes in tastes (like music) or other factors.
To keep the model up to date and as accurate as possible, we need to retrain the models with the latest data available. 
This process needs to happen continuously. Hence we need to monitor the data that we receive and decide whether we need to retrain the model or not. We can measure the divergence in the data.etc to do this. 


## Transfer Learning

Transfer learning is a machine learning method where a model developed for a task is reused as the starting point for a model on a second task.
It is a popular approach in deep learning where pre-trained models are used as the starting point on computer vision and natural language processing tasks given the vast compute and time resources required to develop neural network models on these problems and from the huge jumps in skill that they provide on related problems.


## Methodology 

For this we have used the data from <a href= "https://developer.spotify.com/documentation/">Spotify Developer API</a>
We are trying to predict the popularity of songs by taking into account several features such as danceability, artist name.etc.
We felt that this would be a good dataset because:
1. We keep getting new data every year
2. Tastes may change over time hence requiring us to retrain our model

We have created a neural network of 5 layers.We train the neural network on the data from the years 2008 to 2014.
Then we test our model with new incoming data every year. If our prediction is not accurate (i.e having a loss that is higher than a certain threshold), then we retrain our model on the new year’s data. We use the concept of transfer learning here. We use the same weights we found from the initial training, in the first three layers of the NN. For the last 2 layers we retrain the model with the weight initialised to the previous weights. 
This way our model stays up to date even when there is a drift in the kind of data we receive over time. 

This is the flow of execution that has been implemented by us:

<img src = "/flowchart.png">

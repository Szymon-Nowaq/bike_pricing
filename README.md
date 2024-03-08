Here is your text with corrections:

This is my first DS project in which I developed a neural network model that can predict the price of used bicycles (road and mountain bikes, separately). I used two datasets found on Kaggle which included data scraped from bike-exchange.com and ebay.com.

Cleaning and preprocessing data: The concatenated dataframe contained 500 columns with valuable data spread between them. It was a bit of a struggle (or playing with pandas) to compress the data to 10 useful categories. Unfortunately, this required removing about 45% of the source data, so finally, I was left with:

2000 records for MTB bikes
2500 records for road bikes
The data was preprocessed in a few ways:

Scaled data - between 0 to 1 (bike groupset, frame material, brake type, suspension type). The closer to 1, the better, for example, 0.1 for Shimano Claris, 1 for Shimano Dura-Ace (the best groupset produced by Shimano).
0/1 data - whether the bike has a feature or is it new or used (the vast majority were used).
Year of production was scaled with QuantileTransformer from sklearn, because of its long-tail distribution.
Finally, we have 4 datasets: MTB, road, and each one one-hot encoded.

Training and results:
The stated goal was to predict the price within $100 of the true value. I used a standard neural network with linear layers and ReLU activation function. Optuna helped me a lot with hyperparameters; I used 2 different strategies:

Accuracy maximization
Loss minimization
Here are the results from the best obtained model:
<photo>

A report from other models can be found here <link>.
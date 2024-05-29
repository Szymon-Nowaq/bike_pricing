# Bike pricing 🚲 💸
#### This is my first DS project in which I developed a used bike pricing neural network model 

I used two datasets found in [this](https://www.kaggle.com/datasets/tysonpo/bike-ads-images-prices-specifications) Kaggle repository which included data scraped from bike-exchange.com and ebay.com advertisments.
## Project Story:
### Cleaning the data 🧹
---
Concated dataframe contained **500** columns with valuable data spreaded inbetween, it was a bit of struggle 
(or playing with 🐼pandas🐼) to compress the data to 10 useful cathegories ✅
Unfortunetly it required removing about 45% of source data, so finally I was left with:
- 2000 records for mtb bikes 🚵
- 2500 record for road bikes 🚴
___
### Data was preprocessed in a few ways: 
- **scaled data** - between 0 to 1 (bike gropset, frame material, brake type, suspension type)
the closer to 1 the better, f.e. 0.1 - shimano claris, 1 - shimano dura ace (the best groupset produced by shimano)
- **0/1 data** - does bike has a feature or is it new or used (vast majority - used)
- **year production** was scaled with **QuantileTransformer** from sklearn, because of its long-tail distribution
  #### Finally we've 4 datasets:
- mtb
- mtb one-hot encoded
- road  
- road one-hot encoded.
___
### Training and results: 📈
The stated goal was to predict the price within **100💲**of the true value.
I used standard neural network with **linear** layers and **ReLu** activation function.
Optuna helped me a lot with hyperparameters, I used 2 diffrent strategies:
- accurancy maximize
- loss minimize
___
### Here are the results from the best obtained model: 📊
It used mtb one hot encoded dataset to train, optuna strategy was to minimize loss.
![best](https://github.com/Szymon-Nowaq/bike_pricing/blob/main/best_models/mtb_one_hot/accurancy_raport_mtb_one_hot.jpg)
![bestplot](https://github.com/Szymon-Nowaq/bike_pricing/blob/main/best_models/mtb_one_hot/accurancy_plot_mtb_one_hot.jpg)
___
### And here are the combined accurancy plots from diffrent datasets: 
![combined](https://github.com/Szymon-Nowaq/bike_pricing/blob/main/best_models/accurancy_general_raport.jpg)
___
Raports from other models can be found [there](https://github.com/Szymon-Nowaq/bike_pricing/tree/main/best_models)


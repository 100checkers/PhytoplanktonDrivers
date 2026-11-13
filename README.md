# PhytoplanktonDrivers
Exploring Phytoplankton Drivers with ML


### About This Project:
This project was part of what I worked on for my summer undergraduate research project. It explores the use of machine learning and deep learning to forecast cell counts of phytoplankton (specifically Dinophysis) and their potential application in monitoring for harmful algal blooms (HABS). 

### Objective:
Phytoplankton are a class of underwater plant-like organisms that serve as a food source for many marine life. Once phytoplankton reach an overgrowth that changes normal water conditions, it creates a phenomenon known as a harmful algae bloom (HAB) that wreaks havoc on ecosystems. Since every species of phytoplankton will behave differently under the same conditions and the occurrence of a HAB depends on a range of factors with complex relations, the exact cause isn’t concrete. Therefore, it is increasingly important to monitor water for elevations in phytoplankton growth activity and test different modeling approaches such as the Transformer (a neural network-based model invented by Google researchers in 2017). I evaluated the Transformer models against the performance of a Random Forest model to test whether adapting to newer technologies is beneficial when it comes to environmental forecasting.

### Methodology:
The data was cleaned using a Python script to remove any variables that exhibited strong multicollinearity before saving it to a dropbox file.
The data was further cleaned by eliminating variables that had greater than 90% of values missing. 
I explored the dataset using descriptive statistics and time series plots for different species of phytoplankton. Dinophysis was chosen as the target variable because it's a toxic phytoplankton that leads to HABS (harmful algal blooms).

I then created time-series features to forecast at 1-day, 1-week, and 2-weeks. The first type of model I looked at was the Random Forest model, which was my baseline model because they do well at handling large datasets, reduce overfitting, and are reliable. The second model I created used the Amazon Chronos Transformer. The third type of model I made was the Keras Time-Series Transformer. 

The MAE and RMSE scored better for the Transformer models and that could be caused by low cell counts dominating the time series and skew these metrics. 

### Tools Used: 
  - Pandas
  - NumPy
  - Matplotlib
  - Keras Time-Series Transformer
  - Amazon Chronos Transformer
  - scikit-learn library for Random Forest models.

### Results:
The experiments revealed differences in how the models responded to dataset size and feature selection. The Random Forest models initially showed the best performance. However, an issue I ran into was that the Random Forest did better with a larger number of input variables and the Transformer models did worse with more input variables. I needed to keep the clean dataset with about ~50 variables max for both the Random Forest and the Transformer models to have consistency in my methodology. 

Both the Random Forest and the Transformer appeared to struggle in the second-half of the data. I assume this was because it was harder for the models to predict further in time. This could also be due to the way that the models were trained (80/20 split) because when I attempted a time-series split, I got different results. This is something that could be explored further but wasn't due to time constraints. 


### How to run:
I have added all the necessary libraries and packages to the beginning of each experiment to maintain a modular approach to coding this. If you would like to look at the Random Forest models start at the top and work your way down. Otherwise, you can skip to the Chronos Transformer or Keras Transformer sections and you will find information in the comments that explain how to run the code step-by-step.

Please note that access to the dataset cannot be granted at this time, but you are welcome to try the code with your own data.

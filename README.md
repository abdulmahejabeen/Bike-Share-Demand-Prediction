# Bike-Share-Demand-Prediction-and-Rebalancing
The project aims to address the challenges arising from rapid growth of metropolitan areas and the increasing need for bike-sharing programs. The project objective is to predict the demand for bike share using a variety of machine learning regression models and also to provide an intelligent infrastructure for bike stations that leverages reinforcement learning to expedite the rebalancing procedure.

## Dataset Description
The datasets consists of hourly bike rentals count on a daily basis along with aspects of weather information like temperature, humidity, wind speed, visibility, dewpoint, solar radiation, snowfall, and rainfall, and information about the season, holiday, and functioning day which are the features and the target variable is the number of bikes rented per hour and date information.

DataSources Link: [Bay Wheels data](https://www.lyft.com/bikes/bay-wheels/system-data), [Weather data](https://meteostat.net/en/)

## Community Contribution
The rise in on-road vehicles and traffic congestion underscores the need for reliable transportation options. Through the utilization of bike-sharing systems, our goal is to alleviate traffic congestion, decrease Greenhouse Gas Emissions, and advocate for a healthier and eco-friendly mode of transportation.

## Data Preprocessing
- Checked the multicollinearity across all independent variables and dropped the variables which has a variable inflation factor (VIF) greater than five.
- Label encoding done to transform the categorical variables. 
- Transformed the target variable with square root and logarithmic transformations for Linear regression models.
- scaled the features for normalization.

## Proposed models 
This Project aims to predict hourly bike share demand at a particular location on a particular day using the machine learning models.

Linear Regression Models: Lasso, Ridge, Polynomial, Elastic

Tree-Based Models: Decision Tree, Random Forest, Gradient Boosting

## Rebalancing approach - Reinforcement model

As an extension to this project, attempt to create an intelligent bike station environment that can do the rebalancing activity without manual interruption, using reinforcement learning.

![image](https://github.com/abdulmahejabeen/Bike-Share-Demand-Prediction-and-Rebalancing/assets/56336879/284bc1e6-bcda-4c67-b4f5-4746756bf8b8)

The reinforcement model which can implement the rebalancing strategy without much manual interruption; it is implemented using three modules:
-  Environment: Analogous to a bike station that can simulate the bike stock either linearly or randomly based on input.
-  Agent: Similar to the bike station operator, this sends feedback about the bike inventory, rewards or penalties assigned.
-  Trainer: The trainer module is responsible for end-to-end processing based on input.

Until a terminating state, the agent moves from one state to the next through actions performed. A reward or punishment results from the behavior in a particular state.

The reward and punishment structure are as follows:

#### Reward:
- -30 if the hourly bike stock falls outside the range [0, 100].
- +20 if bike stock is in the range [0, 100] at 23 hours; otherwise, -20
- -0.5 times the number of bikes eliminated every hour.

#### Punishment:
- -30 for falling outside the acceptable stock range.








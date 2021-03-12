# King County Housing Project
Author: Jaclyn Dwyer
<img src = 'https://images.squarespace-cdn.com/content/v1/581c0035f7e0ab2f6c8aeb13/1519535690981-O24DETE6W491IWAZCU4S/ke17ZwdGBToddI8pDm48kO4dmugY0zpo_YzqU442LIIUqsxRUqqbr1mOJYKfIPR7LoDQ9mXPOjoJoqy81S2I8N_N4V1vUb5AoIIIbLZhVYwL8IeDg6_3B-BRuF4nNrNcQkVuAT7tdErd0wQFEGFSnMRCJLRqlrzW4JrPjNfKzxyb6PKCr8WQFbT35T18ZG_IuVd3SpPhHqfBxnqgzYFgXQ/ganapathy-kumar-113604.jpg'>

## Overview
This project examines data about home sales in the Seattle, Washington area to understand what factors about a home impact price. The goal of the project is to create a model that best predicts housing prices in King County. There are two final notebooks included in the repro. The model notebook implements the process of creating a model and is talked about here, while the predict notebook uses the model created to make predictions on housing prices.

## Data Prep and Exploratory Data Analysis
To determine relationships between the features and the target variable (price), the data is prepped and cleaned by looking for missing values, capping extreme values, and more. The data relationships are further explored with data visualizations, statistical tests, and more. 

<img width="908" alt="Screen Shot 2021-03-12 at 8 55 21 AM" src="https://user-images.githubusercontent.com/73671207/110949572-bee00580-8310-11eb-9525-57d083079727.png">

Some findings include that houses on the waterfront, houses with higher grades, and houses in certain zip codes have an impact on price. 

<img width="782" alt="Screen Shot 2021-03-12 at 9 01 25 AM" src="https://user-images.githubusercontent.com/73671207/110950349-bb00b300-8311-11eb-8582-f638704afd65.png">

Features not originially included in the dataset that are thought to impact housing prices are generated using information provided in the data set. Some engineered features include yard size of the house, how many years since the house has been built or renovated, and whether the house is sold during peak months or non peak months. 

<img width="690" alt="Screen Shot 2021-03-12 at 9 06 21 AM" src="https://user-images.githubusercontent.com/73671207/110950783-44b08080-8312-11eb-9ca2-91d14f1b63cf.png">

## Inference OLS Model 
An OLS model is generated from the prepped dataset to draw inferences on which features have more impact on price. By looking at the coefficients from this model, waterfront, certain zip codes, and bathrooms are among some of the things that can positively impact the price of a house while bedrooms and floors are some of things that can negatively impact the price. 

## Prediction Model
A more complex prediction model is genereated by using the information gathered above about which features impact price. Polynomials and interactions are generated to account for complicated relationships in the data for features deemed important. Some examples include how waterfront and square footage of living or zipcode interact, how grade and zipcode interact, and more. 

### Evaluate Model
Model assumptions are checked using graphs to evaluate the model and better understand how to improve the model. Findings include that the residuals from the model are not homoscedastic and not normally distributed. To try and fix the normality issue and improve the prediction model, a non-linear transformation of the data is done with log transformation. The continuous features price, square footage of living, square footage of lot, square footage of living 15 and square footage of lot 15 are selected to log to try and improve normality. Below is a graph representing the data after the log transformation is performed.

<img width="648" alt="Screen Shot 2021-03-12 at 9 21 04 AM" src="https://user-images.githubusercontent.com/73671207/110952551-5eeb5e00-8314-11eb-88a9-e688c7ab847c.png">

With this transformation the root mean square error of the model drops from 142,967 to 125,785. Therefore, the log transformation helped to improve the model as the root mean square error is less. 

### Feature Selection
Finally, some features selections are performed to select relevant features in the model to potentially create a more accurate model. After using the recursive feature elimation method as well as an F-test, the recursive feature model gives us the lowest rmse indicating it is the best model for predicting housing prices.  

## Next Steps
Next steps include adding more relevant information to the data set which could help the accuracy of the model including information regarding crime rate, distances to popular locations, properties with pools and more. 

## Repository Structure
 - data
 - images
 - notebooks
 - Effects on King County Housing Prices.pdf
 - Final_King_County_Housing_Model.ipynb
 - Final_King_County_Predict_Housing.ipynb
 - READ.me
 - model.pickle
 - other_info.pickle

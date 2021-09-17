![Header Image](https://github.com/raylinsoriano/Project_3_Classification/blob/main/Images/chicago-city-lights-at-night.jpg)
Source: [Burst](https://burst.shopify.com/photos/chicago-city-lights-at-night?q=chicago)

# Classifying Risk of Injury for Traffic Crashes in the City of Chicago

## September 2021

Lorela Blaka, Allison Gao, Raylin Soriano


## General Overview and Business Understanding
This analysis used data on car crashes that happened in 2019 in Chicago Illinois to predict different levels of injury with respect to a myriad of factors such as airbag deployment and road defect. Specifically, we split level of injury into mild, medium, and severe, making our target variable a ternary class. 
The purpose of the analysis is to provide recommendations to Chicago's Department of Transportation(DOT) so that they can enact interventions to reduce or prevent injury. Our analysis shows that x. Additionally, we found that x. Department of Transportation can use this project’s findings to develope better policies to increase safety for drivers and pedestrians. 

## Data 

###### Data Source
This project utilized three datasets; one dataset contains information on the crash, a second piece contains information on people involved in the crash and the third dataset contains information on vehicles involved in the crash. Collectively, these three datasets included information on weather condition, road condition, levels of injury, damage cost, among many other related factors. Each row from the three tables has an unique crash ID assigned to it at the scene of the crash, allowing us to merge the three datasets. 

###### Data Preparation
We cleaned the dataset by eliminating columns not needed for analysis, dropping missing values for certain columns, replacing some columns' missing rows with mean or mode, and reformatting certain data types. At the end of the cleaning process, the data contained approximately 550,000 observations for analysis. 

## Data Analysis 

This project used different machine learning algorithms to generate different models in order to predict different levels of injury. In particular, we used multinomial logistic regression, random forest classification, and XGBoost. To generate our target variable, we took a column that reported on different levels of injury and grouped them into mild, medium, and severe. We then split the data into training and testing sets so that we can train our data and test it on completely unseen data in order to understand how well our models are at predicting our target variable. In particular, 30% of the dataset was allocated for training. The distribution of our target variable is imbalanced- approximately 87% of the data is mild, 11% is medium and 2% is severe. To address class imbalance, we used Synthetic Minority Oversampling Technique (SMOTE) to generate synthetic data from the  existing minority cases to purposefully oversample the minority dataset. Additionally, we converted categorical features into binary variables for analysis. 

To help select meaningful features for analysis, we used decision tree to help us choose important features for consideration. Then for each machine learning algorithms we used the grid search method provided by Scikit-learn's GridSearchCV to determine candidates from a grid of parameter values specified with the param_grid parameter. Once the "best" parameters are determined, we ran each model again with these parameters. We assessed each model's performance using accuracy score and macro precision score. 

## Results 

We determined that the best model for predicting our target variable is Random Forest, which has the highest macro precision score. We chose precision over recall as a metric because we believe for the purpose of this analysis the cost of misidentifying a true positive (recall) is not costly. 

![Header Image](https://github.com/raylinsoriano/Project_3_Classification/blob/main/Images/Screen%20Shot%202021-09-16%20at%209.32.22%20PM.png)

From our model, we higlighted the following three features as important factors in predicting different levels of injury. 


### The percent of accidents for most severe injuries was highest when the road was defected

![Header Image](x)



### The accident count for most severe injuries was highest when the airbag was not deployed


![Header Image](x)


### The accident likelihood is highest in areas of Northern Chicago 

![Header Image](x)




## Conclusion and Recommendations 

Results from this project’s analysis suggested the following three recommendations for DOT to consider:

1. Fix road infrastructure to reduce severe level of injury 

2. Investigate airbag safety issues 

3. Implement safety measures in high accident zones (i.e. address congestion issue, implement more safety signs) 


## Next Steps

1.Increase dataset to include greater number of years 

2.Further modeling and hyperparameter tuning. For example, compare difference between rural and urban Chicago 



## Additional Information

See the full analysis in the [Jupyter Notebook](x) or review [this presentation](x).

For additional info, contact

Lorela Blaka: lblaka@gmail.com

Allison Gao: allison.gao@nyu.edu

Raylin Soriano: sorianoraylin@gmail.com

## Project Structure 

```## Project Structure

├── README.md
├── data      <-- CSV file used in analyses
├── images    <-- visualizations generated from working notebooks and external images
├── Individuals Notebooks       <--- Directory for individual workspaces
│   ├── allison
│   ├── raylin
│   ├── lorela
│   
├── Final Notebook.ipynb    <-- Jupyter Notebook containing codes detailing project's analysis 
├── Non-technical Presentation.pdf   <-- non-technical presentation slides
└── .gitignore


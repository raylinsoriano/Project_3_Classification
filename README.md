![Header Image](https://github.com/raylinsoriano/Project_3_Classification/blob/main/Images/chicago-city-lights-at-night.jpg)
Source: [Burst](https://burst.shopify.com/photos/chicago-city-lights-at-night?q=chicago)

# Classifying Risk of Injury for Traffic Crashes in the City of Chicago

## September 2021

Lorela Blaka, Allison Gao, Raylin Soriano

## Business Understanding
The purpose of the analysis is to provide recommendations to Chicago's Department of Transportation(DOT) so that they can enact interventions to reduce or prevent injury. Department of Transportation can use this project’s findings to develope better policies to increase safety for drivers and pedestrians. This analysis used data on car crashes that happened in 2019 in Chicago Illinois to predict different levels of injury with respect to a myriad of factors such as airbag deployment and road defect. Specifically, we split level of injury into mild, medium, and severe, making our target variable a ternary class. 

You can find these datasets on the city of Chicago website:

https://data.cityofchicago.org/Transportation/Traffic-Crashes-Vehicles/68nd-jvt3
https://data.cityofchicago.org/Transportation/Traffic-Crashes-People/u6pd-qa9d
https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if


## Data 

##### Data Source
This project utilized 3 datasets: <br>-First dataset contains information on the crash <br>-Second piece contains information on people involved in the crash  <br>-Third dataset contains information on vehicles involved in the crash <br><br>Collectively, these three datasets included information on weather condition, road condition, levels of injury, damage cost, among many other related factors. Each row from the three tables has an unique crash ID assigned to it at the scene of the crash, allowing us to merge the three datasets. 

##### Data Preparation
We cleaned the dataset by eliminating columns not needed for analysis, dropping missing values for certain columns, replacing some columns' missing rows with mean or mode, and reformatting certain data types. At the end of the cleaning process, the data contained approximately 550,000 observations for analysis. 

## Data Analysis 

This project used different machine learning algorithms to generate different models in order to predict different levels of injury. In particular, we used:<br>
* Multinomial Logistic Regression 
* Random Forest Classification 
* XGBoost <br>

To generate our target variable, we took a column that reported on different levels of injury and grouped them into mild, medium, and severe. Then conducted a train test split on training so that we can train our data and test it on completely unseen data in order to understand how well our models are at predicting our target variable. The distribution of our target variable is imbalanced- approximately 87% of the data is mild, 11% is medium and 2% is severe. To address class imbalance, we used Synthetic Minority Oversampling Technique (SMOTE) to generate synthetic data from the existing minority cases to purposefully oversample the minority dataset. Additionally, we converted categorical features into binary variables for analysis. 
<br><br>
To help select meaningful features for analysis, we used decision tree to help us choose important features for consideration. Then for each machine learning algorithms we used the grid search method provided by Scikit-learn's GridSearchCV to determine candidates from a grid of parameter values specified with the param_grid parameter. Once the "best" parameters are determined, we ran each model again with these parameters. We assessed each model's performance using accuracy score and macro precision score. 

## Results 

We determined that the best model for predicting our target variable is XGBoost, which has the highest macro precision score. We chose precision over recall as a metric because we believe for the purpose of this analysis the cost of misidentifying a true positive (recall) is not costly. 

![Header Image](https://github.com/raylinsoriano/Project_3_Classification/blob/main/Images/Screen%20Shot%202021-09-16%20at%209.32.22%20PM.png)

#### XGBoost Confusion Maxtrix

* XBBoost confusion matrix that our model is good at predictiong level 2 (Most Severe) injuries on training data.

#### From our graphs below, we higlighted the following three features as important factors in predicting different levels of injury. 

* The percent of accidents for most severe injuries was highest when the road was defected
<br>
<img width="567" alt="Screen Shot 2021-09-17 at 11 58 00 AM" src="https://user-images.githubusercontent.com/40476299/133818655-a78bf3ec-99b1-4de1-bd4e-5a626ef1ccb4.png">



* The accident count for most severe injuries was highest when the airbag was not deployed

<img width="586" alt="Screen Shot 2021-09-17 at 11 58 09 AM" src="https://user-images.githubusercontent.com/40476299/133818753-57db9d6c-6e81-43a1-93a3-bbc1fd01717b.png">


* The accident likelihood is highest in areas of Northern Chicago 

<img width="604" alt="Screen Shot 2021-09-17 at 11 58 27 AM" src="https://user-images.githubusercontent.com/40476299/133818876-a28d61c6-3703-460d-8cf2-37baece2f41a.png">





## Conclusion and Recommendations 

Results from this project’s analysis suggested the following three recommendations for DOT to consider:

1. Fix road infrastructure to reduce severe level of injury 

2. Investigate airbag safety issues 

3. Implement safety measures in high accident zones (i.e. address congestion issue, implement more safety signs) 


## Next Steps

1. Increase dataset to include greater number of years 

2. Further modeling and hyperparameter tuning. For example, compare difference between rural and urban Chicago 



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


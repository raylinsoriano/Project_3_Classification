![Header Image](https://github.com/raylinsoriano/Project_3_Classification/blob/main/Images/chicago-city-lights-at-night.jpg)
Source: [Burst](https://burst.shopify.com/photos/chicago-city-lights-at-night?q=chicago)

# Classifying Risk of Injury for Traffic Crashes in the City of Chicago

## September 2021

Lorela Blaka, Allison Gao, Raylin Soriano


## General Overview and Business Understanding
This analysis used data on car crashes that happened in 2019 in Chicago Illinois to predict different levels of severity in injury with respect to a myriad of factors such as airbag deployment and road defect. The purpose of the analysis is to provide recommendations for Chicago's Department of Transportation so that they can enact interventions to reduce or prevent injury.Our analysis shows that x. Additionally, we found that x. Department of Transportation can use this project’s findings to develope better policies to increase safety for drivers and pedestriany. 

## Data 

###### Data Source
This project utilized three datasets; one dataset contains information on the crash, a second piece contains information on people involved in the crash and the third dataset contains information on vehicles involved in the crash. Collectively, these three datasets included information on weather condition, road condition, levels of injury, damage cost, among many other related factors. 

###### Data Preparation
We cleaned the dataset by dropping missing values, reformatting certain data types. We also created additional columns that are needed for analysis. This included interaction terms where we deemed that certain variables are better interpreted with another factor. For example, we created an interaction term for building quality(as measured by grade) with square footage of the house. Additionally, we logged certain variables in order to normalize them because they are not normally distributed. At the end of the cleaning process, the data contained approximately 550,000 observations for analysis. 

## Data Analysis 

This project used different machine learning algorithm to generate different models to predict different levels of injury. We split the data into training and testing sets so that we can train our data and test it on completely unseen data in order to understand how well our models are at predicting our response variable. In particular, 30% of the dataset was allocated for training. We iterated our model multiple times by changing the features to assess accuracy score and precision macro score, two values we used to assess our model's accuracy. 


## Results 

Our cleaned and filtered dataset had an average home price of $540,168. Furthermore, our best model contained 23 variables using approximately 15,000 observations. It explained about 78% of the variation we see in home sale price, our response variable. Additionally, our model saw an average error of $180,475 on our training data and an average error of $185,615 on our unseen data. 

The following three operable factors are statistically significant. We defined operable to mean features home flippers can operate on or fix. 

1. Square footage of the entire house
2. Building quality as measured by building grade ( 1 to 13)
3. Number of bathrooms

The following three non-operable factors are statistically significant. We defined non-operable to mean features home flippers cannot operate on or fix. However, home flippers can still exert decision over these factors. 

1. If a house is facing the waterfront 
2. Age of the house
3. House living space for the nearest 15 neighbors


### Change in feature and its relationship to change in home price 

![Header Image](x)
We highlighted what happens when we increase a feature by one unit or one percentage point. For example, we see that among the three factors, one additional increase in bathroom generated the greatest change in home sale price compared to the other two factors. 


### Change in house square footage and its relationship to change in home price 

![Header Image](x)
Sale price increases by ~0.75% for every 1% increase in the house's square footage


### Change in house square footage and its relationship to change in home price for different quality houses

![Header Image](x)
For a house with an average grade and at an average price ($540,168) if you increase the square footage of the entire living space by 1%, it will increase the sale price by  ~$5,700. 


### Change in number of bathroom and its relationship to change in home price

![Header Image](https://github.com/ericdnbn/Phase_2_Project/blob/main/Images/Image%204-bathroom.png)
For a house at the average price, one additional bathroom will increase the home sale price by  ~$25,000. 



## Conclusion and Recommendations 

Results from this project’s analysis suggested the following three recommendations for home flippers to consider:

1. Start with location. We found that home sale prices do differ whether or not a house is facing a waterfront. Additionally, such a difference is also statistically significant between houses in the northern and southern part of the county. Even at the neighborhood level, the square footage of interior housing living space for the nearest 15 neighbors has an impact on house price. These three factors are helpful to consider as home flippers start the decision process. 

2. After a location is selected, we recommend that home flippers consider these three features that are operable as an effort to increase home price. 

    A. We found that increasing the house size is associated with an increase in house price. For example, a house that is at $540,168, if you increase the square footage of the entire living space by 1%, it will increase home sale price by  ~$5,700. 
    
    B. Additionally, we recognized that many variables are interconnected and that many features need to be analyzed in the context with other factors. In particular, we believe that house size's relationship with home price also depends on the house's quality as measured by the county's grading system. That a higher grade is associated with higher home price. Therefore, we recommend that home flippers take into consideration building quality. Details of the grading scale can be found here on [this website](https://info.kingcounty.gov/assessor/esales/Glossary.aspx?type=r). 
    
    C. Lastly, we recognize the various possibilities involved in flipping a house for profit and recommend adding bathrooms to increase sale price. For a house with an average price, one additional bathroom will increase the home sale price by  ~$25,000. 


## Next Steps

1. Calculate ratios of relevant interaction terms to put numbers into greater perspective. For example, bedroom to bathroom ratio or house size to lot size ratio. 

2. Find real estate data that includes other relevant information impacting house price. For example, kitchens and the presence of a pool. 

3. Obtain renovation cost in King County by house size for budget analysis 


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
│   ├── eric
│   
│   
├── Final Notebook.ipynb    <-- Jupyter Notebook containing codes detailing project's analysis 
├── Non-technical Presentation.pdf   <-- non-technical presentation slides
└── .gitignore


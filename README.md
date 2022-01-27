# Gems-Price-Prediction
Gem Stones co ltd is a cubic zirconia manufacturer (which is an inexpensive diamond alternative with many of the same qualities as a diamond). Using the dataset containing the prices and other attributes of almost 27,000 cubic zirconia, predicted the price for the stone so that company  can distinguish between higher profitable stones and lower profitable stones so as to have better profit share.

## EDA
   Dataset has 10 variables and 26967 instances.
   Six columns are float type, two columns are int type and three columns are object type. 
   From the  data, it is evident that no null values are present in the data. 
   
   -Using the describe() function in Python, a summary of all the parameters can be obtained.
   -Using the .duplicated() function, it is found that the given dataset has no duplicate values.
   -Using the .shape() function, we get to know that (26967, 11) rows and columns are present in the data respectively.
   -Using the .isnull.sum() function, it can be concluded that only the column ‘depth’ has total 697 null values and the rest of the cells don’t have any null values.
   -Using the .nuinque() function, we found the number of unique values in each column of the dataset.

   We have both categorical and continuous data. For categorical data we have cut, colour and clarity
   For continuous data we have carat, depth, table, x. y, z and price.
   Price will be target variable.
   
 Univariate Analysis using dist plot and box plot
    The distribution of data in Carat seems to positively skewed, as there are multiple peaks points in the distribution there could multimode and the box plot of carat seems to have large number of outliers. In the range of 0 to 1 where majority of data lies. 
    The distribution of Depth seems to be normal distribution. The depth ranges from 55 to 65 and the box plot of the depth distribution holds many outliers.
    The distribution of Table also seems to be positively skewed. The box plot of table has outliers. The data distribution where there is maximum distribution is between 55 to 65. 
    The distribution of x (Length of the cubic zirconia in mm.) is positively skewed. The box plot of the data consists of many outliers. The distribution rages from 4 to 8.
    The distribution of Y (Width of the cubic zirconia in mm.) is positively skewed. The box plot also consists of outliers. The reason for skewness might be due to the specific shape in which the diamonds are made. Due to this, the availability of sizes might be less in the market.
    The distribution of z (Height of the cubic zirconia in mm.) is also positively skewed. The box plot also consists of outliers. 
    The price seems to be positively skewed. The box plot of price shows many outliers and the distribution ranges from 300 to 19000.
    
    
 Multivariate analysis using heatmap
    The heatmap shows quite a few strong positive correlations between the fields like carat and price as well as carat and x, y, z. This shows the multicollinearity of the data.
    
 Database has Null values in depth. Since depth is a continuous variable, mean or median imputation can be done. 
 The percentage of Null values is calculated to be less than 5%, thus these can be dropped. After median imputation, we don’t have any null values in the dataset.
 
 The x, y, z columns are the dimensions of a diamond so they won’t be necessary to consider while modelling. 
 Since very less rows have 0, we can drop these rows as don’t have any meaning in model building.
 
 Outliers are treated and the data is ready for modelling.
 
 ## Linear Regression
 
  Linear regression model do not take categorical values and so we have encoded categorical values to integer for better results - dummie variables.
  We dropped the column ‘unnamed’ due to it’s redundant nature.
  
  We split the data into training and testing and ran the regression model.
  Calculated the Model score and RSME values on both training and testing data.
  
  We still find we have multi collinearity in the dataset. To drop these values to Lower level we can drop more columns after doing stats model.
   From stats model we can understand the features that do not contribute to the Model can be removed. Those features after that the VIF Values will be reduced. 
   Ideal value of VIF is less than 5%.

### ANALYSIS

    We had a business problem to predict the price of the stone and provide insights for the company on the profits on different prize slots. 
    From the EDA analysis we could understand the cut, ideal cut had number profits to the company. The colours H, I, J have bought profits for the company. 
    In clarity if we could see there were no flawless stones and they were no profits coming from l1, l2, l3 stones. 
    The ideal, premium and very good types of cut were bringing profits where as fair and good are not bringing profits. 
    The predictions were able to capture 95% variations in the price and it is explained by the predictors in the training set. 
    Using stats model if we could run the model again we can have P values and coefficients which will give us better understanding of the relationship, so that values more 0.05 we can drop those variables and re run the model again for better results. 
    For better accuracy dropping depth column in iteration for better results.




   

🌟 Thrilled to Share Our Success in the Sberbank Kaggle Competition! 🏆

TL;DR: We clinched a top 5 spot with a private score of 0.31051! 
 
🔍 Exploring the Data Landscape: Over the past two weeks, my partners and I have been competing  against other student groups in the Sberbank Kaggle Competition as part of our Machine Learning course. With datasets spanning from August 2011 to May 2016, alongside macroeconomic insights for Russia, we tried our best to predict property sale prices.

🛠️ Building a Strong Foundation: We began by building baseline models (RF and XGBoost) as per our lecturer's instructions. Then we conducted a literature review to get a better understanding of the problem  of reading  Kagglers' notebooks related to the competition.

🧹 Ensuring Data Integrity: We figured that data integrity is necessary for this task so we cleaned interior features (Features representing the apartment), ensuring correctness and validity using domain knowledge and other people’s approach. From dropping columns with significant missing values to leveraging innovative imputation techniques, we left no stone unturned in preparing our dataset.

🧹 Data Cleaning: We dropped columns with large amounts of missing values that have a low correlation with the dependent variable (the price) and also used imputation methods and sophisticated methods we developed on our own (such as filling kitchen sq using the average ratio of kitch sq / life sq for each sub-area).

💡 Innovative Feature Engineering: Inspired by others' work and driven by our own insights, we created features to enhance our model learning.

📊 Insights Through EDA: Exploratory Data Analysis (EDA) was our guiding light. We tried to learn more about the price distribution among different product types (owner-occupier apartments and apartments for investment) and also analyzed the sparsity of count columns and price behavior among different categories (such as build year) 

🌍 Macro Dataset Analysis: We analyzed inflation-related trends and gained critical insights into price behavior such as prices decrease between 2015 and 2016 which was the years we were tested on.

🔢 Crafting Encoding Strategies: The main part here is the way we encoded the sub-area. From reading other people's insights on Kaggle we figured that the price per square meter is strongly related to the sub-area so we decided to encode the sub-area as the following:
avg price sq_(sub-area)*(n/(n+m))+avg price sq*( 1- n/(n+m))
n-counts of a sub-area,m-parameter
This way we could model the relation of the sub-area with the price without overfitting.


🧮 Correlation Analysis & PCA: Since our feature space is large we used correlation analysis to figure out if there was redundancy in our data. After figuring there was highly correlated features In our data we decided to use PCA to reduce the dimensionality of our feature space while still preserving 95% of the variance.

🎯 Model Training & Tuning: We decided to build separate models for each product type as the price distribution was too different and we used Bayesian optimization as our hyperparameter tuning algorithm. In the end, we compared the performance of both XGBoost and RF  in each product type (we selected XGBOOST as it gave us better results). 


🚀 Model Enhancement: We analyzed the results of our XGBOOST models  to better understand them. We understood that the data related to  OwnerOcuppier properties is easier to model which led us to wisely choose hyperparameters for each model without using any tuning algorithm. We also came up with an idea to ensemble XGBOOST models for each product type and ended up having 3 models for OwnerOcuppier and 5 models for Investment. After getting the predictions for each model we calculated the median of the predictions and multiplied it by a “magic number” to normalize our prices as we understood that we might predict higher than the actual prices.

I hope you find our work fascinating!


 

## Credit Risk Analysis with Machine Learning
### Predicting the risk of client default using XGBoost, LightGBM and CatBoost

- Credit risk is associated with the possibility of a client failing to meet contractual obligations, such as mortgages, credit card debts, and other types of loans.

- Minimizing the risk of default is a major concern for financial institutions. For this reason, commercial and investment banks, venture capital funds, asset management companies and insurance firms, to name a few, are increasingly relying on technology to predict which clients are more prone to stop honoring their debts.

- Machine Learning models have been helping these companies to improve the accuracy of their credit risk analysis, providing a scientific method to identify potential debtors in advance.

### About the Data
Nubank is a Brazilian digital bank and one of the largest Fintechs in Latin America. It is known to be a data-driven company, taking advantage of technology to make decisions and improve services.

- Dataset Link: http://dl.dropboxusercontent.com/s/xn2a4kzf0zer0xu/acquisition_train.csv?dl=0

### Data Analysis

We are working with a data set containing 43 features for 45,000 clients. target_default is a True/False feature and is the target variable we are trying to predict. After exploring the data set, we found that some features had outliers and missing values. 

- **check Notebook:** https://github.com/thabresh-s/Credit-Risk-Analysis/blob/main/Credit_Risk_Analysis.ipynb

### Machine Learning Models
We are experimenting with the following 3 gradient boosting algorithms to determine which one yields better results:

1. XGBoost
2. LightGBM
3. CatBoost

### Results

- The main objective of this article was to build machine learning algorithms that would be able to identify potential defaulters and therefore reduce company loss. The best model possible would be the one that could minimize false negatives, identifying all defaulters among the client base, while also minimizing false positives, preventing clients to be wrongly classified as defaulters.

- Meeting these requirements can be quite tricky as there is a tradeoff between precision and recall, meaning that increasing the value of one of these metrics often decreases the value of the other. Considering the importance of minimizing company loss, we decided to give more emphasis on reducing false positives, searching for the best hyperparameters that could increase the recall rate.

- Among the three Gradient Boosting Algorithms tested, XGBoost yielded the best results, with a recall rate of 81%, although it delivered an undesired 56% of false positives. On the other hand, LightGBM and CatBoost delivered a better count of false positives, with 38% and 33% respectively, but their false negatives were substantially higher than that of XGBoost, resulting in a weaker recall rate.


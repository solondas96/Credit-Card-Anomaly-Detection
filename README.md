# Credit-Card-Anomaly-Detection

Before we begin with our analysis, let's understand a bit more about the dataset that is provided to us. The dataset that we have can be downloaded link at https://drive.google.com/file/d/1ISpmXkavPTRqE1Jq716P4nGO5hiSI_bB/view?usp=sharing. The given dataset contains information about transactions that were made using credit cards in the month of September, 2013. The transaction data is captured over a duration of 2 days. We have 492 cases of fraudulent transactions out of a total number of 284807 number of transactions recorded during those two days.

The dataset as such is severely imbalanced with the percentage of fraud transactions being 0.172% of the total data. The dataset contains only transformed numerical features which are a result of a PCA transormation. The original data is not provided to us due to security reasons and to protect the identity of the customers.

Having said that, there are two features which are not transformed using PCA - 'Time' and 'Amount'. These features are given as it is. The 'Time' feature basically says how much time for each transaction has elapsed since the first transaction in the dataset has taken place. The 'Amount' feature gives us information about the transaction amount for each of the transactions. The fraudulent transactions are denoted by class label 1 and the non fraudulent transactions are denoted by class label 0.

What is the business problem that we are trying to solve?
Credit card fraud refers to a wide range of activities which includes theft of money using either credit cards or debit cards. The theft can be either online or ofline. An ofline theft generally involves withdrawing money from an ATM machine physically using a stolen credit card. An online theft involves any online transaction using the card without the prior consent of the owner. Both as a customer and as a bank, fraudulent credit card transactions can give you nightmares! From a bank's point of view, it's very essential to identify whether a transaction is fraudulent or not because they don't want to lose money or don't want to lose the faith that there customer has entrusted upon them. In such a scenario it becomes a necessity to build a robust system which can be used to determined fraudulent transactions.

While designing the system we should keep in mind that the cost of misclassification of a fraudulent transaction is very high. We don't to end up with a system which might classify a fradulent transaction as a non-fradulent one. Such a system in machine learning is also called a high recall system. It's important for the bank to know which of the transactions are fraud, at the same time it is important to understand which of the transactions are not fraud.

What are the real world business constraints and what metrics we will use to evaluate our model?
The dataset that we have is a real world dataset which is severely imbalanced. This is expected because if you imagine, the number of valid transactions has to be much much greater than the number of fraud transactions in the world, or else everyone would have been bankrupt by now! Due to the severely imbalanced dataset building the best Machine Learning models will be a challenge. But this is a constraint we have to deal with. Since the dataset is imbalanced we will use roc-auc as our key metric.

Another important factor we must keep in mind is the cost of making an incorrect prediction for the fraudulent class is very very high. It's okay if the model classifies a non-fraudulent transaction as a fraudulent one, but classifying a fraudulent transaction as a non-fradulent one is very very costly, because at the end of the day no one want to lose money. Due to this reason we must always keep a close look at the recall metric and make sure that the false negatives are as low as possible. We will print the confusion matrix and generate classification reports for each models and monitor the false positives.

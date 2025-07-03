# Fraud-Detection---CreditCard
Classification algorithms and undersampling techniques for detecting anomalous transactions on the dataset

Using LDA, Random under sampling on GBM

Fraud is one of the most significant issues the finance sector faces. It is incredibly costly. According to one study, it is estimated that the typical organization loses 5% of its annual revenue to fraud each year. When applied to the 2025 estimated Gross World Product of 111.6 trillion dollars, this translates to potential global losses of up to 4 trillion dollars. Fraud detection is a task inherently suitable for machine learning, as machine learning–based models can scan through huge transactional datasets, detect unusual activity, and identify all cases that might be prone to fraud. Also, the computations of these models are faster compared to traditional rule-based approaches. By collecting data from various sources and then mapping them to trigger points, machine learning solutions are able to discover the rate of defaulting or fraud propensity for each potential customer and transaction, providing key alerts and insights for financial institutions.

Results (MSE) (Mean - Std.Dev for 10-Fold cross validation)

LR: 0.928613 (0.029767)
LDA: 0.910508 (0.034821)
KNN: 0.651609 (0.039796)
CART: 0.922995 (0.033635)
NB: 0.876634 (0.046132)
SVM: 0.575919 (0.062354)
NN: 0.658312 (0.135549)
AB: 0.941062 (0.029656)
GBM: 0.942224 (0.026700)
RF: 0.937679 (0.028996)
ET: 0.927528 (0.017197)


Model Tuning for balancing the sample by Random Under Sampling

We will implement "Random Under Sampling" which basically consists of removing data in order to have a more balanced dataset and thus avoiding our models to overfitting.

Steps:

The first thing we have to do is determine how imbalanced is our class (use "value_counts()" on the class column to determine the amount for each label).

Once we determine how many instances are considered fraud transactions (Fraud = "1") , we should bring the non-fraud transactions to the same amount as fraud transactions (assuming we want a 50/50 ratio), this will be equivalent to 492 cases of fraud and 492 cases of non-fraud transactions.

After implementing this technique, we have a sub-sample of our dataframe with a 50/50 ratio with regards to our classes. Then the next step we will implement is to shuffle the data to see if our models can maintain a certain accuracy everytime we run this script.

Note: The main issue with "Random Under-Sampling" is that we run the risk that our classification models will not perform as accurate as we would like to since there is a great deal of information loss (bringing 492 non-fraud transaction from 284,315 non-fraud transaction)

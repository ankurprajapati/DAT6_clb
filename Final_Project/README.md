Full Project Proposal

#### Title
Predicting Repeat Buyers

#### Project Summary
My project will be to predict which shoppers will become repeat buyers, using shopping history, demographic and business information.  Shoppers were offered a coupon for a particular item, and the question is which shoppers who use the coupon will return to purchase the same item again.

#### Objective
The objective is to create a model that predicts which shoppers will become repeat buyers.  Success will be measured in terms of precision, recall and predictive power. 

#### Methods
##### Model.
. Logistic regression.  The model will assign each user a probability of becoming a repeat buyer.  Initially, the model will be used to categorize each user as a target (bought product at least once) or non-target (did not buy product).  Depending on the data and the results, additional modeling to distinguish high versus low repeat buyers may be done. 

##### Performance metrics.
. Precision:  The fraction of all predicted targets that are actual targets.  This is a measure of accuracy.
. Recall:  The fraction of all actual targets that predicted by the model.  This is a measure of completeness.
. Predictive power:  There are many ways to measure predictive power.  Unless I come up with a better idea, I’ll use ROC, which measures how well the model distinguishes targets from non-targets.  An ROC of 0.5 indicates chance performance (for a binary outcome), while an ROC of 1.0 indicates perfect performance.  ROC has the advantage of evaluating model performance across the full range of thresholds one might use in converting the model output (a continuous probability) to a binary result (target and non-target categories).

##### Tasks.
There are several things I’ll need to do.
. Characterize dataset:  Measure and visualize the range and distribution of each dimension in the dataset.  Determine if any data preparation needs to be done.
. Dimension reduction:  Determine which metrics to use in the model.  (Could use input on this one.  I could just try out a bunch of different variables, a couple at a time, and weed out ones that don’t do well, but there may be better ways to do this.  PCA?  Something else?  This is an area I don’t have experience in.)
. Build and test the model.  This will no doubt be iteratively.  I expect a baseline level of performance will be established, and then I will work to find ways I can make the model do better.  (There may also be types of models to test besides logistic regression.  I welcome any input on this.)
. Summarize results, quantitatively and graphically.  Build 12-minute presentation.

#### Dataset
This project is taken directly from Kaggle, where it's listed as the Acquire Valued Shoppers Challenge. The dataset has about 350 million rows, 300k shoppers, and about 20 dimensions. 

#### Links
. The data has already been curated and is available on Kaggle:  https://www.kaggle.com/c/acquire-valued-shoppers-challenge
. ROC methodology:  http://en.wikipedia.org/wiki/Receiver_operating_characteristic

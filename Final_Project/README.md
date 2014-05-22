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
. The data has already been curated and is available on Kaggle.  CSVs and meta info about the data here:  https://www.kaggle.com/c/acquire-valued-shoppers-challenge/data

———————
#### Data description (copied from the site, for easy reference)

##### Relational files
. transactions.csv - contains transaction history for all customers for a period of at least 1 year prior to their offered incentive
. trainHistory.csv - contains the incentive offered to each customer and information about the behavioral response to the offer
. testHistory.csv - contains the incentive offered to each customer but does not include their response (you are predicting the repeater column for each id in this file)
. offers.csv - contains information about the offers

NOTE:  For this project, I’ll ignore testHistory.csv, and divide trainHistory into train and test sections for the purpose of building and testing models.  testHistory.csv contains the test data for the Kaggle competition, and doesn’t include the target being predicted, so it doesn’t help me.

##### Fields
. history
id - A unique id representing a customer
chain - An integer representing a store chain
offer - An id representing a certain offer
market - An id representing a geographical region
repeattrips - The number of times the customer made a repeat purchase
repeater - A boolean, equal to repeattrips > 0
offerdate - The date a customer received the offer

.. sample
id,chain,offer,market,repeattrips,repeater,offerdate
86246,205,1208251,34,5,t,2013-04-24
86252,205,1197502,34,16,t,2013-03-27
12682470,18,1197502,11,0,f,2013-03-28
12996040,15,1197502,9,0,f,2013-03-25
13089312,15,1204821,9,0,f,2013-04-01

. transactions
id - see above
chain - see above
dept - An aggregate grouping of the Category (e.g. water)
category - The product category (e.g. sparkling water)
company - An id of the company that sells the item
brand - An id of the brand to which the item belongs
date - The date of purchase
productsize - The amount of the product purchase (e.g. 16 oz of water)
productmeasure - The units of the product purchase (e.g. ounces)
purchasequantity - The number of units purchased
purchaseamount - The dollar amount of the purchase

.. sample
<pending>

. offers
offer - see above
category - see above
quantity - The number of units one must purchase to get the discount
company - see above
offervalue - The dollar value of the offer
brand - see above

.. sample
offer,category,quantity,company,offervalue,brand
1190530,9115,1,108500080,5,93904
1194044,9909,1,107127979,1,6732
1197502,3203,1,106414464,0.75,13474
1198271,5558,1,107120272,1.5,5072
1198272,5558,1,107120272,1.5,5072

The transactions file can be joined to the history file by (id,chain). The history file can be joined to the offers file by (offer). The transactions file can be joined to the offers file by (category, brand, company). A negative value in productquantity and purchaseamount indicates a return.
———————

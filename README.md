# Report:


### data preprocessing:

* delete items which price >= 100000 or sales >= 1000.
* some shops are almost the same, so merge them together.
* some of test set are not in the training set, so fill those blanks with zeros.
* clip the target value to (0, 20).
* add mean encoded features (Ex: average item sales every month, every shops).
* add price trend features
* add date (months, and days)

### model:
XGBRegressor

### feature selection
first, try to train with all the feature. Then use the function "plot_features" to delete the unimportant features.

### description:
baseline 0.90646 is the best.

## Fail Try:

### data preprocessing:

* the features of training set are only date_block_num, shop_id, item_id, average items price every months, every shops
* delete items which price >= 100000 or sales >= 999.
* although some shops are almost the same, but still treat them as different shop.
* some of test set are not in the training set, so fill those blanks with zeros.

### model:
* the loss of linear regression, ElasticNet, lasso, ridge are about 5.1
* the loss of SVR, SVM are about 0.98

  PS : since all the target in the training set are actually only 324 kinds of values, so regression can be treated as classification
* the loss of decision tree is about 1.2

  PS : this model predict that all the result are the same value, I guess the problem is my data preprocessing.




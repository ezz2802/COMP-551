Reddit_Comment_Classification: Kaggle competition

Packages used include: numpy, panda, warnings, sklearn, and nltk.

It might be necessary to uncomment the nltk.download lines in the imports block to gain access to the package.


The code is split into 2 parts: Evaluation

First part there is a clean_text function that we eventually don't use due to it lowering the accuracy. It converts the data set into pure text.

There is also a k folds function that returns an array with k*2 entries (Train/Test folds).

In our main we read the dataset, drop ID column, and call k_fold. After that we evaluated several models: LR, CNB, DTC, SVC, etc.

Our best performance was on ComplementNaiveBayes and hence we uploaded the results from that algorithm to Kaggle.

There is also a decode_labels function that returns labels to subreddits.


Next part: Submission csv

Next, we just read the datasets (train/test) again, train CNB on the entire dataset, and output a prediction csv in order to upload to Kaggle.

In order to reproduce the Kaggle & validation results, just run entire notebook with the datasets in the same folder.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
BNB Implementation: our own BNB implementation

Packages used include: numpy, panda, and sklearn.


Same k folds function that returns an array with k*2 entries (Train/Test folds).

bnbayes is our fit function and predict outputs y_pred. BNB is our main function.

In our main we read the dataset, drop ID column, and call k_fold. After that we evaluated our model using our k_fold, fit/predict, and sk metrics accuracy.

In order to recreate our BNB accuracy just run the notebook.
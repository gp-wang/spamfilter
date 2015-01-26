# spamfilter
a Bayesian-network-based spam-email filter

 Implement a Naïve Bayes Classifier for Spam Detection [60]

Naive Bayes is a simple and effective machine learning method that is used to solve a variety of
problems, including the application of spam e-mail detection. You are to implement a Naive Bayes
classifier that classifies e-mail messages as spam (i.e., junk mail) or ham (i.e., legitimate message).
The training and test data sets for this assignment can be found in HW5_code.zip
The training set consists of 800 spam messages and 800 ham messages in separate directories, and
the test set contains 400 spam and 400 ham messages. Both sets have original header information
intact. Each e-mail message is an individual text file. The data is organized as follows:

/train/ham/
/train/spam/
/test/ham/
/test/spam/

The code provided reads in all messages in the training set, extracts each word, removes
punctuation and digits, builds a dictionary of all the words, and stores the word counts and word
probabilities. This code is provided in the skeleton code file NBSpamDetectionIO.java. You
will need to edit this code and add additional code to complete the tasks below.
Using the dictionary, you must compute and store the prior probabilities, P(spam) and P(ham), as
well as the conditional probabilities, P(w | spam) and P(w | ham) for each word w. Store all
probabilities as logs to avoid underflow. For example, instead of storing P(spam) directly, calculate
and store log P(spam). This also means you need to do arithmetic in log-space. That is,
multiplications of probabilities become additions of log probabilities (see the Hints section below).
For example, log P(“the”, spam) = log [ P(“the” | spam)P(spam) ] = log P(“the” | spam) + log P(spam)
Also, to avoid any “zero count” issues, implement “add-1 smoothing” when calculating frequencies.


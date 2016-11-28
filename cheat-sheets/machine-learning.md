# Machine Learning

A highly opinionated ML cheat sheet.

## Getting Started

* Deep Learning Demystified, by [Brandon Rohrer](https://brohrer.github.io/):
    * [How Neural Networks work?](https://brohrer.github.io/deep_learning_demystified.html)
    * [How Convolutional Neural Networks work?](https://brohrer.github.io/how_convolutional_neural_networks_work.html)
* A Neural Network in 15 lines of Python, by [Andrew Trask](https://twitter.com/iamtrask):
    * [basic Neural Network in 11 lines](http://iamtrask.github.io/2015/07/12/basic-python-network/)
    * [adding Gradient Descent Optimizer](http://iamtrask.github.io/2015/07/27/python-network-part2/)
    * [adding Hinston's Dropout](https://iamtrask.github.io/2015/07/28/dropout/)
* Understanding the maths behind Deep Learning, with code implementations:
    * [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/index.html) by [Michael Nielsen](https://twitter.com/michael_nielsen)
* Gentlest Introduction to Tensorflow, by [Soon Hin Khor](https://twitter.com/neth_6):
    * [Linear regression for single feature single outcome model](https://medium.com/all-of-us-are-belong-to-machines/the-gentlest-introduction-to-tensorflow-248dc871a224#.pbfs8sxmz)
    * [Training illustrated in diagrams/code, and exploring training variations](https://medium.com/all-of-us-are-belong-to-machines/gentlest-introduction-to-tensorflow-part-2-ed2a0a7a624f#.eerdfyjcs)
    * [Matrices and multi-feature linear regression](https://medium.com/all-of-us-are-belong-to-machines/gentlest-intro-to-tensorflow-part-3-matrices-multi-feature-linear-regression-30a81ebaaa6c#.1c6z3z79z)
* Practical Examples:
    * [Qualifying sales leads](https://medium.com/xeneta/boosting-sales-with-machine-learning-fbcf2e618be3#.192b2lj98), by [Per Harald Borgen](https://twitter.com/perborgen)
    * [Deep Learning for RegEx](http://dlacombejr.github.io/2016/11/13/deep-learning-for-regex.html)

## Classification

### Bag of Words Model

Assuming the occurence of each words can be used as a feature for training a classifier.

#### How it works

1. fitting: "learn" vocabulary by extracting each words from all sentences
2. transforming: extract vocabulary word count for each sentence
3. optionally keep only the most x used words

#### Reference

[Bag of Words for beginners](https://www.kaggle.com/c/word2vec-nlp-tutorial/details/part-1-for-beginners-bag-of-words)
by [Kaggle](https://www.kaggle.com/)

### Naive Bayes Classifier

Assuming that a statement probability of being of a certain type depends if this type is more likely
and if the statement contains more words of this type.

#### How it works

1. "learning" types:
   * count the total number of documents
   * count how many times a word from a statement occurs for a given type
2. "guessing" types:
   * calculate type probability: count of documents of this type / total count of documents
   * calculate statement type probability: for each words in the statements
     * calculate word type probability: count occurence of this word for this type / total number of words
     * multiply all word type probabilities
   * calculate likelihood: multiply type probability by statement type probability
   * the statement is likely being of the type that has the highest likelihood

#### Reference

[Machine Learning: Naive Bayes](https://stovepipe.systems/post/machine-learning-naive-bayes),
by [Yannick de Lange](https://twitter.com/yannickl88)

### Random Forest Classifier

#### How it works

1. "training":
   * take a subset (~66%) of the data
   * for each node:
     - take randomly _m_ items from the subset
     - pick the item that provides the best split and use it to do a binary split on that node
     - for the next node, do the same with another _m_ random items from the subset
2. "running":
   * run input down all the trees
   * take the average, or weighted average, or voting majority of all the results

> _m_ can be either (your choice):
>
> * 1 (random splitter selection)
> * total number of items (breiman’s bagger)
> * something in between, e.g. ½√m, √m, and 2√m (random forest)

#### Reference

[A Gentle Introduction to Random Forests](https://citizennet.com/blog/2012/11/10/random-forests-ensembles-and-performance-metrics/),
by [Dan Benyamin](https://twitter.com/dbenyamin)
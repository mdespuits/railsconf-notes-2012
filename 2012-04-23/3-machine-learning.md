# Machine Learning and Rails

## Speakers: Andrew Cantino and Ryan Stout

    The web is data.

## Andrew Cantino

### Classification

#### Documents

* Sort
* Route

#### Users

* Expertise
* Interest
* Pre vs Free

#### Events

* Links
* Locations

### Algorithms

* Decision Tree Learning
* Support Vector Machines (SVMs)

#### Support Vector Machines

* Works well for anything small.
* Library called `libsvm`
* Naive Bayes works well for text
* Neural Nets

#### Naive Bayes

* Break documents into words and treat each word as an **independent** feature.
* Works well when you have lots of data.

1. You received **100** emails, **70(( of which were spam
2. Count the number of times various words occurred in those emails.

#### Neural Nets

* Input layer (features)
* Hidden layer
* Output layer (Classification)

### Curse of Dimensionality

    The more features and labels that you have, the more data that you need.

* Number of features => data is generally exponential.

### Overfitting

* With enough parameters, anything is possible.
* We want our algorithms to **generalize** and infer, not **memorize** specific training examples.
* Therefore we **test** our algorithms on different data than we train them on.

    Our algorithm is going to learn the simplest things it can.

## Ryan Stout

* What does it look like when you want to get into machine learning?
* There are some great tools for getting you started.

### Sentiment Classification

#### Training Data:

* Tweets
* Positive / Negative
* use emoticons from twitter

We need to extract the features that we found.

#### Bag of Words Model

* What words occur in this model?
* Create a dictionary of words that occur.
* Keep a certain number of thoese.
* Replace those words with the counts that have occurred.

```ruby
dictionary = %w{I ran fast Bob far to}
```

#### Weka

* Open source java app
* Contains common ML algorithms
* GUI interface
* Can access it from jruby

Here is a [Sentiment Classification Example](https://github.com/ryanstout/mlexample)

### How do we improve?

* Have a bigger dictionary
* Bi-grams/tri-grams
* Part of speech tagging
* More data

### Feature Generation

* Think about what information is valuable to an **expert**.
* Remove data that isn't useful (**attribute selection**).
* Example: Domain Price Prediction
* Predict how much a domain would sell for.

#### Example: Domain Price Prediction

Predict how much a domain would sell for.

##### Features

* Split domain by words
* Generate features for each word
* How common the word is.
* Nubmer of google results for each word
* CPC for the word

##### Algorithm

* Support Vector Regression (SVR)

Machine learning is a ** *Massive* ** field.

### What we didn't cover

* Collaborative filtering
* Clustering
* Therorem proving (classical AI)

### Additional resources

Stanford Machine Learning Class: [mi-class.org](http://mi-class.org)

### Tools

* Weka
* `libsvm` and `liblinear`
* Vowpal Wabbit (big dictionaries)
* [Recommendify](https://github.com/paulasmuth/recommendify)

[@tectonic](http://twitter.com/tectonic) and [@ryanstout](http://twitter.com/ryanstout)

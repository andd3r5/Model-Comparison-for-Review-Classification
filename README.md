# Model Comparison for Review Classification
There are a wide variety of classification models available but the hardest part is trying
to pick which one to use for the task at hand. Depending on the type of data, hardware
resources, amount of data and other factors this can vary a lot. This project answers
how available resources and data volume influence this decision between a number of 
Machine Learning models and a RoBERTa Transformer. 
While clearly outperforming the other models on little data the Transformer couldn’t be trained on
higher amounts of data. Because of this it was surpassed by not just the moderately
time consuming Support Vector Classifier but also the very efficient Multinomial Naive
Bayes.

### Results
![](/images/Comparison_of_test_accuracy.png)

As visible above I was able to reach an accuracy of 84% with the Support Vector Classifier.
The RoBERTa Transformer outperformed it on the lower observation numbers but wasn't able to be trained on higher ones due to resource restrictions.

![](/images/Comparison_of_training_times.png)

Above displayed are the training times which show how much longer the transformer needs to train compared to the other models.

### Models

The models used in this comparison are:

- Multinomial Naive Bayes
- Bernoulli Naive Bayes
- Support Vector Machines
- RoBERTa

The model hyperparameter were optimized with CVGridSearch(), which gave the folloging result.

| Preprocessor | Tf-idf Transformer | Model |
|----------|:-------------:|------:|
| CountVectorizer(binary=True,ngram\_range=(2,2)) |  | MultinomialNB(alpha=1)|
| CountVectorizer(ngram\_range= (1, 2)) | TfidfTransformer(use\_idf=False) | MultinomialNB(alpha=0.1) |
| CountVectorizer(ngram\_range=(1, 2), binary=True) | | BernoulliNB() |
| CountVectorizer(ngram\_range= (1, 2), binary=True) | TfidfTransformer(use\_idf=True) | svm.LinearSVC() |

RoBERTa was run on default hyperparameters due to limited computational resources.

### Data
The selected dataset for the project consists of reviews of fine foods from amazon. The
reviews were written between October 1999 and Oct 2012. There are 568,454 reviews in
total by 256,059 users on 74,258 products. It was collected in J. McAuley and J. Leskovec. From amateurs to connoisseurs: modeling the evolution of user= expertise through online reviews. 2013. url: http://i.stanford.edu/~julian/pdfs/www13.pdf and has the following distribution.

![](/images/Distribution_of_user_reviews.png)

### Requirements
- Python 3.6+
- sklearn
- numpy
- pandas
- simpletransformers


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
![](/images/Comparison_of_training_times.png)
![](/images/Comparison_of_test_accuracy.png)

### Data
![](/images/Distribution_of_user_reviews.png)

### Requirements
- Python 3.6+
- sklearn
- numpy
- pandas
- simpletransformers


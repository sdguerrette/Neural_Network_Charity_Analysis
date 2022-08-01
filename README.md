# Neural Network Charity Analysis
## Overview
The purpopse of this project was to help Aplhabet Soup, a non-profit that provides business funds, to determine which candidates will successfully and effectively use the money provided to them. To accomplish this, we utilized a deep-learning neural network model that was trained and tested on previous applicant data provided by Alphabet Soup

## Results
### Data Preprocessing
- The target variable that our model attempts to predict is the "IS_SUCCESSFUL" column in the dataset.
- The feature variables include the columns: "NAME", "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION'", "USE_CASE", "INCOME_AMT", AND "ASK_AMT".
- The "EIN", "SPECIAL_CONSIDERATIONS", and "STATUS" columns were determined to provide no benefit to the model, and thus were not included in the feature variables
### Compiling, Training, and Evaluating the Model
- Our model utilized a the Keras Dense method from the Tensorflow library, and included 3 hidden layers of 100, 60, and 20 neurons. After proprocessing the dataset, we found it to be very wide, and thus decided that a higher number of neurons woul denefit our model. After testing different set ups, we settled on the layout described as it provided the best accuracy and efficiency combination. We used the RELU activation function for out hidden layers since our data points have non-linear relationships. Our output function used a Sigmoid activation, as the goal of our model was binary classification.
- After optimizing our dataset and model, we were able to achieve and surpass the goal of 75% accuracy, with our final model returning and accuracy score of 79.44%
- We achieved these results through the following steps:
 - We dropped two additional columns - "STATUS" and "SPECIAL_CONSIDERATIONS" - as we found the data in these columns extremely unbalanced, with only a small percent classifed at "STATUS" 1 or "SPECIAL_CONSIDERATIONS" Y.
 - We decided against dropping the "NAME" column and instead decided to bucket the data, with all names appearing a single time grouped into and OTHER category. In essence, this allowed the model to factor in whether a business had received funds previously, and if they had succesfully used those funds on the previous applicatioms. This changed made the largest impact on our accuracy results, making up the bulk of the nearly 7% jump in accuracy.
 - We opted to bucket the "ASK_AMT" column, as we found that nearly 75% of all applicants asked for $5,000. The remaining 25% included some massive outliers, with the maximum amount surpassing $8 Billion. We found that this allowed us to reduce the noisiness of this variable and increase the accuracy of our model by a small but measurable amount.
## Summary
We found that, after optimization, our model was able to predict whethere an applicant would successfuly allocate their funds nearly 80% of the time. We believe this to be a reasonable and useful results based on the size and type of the data provided. However, neural networks can be code, time, and resource intensive, and we believe that for a binanary classification problem such as this, other model times may be able to produce similar results more efficiently. In particular, and ensemble learning method, such as a Random Forrest Classifier, could handle the same data and produce similary results with less work and processing power.

# Credit Risk Analysis Using Supervised Machine Learning

## Overview:
Our peer-to-peer lending service company wants to use machine learning to better predict credit risk to provide more efficient and reliable lending services. Since credit risk poses an unbalanced classification problem, the purpose of this project is to build and evaluate models using resampling. In total, six machine learning models will be built, each using different techniques to deal with the unbalanced classes, and the performance of each evaluated for further recommendation and use.

## Results:
- **RandomOverSampler model:**
  - As seen below, the balanced accuracy score for this model can be rounded up to 66%. 
  - The classification report shows that while the precision is high for the majority class (low-risk), it is very low at 1% for the minority (high-risk) class.
  - Recall (sensitivity) is 71% for high-risk, but the F1 score of 2% is low meaning poor overall predictive performance.
![RandomOverSampler](https://github.com/bfox87/Credit_Risk_Analysis/blob/main/Screenshots/RandomOverSampler.PNG)
   
- **SMOTE Oversampling model:**
  - The balanced accuracy score is 66%.
  - Precision for the high-risk classs is very low at 1% with a recall of 63% which leads to a low F1 score of 2%.
  - The results of this model are quite close to that of the prior Random Oversampler model.
![SmoteOversample](https://github.com/bfox87/Credit_Risk_Analysis/blob/main/Screenshots/SmoteOversample.PNG)

- **ClusterCentroids Undersampling model:**
  - The balanced accuracy score is 54% which is lower than that of the two oversampling models above.
  - High-risk precision and recall scores are 1% and 69% respectively resulting in a very poor F1 score of 1%.
  - Also of note is the low recall of 40% for the low-risk class. This indicates a large number of false negatives.
  - In general, this model appears to a particularly poor choice for further use. 
![ClusterCentroids](https://github.com/bfox87/Credit_Risk_Analysis/blob/main/Screenshots/ClusterCentroids.PNG)

- **SMOTEENN Combination Sampling model:**
  - The balanced accuracy score is 64%.
  - High-risk precision is again 1% with recall at 70%.
  - Low-risk recall is better at 58% than the 40% seen in undersampling, but is still not great, indicating false negatives. 
![SmoteennCombo](https://github.com/bfox87/Credit_Risk_Analysis/blob/main/Screenshots/SmoteennCombo.PNG)

- **Balanced Random Forecast Classifier model:**
  - The balanced accuracy score is 79%, an improvement over the previous models.
  - The high-risk metrics have improved a little with precision now at 3% and recall at 70%.
  - Low-risk recall has also improved and now at 87%. 
![BalancedRandomForest](https://github.com/bfox87/Credit_Risk_Analysis/blob/main/Screenshots/BalancedRandomForest.PNG)

- **Easy Ensemble AdaBoost Classifier model:**
  - The balanced accuracy score is 93%, the highest seen in any of the models evaluated.
  - The high-risk metrics have jumped over the other models with precision now at 9% and recall at 92% for a F1 of 16%.
  - Low-risk F1 score of 97% indicates a strong predictive performance. 
![AdaBoost](https://github.com/bfox87/Credit_Risk_Analysis/blob/main/Screenshots/AdaBoost.PNG)

## Summary:
The main thing that stands out is all six models display poor precision when evaluating if high-risk. These low precision scores are indicative of large numbers of false positives. In other words, predicting a high credit risk when in actuality they are low-risk. Beyond this main point, the ensemble models, particularly the Easy Ensemble AdaBoost Classifier, did show some predictive improvement. The process of Adaptive Boosting appears successful as the AdaBoost Ensemble model showed significant improvement in balanced accuracy scores as well as recall (sensitivity) in predicting high-risk instances.

#### Model Recommendation:
I would advise against using any of these models to predict credit risk. The reason being the prevelance of low precision values in all of the models, which due to the problems described above, will likely cause the lending service to shy away from lower-risk customers it mistakenly thinks are high-risk. Over time this could have a major impact on revenue growth at the company. Credit risk is quite hard to predict and no prediction model is perfect. However, a better model should be developed.

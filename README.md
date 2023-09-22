# Toxic-Comment-Classification
Toxic Comment Classification using standard ML and LSTM

### Problem statement : 
Our project aims to construct a robust predictive model capable of assessing the likelihood of various forms of toxicity, including but not limited to toxic, severe_toxic, obscene, threat, insult, and identity_hate, within a vast dataset of user comments sourced from Wikipedia. These comments have been meticulously annotated by human raters for classification.

### Data source:
Dataset is available on Kaggle at the following link :
https://www.kaggle.com/competitions/jigsaw-toxic-comment-classification-challenge/data

### What analysis were performed
In our quest for efficient multi-label classification, we explored  different methods of traditional ML and Neural Network based, each with its unique approach and advantages.

#### Traditional ML approach:

##### Method 1: Binary Classifiers using Logistic Regression<br>
Our initial strategy involved treating each label as an independent binary classification problem. This Binary Relevance approach created six separate binary classifiers, one for each label. Despite assuming no label correlations, it provided a solid baseline for our task.

##### Method 2: Chained Binary Classifiers using Logistic Regression<br>
To capture potential label dependencies, we adopted the Classifier Chains approach. Here, we trained a chain of classifiers where each subsequent classifier incorporated the predictions of all preceding ones. This method leveraged label correlations, improving classification performance.

##### Method 3: Single MultiClass Classifier using Logistic Regression<br>
Recognizing the computational overhead of maintaining six separate models, we devised a unified solution. We combined the labels into a new multiclass classification problem, resulting in 64 classes. Using a multiclass linear regression model, we efficiently handled all classes within a single model.

Our evaluation revealed that the single multiclass classifier yielded results comparable to Binary Relevance and Chained Binary Classifiers. Its advantages included reduced complexity, streamlined approach, efficient inference, unified decision-making, simplified maintenance, and faster predictions.

#### Neural Network based approach:

We also implemented an LSTM model with Glove embeddings. Compared to Method-3 from traditional ML the results were similar, with the LSTM slightly outperforming. Choosing a neural network like LSTM was advantageous due to our large dataset, avoiding overfitting common in traditional ML with limited data. LSTM's ability to model word relationships and avoid manual feature engineering also contributed to its superior performance.

<img width="471" alt="image" src="https://github.com/aasthatandon/Toxic-Comment-Classification/assets/28407844/069a7e9e-7315-4f97-a4a0-d1aa1127cfe6">


### Files Overview:
- ```EDA_and _Traditional_ML_Method.ipynb```: EDA and Designed a classification system using the traditional NLP techniques - for
instance - stop word removal, stemming… etc - followed by a standard ML algorithm.
- ```Neural_Network_Method_usingLSTM.ipynb```: Designed a classification system using Neural Networks - LSTM 

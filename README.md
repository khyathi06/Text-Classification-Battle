Text Classification Battle: Comparative Analysis of Machine Learning Algorithms for SMS Spam Detection

1. Project Overview

SMS spam detection is a text classification problem that identifies whether a text message is legitimate or unwanted. Spam messages may contain fraudulent offers, suspicious links, advertisements, or misleading information.

This project presents a comparative study of four machine learning classification algorithms:

- Decision Tree
- K-Nearest Neighbours (KNN)
- Support Vector Machine (SVM)
- Naive Bayes

All four algorithms are evaluated using the same dataset, preprocessing procedure, TF-IDF feature representation, and train-test split to ensure a fair comparison.

2. Problem Statement

The increasing number of unwanted and potentially fraudulent SMS messages creates a need for automatic message classification. Manually identifying spam messages is time-consuming and may lead to errors.

The objective is to develop and evaluate machine learning models that classify SMS messages into two categories: spam and ham.

3. Project Objectives

1. Select a suitable labelled SMS text classification dataset.
2. Explore the dataset and examine the distribution of spam and legitimate messages.
3. Perform text preprocessing to prepare messages for machine learning.
4. Convert text messages into numerical features using TF-IDF.
5. Implement Decision Tree, KNN, SVM, and Naive Bayes classifiers.
6. Evaluate the classifiers using Accuracy, Precision, Recall, and F1-score.
7. Compare classifier performance using tables and visualizations.
8. Analyze confusion matrices to understand classification errors.
9. Conduct a what-if experiment by changing the SVM regularization parameter.
10. Recommend the most suitable classifier based on the actual experimental results.

4. Dataset Description

Dataset name: SMS Spam Collection

Source: UCI Machine Learning Repository

Official dataset URL:
https://archive.ics.uci.edu/dataset/228/sms+spam+collection

The dataset contains SMS messages labelled according to their class.

Dataset attributes

Attribute| Description
label| Category assigned to the message
message| Original SMS text

Classification labels

- Ham: A legitimate, non-spam SMS message.
- Spam: An unwanted or spam SMS message.

The original dataset contains 5,574 messages. The actual number of records used in the experiment may differ after data cleaning and duplicate removal.

5. Tools and Technologies

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- GitHub

6. Methodology

The project follows these stages:

1. Dataset loading and inspection
2. Exploratory data analysis
3. Text preprocessing
4. Training and testing data split
5. TF-IDF feature extraction
6. Model training
7. Performance evaluation
8. Comparative visualization
9. Confusion matrix analysis
10. What-if experiment
11. Final recommendation

7. Text Preprocessing

Text preprocessing helps standardize messages before feature extraction.

The preprocessing operations used in this project include:

- Converting text to lowercase.
- Removing HTML tags where present.
- Removing punctuation and unwanted special characters.
- Removing extra whitespace.
- Checking for missing values.
- Removing duplicate records.

The cleaned messages are used as inputs to the TF-IDF vectorizer.

8. Feature Extraction Using TF-IDF

Term Frequency–Inverse Document Frequency (TF-IDF) converts text documents into numerical feature vectors.

Term Frequency represents how frequently a term appears in a document. Inverse Document Frequency reduces the relative importance of terms that occur across many documents.

The project uses "TfidfVectorizer" to transform the cleaned SMS messages into numerical features.

The vectorizer is fitted only on the training text and then applied to the test text. This prevents information from the test set from influencing feature fitting.

9. Train-Test Split

The dataset is divided into training and testing subsets using an 80:20 split.

- Training set: Used to train the classifiers.
- Testing set: Used to evaluate predictions on unseen messages.

A fixed random seed and stratified splitting are used so that all four classifiers receive the same training and testing samples.

10. Machine Learning Algorithms

10.1 Decision Tree

Decision Tree creates a sequence of decision rules based on input features. It can model nonlinear relationships but may overfit when the tree becomes too complex.

10.2 K-Nearest Neighbours (KNN)

KNN classifies a message using the labels of nearby training examples in feature space. Its performance can depend on the number of neighbours, distance calculation, and the sparsity of TF-IDF features.

10.3 Support Vector Machine (SVM)

SVM learns a decision boundary that separates classes. The project uses "LinearSVC", which is suitable for high-dimensional text feature representations.

10.4 Naive Bayes

Multinomial Naive Bayes estimates class probabilities from feature frequencies. It is commonly used for text classification because it is computationally efficient and works with non-negative feature values such as TF-IDF.

11. Evaluation Metrics

The classifiers are evaluated using four metrics.

- Accuracy: Proportion of all predictions that are correct.
- Precision: Proportion of messages predicted as spam that are actually spam.
- Recall: Proportion of actual spam messages correctly detected.
- F1-score: Harmonic mean of precision and recall.

Spam is treated as the positive class when calculating Precision, Recall, and F1-score.

12. Experimental Results

The table below must be completed using the actual output generated by the executed notebook.

Algorithm| Accuracy| Precision| Recall| F1-score
Decision Tree| To be measured| To be measured| To be measured| To be measured
KNN| To be measured| To be measured| To be measured| To be measured
SVM| To be measured| To be measured| To be measured| To be measured
Naive Bayes| To be measured| To be measured| To be measured| To be measured

The experimental values will be reported after running all four models on the selected dataset.

13. Performance Visualization

A grouped bar chart is generated to compare Accuracy, Precision, Recall, and F1-score across the four classifiers.

The visualization helps identify differences in overall correctness, spam detection, and the balance between Precision and Recall.

14. Confusion Matrix Analysis

A confusion matrix is generated for each classifier.

The matrix contains:

- True Negatives: Ham messages correctly classified as ham.
- False Positives: Ham messages incorrectly classified as spam.
- False Negatives: Spam messages incorrectly classified as ham.
- True Positives: Spam messages correctly classified as spam.

False positives may cause legitimate messages to be filtered unnecessarily. False negatives allow spam messages to pass through undetected.

The confusion matrices are used to examine these errors and complement the evaluation metrics.

15. What-If Experiment

The what-if experiment investigates how changing the SVM regularization parameter "C" affects classification performance.

The experiment compares the following values:

- C = 0.1
- C = 1.0
- C = 10.0

All other conditions, including the dataset, TF-IDF representation, and train-test split, are kept constant.

The Accuracy, Precision, Recall, and F1-score are measured for each configuration. The results are used to determine whether changing the parameter improves or reduces performance.

The final interpretation will be based on the actual experimental output.

16. Discussion

The performance differences between classifiers can arise from their learning mechanisms.

Decision Tree learns feature-based decision rules, while KNN relies on similarity between feature vectors. SVM learns a separating boundary, and Naive Bayes uses probabilistic class estimates based on feature distributions.

The final discussion will compare the measured metrics and confusion matrices to explain the observed differences. No classifier will be declared the winner before the experimental results are verified.

17. Conclusion

This project evaluates four machine learning algorithms for SMS spam classification using a common dataset and TF-IDF feature representation.

The final recommendation will be based on the actual Accuracy, Precision, Recall, F1-score, and confusion matrix analysis. The selected model should provide an appropriate balance between detecting spam and avoiding the incorrect filtering of legitimate messages.

18. Limitations

- The dataset may not represent all current SMS spam patterns.
- New spam messages may contain vocabulary not present in the training data.
- Model performance depends on preprocessing choices and hyperparameters.
- Results from one train-test split may not generalize to every real-world dataset.
- This experiment evaluates text classification and does not establish that the system can detect every fraudulent message.

19. Future Enhancements

- Evaluate additional text representations and n-gram features.
- Apply cross-validation for more robust performance estimates.
- Tune model hyperparameters systematically.
- Test the models on newer SMS datasets.
- Develop a simple web interface for classifying user-provided messages.

20. Repository Contents

- "Text_Classification_Battle.ipynb" — notebook containing the code, experimental outputs, tables, and visualizations.
- "README.md" — project documentation.
- Additional result files — graphs or reports, if saved separately.

21. References

1. UCI Machine Learning Repository, SMS Spam Collection Dataset: https://archive.ics.uci.edu/dataset/228/sms+spam+collection
2. Scikit-learn documentation: https://scikit-learn.org/stable/
3. Scikit-learn text feature extraction documentation: https://scikit-learn.org/stable/modules/feature_extraction.html#text-feature-extraction


Note: All reported metrics, graphs, and conclusions must correspond to the actual executed experiments.

Final report 

The objective of this study is to build a machine learning model that accurately classifies mushrooms as edible or poisonous based on their physical characteristics. This classification can help in preventing mushroom poisoning by providing an automated method for identifying toxic species.

1.2 Dataset Overview

The dataset contains 8,124 mushroom samples with 23 categorical features, including:

Cap shape, cap color, and cap surface – Describe the appearance of the mushroom cap.

Gill characteristics (size, color, spacing, attachment) – Important for mushroom identification.

Odor – One of the strongest indicators of toxicity.

Spore print color, habitat, and population – Environmental attributes influencing classification.

Class (Target Variable):

0 = Edible (safe for consumption)

1 = Poisonous (toxic and dangerous)

--2. Data Preprocessing

2.1 Cleaning the Data

Column names and values contained encoding artifacts (e.g., b'x'). These were removed.

All features were categorical, requiring label encoding for machine learning.

The dataset contained no missing values, so no imputation was needed.


2.2 Encoding Categorical Data

Each categorical variable was converted into numerical format using label encoding, ensuring compatibility with machine learning models. For example:

Odor:

Almond → 0

Foul → 1

None → 2

...


Cap Shape:

Bell → 0

Conical → 1

Convex → 2

...



2.3 Splitting the Data

The dataset was divided into:

Training Set: 6,499 samples (80%)

Testing Set: 1,625 samples (20%)


This ensures that the model generalizes well to unseen data.


---

3. Model Selection & Training

3.1 Model Choice: Random Forest Classifier

A Random Forest Classifier was selected as the classification model.

Random Forest is an ensemble learning method that combines multiple Decision Trees to improve accuracy and reduce overfitting.

It is robust against noisy data and provides better generalization than a single Decision Tree.


3.2 Model Training

The Random Forest model was trained on the 80% training set, learning to classify mushrooms based on features like odor, gill characteristics, and habitat.


---

4. Model Evaluation

4.1 Accuracy Score

The Random Forest model achieved an accuracy of 100%, correctly classifying all mushrooms in the test set.

4.2 Confusion Matrix

True Positives (TP): 782 poisonous mushrooms correctly classified.

True Negatives (TN): 843 edible mushrooms correctly classified.

False Positives (FP): 0 (No edible mushrooms misclassified as poisonous).

False Negatives (FN): 0 (No poisonous mushrooms misclassified as edible).


4.3 Classification Report

Precision: The model correctly classifies 100% of mushrooms as edible or poisonous.

Recall: It captures 100% of poisonous mushrooms, meaning no misclassified dangerous mushrooms.

F1-Score: A perfect score (1.00), indicating balanced precision and recall.



---

5. Interpretation of Results

5.1 Key Features in Classification

The Random Forest model identified three highly influential features:

1. Odor → The strongest predictor of toxicity. Mushrooms with a foul odor are almost always poisonous.


2. Gill Size & Color → Certain gill sizes and colors strongly correlate with edibility.


3. Spore Print Color → Some colors (e.g., white, brown) indicate safety, while others (e.g., green) suggest toxicity.



5.2 Comparison with Decision Tree

The Random Forest performed as well as the Decision Tree (100% accuracy) but has a lower risk of overfitting since it averages multiple decision trees.

If deployed in a real-world setting, Random Forest is preferred due to its better generalization.


5.3 Implications

The model can be used in real-world applications, such as mushroom identification apps or food safety analysis.

Since 100% accuracy is rare, real-world deployment should involve additional verification methods to ensure safety.



---

6. Conclusion & Recommendations

6.1 Summary

The Random Forest model successfully achieved 100% accuracy, correctly classifying all mushrooms as either edible or poisonous.

The most critical feature in classification was odor, followed by gill and spore characteristics.

No mushrooms were misclassified, meaning the model is highly reliable.

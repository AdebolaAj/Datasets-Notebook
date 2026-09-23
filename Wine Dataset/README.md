# Wine-Dataset-Notebook

### Purpose
The purpose of this notebook is to analyze the Wine dataset available through scikit-learn and compare two classification methods: K-Nearest Neighbors (KNN) and Radius Neighbors (RNN). The dataset contains 178 wine samples with 13 numerical features, including alcohol, malic acid, color intensity and proline, and a target identifying one of three wine classes. We want to use these measurements to predict the wine class and see how different neighbor settings affect model accuracy.

### Key Insights
The dataset has no missing values, so no missing data handling was needed. The three classes contain 59, 71 and 48 samples respectively, with class 1 being the largest at approximately 39.89% of the dataset. The data was split into 142 training samples and 36 testing samples, preserving the class proportions through a stratified split.

From the results and accuracy plots, KNN achieved 97.22% accuracy for k values of 1 and 5, and 100% accuracy for k values of 11, 15 and 21. The notebook reports k = 11 as the best setting because it is the first value to reach the highest accuracy, although all three settings tied on this test set.

For RNN, the highest accuracy was 72.22% with a radius of 350. Accuracy generally decreased as the radius increased, reaching 66.67% at radii of 550 and 600. KNN achieved higher accuracy in this experiment, but the models used different preprocessing: KNN used standardized features while RNN used the original feature values. This means the results reflect both the model settings and the difference in feature scaling.

### Challenges and decisions
A key consideration was handling the different scales of the wine measurements. For KNN, I used StandardScaler so that features with larger numerical values would not dominate the distance calculation. The scaler was fitted only on the training data and then applied to the test data. RNN used the original feature values with radii ranging from 350 to 600, so features with larger scales, such as proline, can have more influence on its distances.

I used an 80/20 train-test split with random_state = 42 to make the results reproducible, and stratification to preserve the class distribution. For RNN, I set outlier_label="most_frequent" so that a sample with no neighbors within the chosen radius could still receive a prediction using the most frequent training class.

The results show how neighbor settings can affect classification accuracy. However, the same 36 test samples were used to compare all settings, so the 100% KNN result is specific to this split. A useful next step would be to apply consistent scaling to both models, tune their settings through cross-validation on the training data, and evaluate the selected models on a separate test set.

# Machine-Learning
This is Repository NutriKids to save progress Working 


### Project Overview: Nutrition Status Prediction and Food Recommendation Models

This project aims to combine two machine learning models to provide a comprehensive solution for assessing children's nutritional status and recommending suitable food and drinks to improve their health. Below is a detailed breakdown of the models and the technologies used.

---

### **Technologies Used:**
1. **Programming Language:**
   - Python
2. **Libraries and Frameworks:**
   - **Data Processing:** Pandas, NumPy
   - **Machine Learning:** Scikit-learn (LabelEncoder, train_test_split, MinMaxScaler, classification metrics)
   - **Deep Learning:** TensorFlow, Keras (LSTM, Dense layers)
   - **Visualization:** Matplotlib, Seaborn
3. **Storage and Deployment:**
   - Google Colab and Google Drive for model storage and deployment.

---

### **1. Nutrition Status Prediction Model**

#### **Purpose:**
- To predict the nutritional status of children (e.g., "Underweight," "Normal," "Overweight") based on their **age**, **height**, and **weight**.

#### **Model Type and Architecture:**
- **Type:** Classification model using Long Short-Term Memory (LSTM), which is suitable for sequential data.
- **Architecture:**
  - Input: Preprocessed features (age, height, weight).
  - LSTM layer: Captures relationships between features over sequential inputs.
  - Dense layers: Used for classification into one of three classes.
  - Activation function: **Softmax** for multi-class classification.

#### **Input:**
- Features: `Age`, `Height`, `Weight` (numerical data normalized using MinMaxScaler).

#### **Output:**
- Predicted class: Nutritional status (e.g., "Underweight," "Normal," "Overweight").

#### **Data:**
- Dataset: Includes details on children's age, height, weight, and computed BMI.

#### **Workflow:**
1. **Data Preprocessing:**
   - Compute BMI using the formula: `BMI = weight / (height^2)`.
   - Categorize BMI into nutritional statuses based on thresholds.
   - Encode categorical statuses into numerical labels using LabelEncoder.

2. **Training:**
   - Split data into training and validation sets.
   - Train the LSTM model with class weights to handle class imbalances.

3. **Evaluation:**
   - Metrics: Accuracy, classification report, and confusion matrix.
   - Visualize training performance with accuracy and loss plots.

---

### **2. Food and Drink Recommendation Model**

#### **Purpose:**
- To recommend suitable food and drink items based on the nutritional needs of children and nutrient composition of available foods.

#### **Model Type and Architecture:**
- **Type:** Regression model using a feed-forward neural network.
- **Architecture:**
  - Two input layers: 
    - **User Input:** Captures user preferences for various nutrients.
    - **Food Data Input:** Represents the nutritional composition of food items.
  - Fully connected dense layers: Perform feature combination and prediction.
  - Regularization: Dropout and Batch Normalization to prevent overfitting.
  - Output: A suitability score for each food item.

#### **Input:**
- **User Preferences:** Hypothetical preferences for nutrients.
- **Food Nutrient Data:** Features such as caloric value, protein, vitamins, minerals.

#### **Output:**
- Predicted rating or suitability score for food items.

#### **Data:**
- **Food Dataset:** Contains nutrient details like calories, protein, fats, vitamins, and minerals.

#### **Workflow:**
1. **Data Preprocessing:**
   - Normalize food features using MinMaxScaler to ensure uniform scaling.

2. **Training:**
   - Generate synthetic ratings as labels.
   - Train the model to predict ratings for food items.

3. **Evaluation:**
   - Metrics: Mean Squared Error (MSE), Mean Absolute Error (MAE), and accuracy.
   - Visualize training performance through loss and accuracy plots.

---

### **Project Integration:**
1. **Step 1:** Predict a child's nutritional status using the **Nutrition Status Prediction Model** based on age, height, and weight.
2. **Step 2:** Use the predicted nutritional status as context to query the **Food Recommendation Model**.
3. **Step 3:** Recommend food and drink items tailored to improve the child's nutritional status based on nutrient composition.

---

### **Summary of the System:**

- **Scalability:** 
  - The models can be easily scaled to include more features (e.g., activity level, genetic factors) or a larger variety of food items.
- **Usability:**
  - Useful for healthcare professionals and parents to make informed decisions about child nutrition.
- **Deployment:**
  - Models are saved and deployed using Google Drive for accessibility and reusability.

By integrating these two models, the system provides a comprehensive pipeline for analyzing a child's health and offering actionable recommendations to ensure balanced nutrition.

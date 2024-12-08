# Machine-Learning
This is Repository NutriKids to save progress Working 


### Purpose and Flow of the Models

#### **1. Nutrition Status Prediction Model (LSTM-based):**

**Purpose:**
- The goal is to predict the nutritional status (e.g., underweight, normal, overweight) of children based on their **age**, **height**, and **weight**.
- The classification is based on Body Mass Index (BMI) and uses categories defined by BMI thresholds.

**Workflow:**
1. **Data Preparation:**
   - Load child growth data.
   - Compute BMI using the formula: `BMI = weight / (height^2)`.
   - Categorize BMI into nutritional status classes (`underweight`, `normal`, and `overweight`).
   - Encode the nutritional status labels into numerical values for machine learning.

2. **Feature Scaling:**
   - Use Min-Max Scaling to normalize age, height, and weight values to ensure the features are on the same scale.

3. **Data Splitting:**
   - Divide the dataset into training and validation subsets to evaluate model performance.

4. **Model Architecture:**
   - Use an LSTM (Long Short-Term Memory) network for sequential data modeling.
   - The LSTM captures patterns in the input features that relate to the nutritional status.

5. **Training:**
   - Train the model with class weights to handle imbalanced datasets, ensuring fair performance across all classes.

6. **Evaluation:**
   - Evaluate the model on validation data using accuracy, confusion matrix, and a classification report.
   - Visualize training progress through accuracy and loss plots.

7. **Outcome:**
   - The trained model predicts the nutritional status of children given their age, height, and weight.

---

#### **2. Food and Drink Recommendation Model:**

**Purpose:**
- Recommend suitable food and drink options based on the nutritional status of children and nutrient preferences.
- Provide data-driven suggestions to improve the child's nutrition profile.

**Workflow:**
1. **Data Preparation:**
   - Load food data, including features like caloric value, fat, protein, vitamins, and minerals.
   - Normalize all nutritional features using Min-Max Scaling.

2. **Model Architecture:**
   - The model uses two input layers:
     - **User preferences input**: Captures hypothetical preferences for each nutrient (e.g., high protein).
     - **Food nutrient data input**: Represents the nutrient composition of each food item.
   - Layers:
     - Fully connected dense layers with Dropout for regularization and BatchNormalization for stable training.
     - Final output predicts the suitability or score of the food item for a child.

3. **Data Generation:**
   - Generate synthetic user preferences and rating data for training and testing purposes.

4. **Training:**
   - Train the model to predict food ratings using features of both the user and food.

5. **Evaluation:**
   - Evaluate model performance using metrics like Mean Squared Error (MSE), Mean Absolute Error (MAE), and accuracy.
   - Visualize training performance with accuracy and loss graphs.

6. **Outcome:**
   - Given a child's nutritional needs and preferences, the model recommends food and drink items that align with their dietary goals.

---

#### **Integrated Flow:**
1. Use the **Nutrition Status Prediction Model** to determine a child’s current nutritional status (e.g., `underweight`).
2. Based on the predicted status, query the **Food Recommendation Model** to recommend food items that address the child’s nutritional deficiencies or maintain balance.
3. Save the models and scalers for future use, and transfer them to Google Drive for deployment.

By combining these models, the system provides a complete pipeline for analyzing a child’s nutritional health and offering actionable dietary suggestions tailored to their needs.

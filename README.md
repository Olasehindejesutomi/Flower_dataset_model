# 🌸 Iris Flower Species Prediction

A beginner-friendly Machine Learning classification project that predicts the species of an Iris flower from four measurements:

- Sepal Length
- Sepal Width
- Petal Length
- Petal Width

The project uses the built-in Iris dataset from Scikit-learn and a Logistic Regression classifier to predict one of three flower species: **Setosa, Versicolor, or Virginica**.

## 📌 Project Overview

The aim of this project is to understand the basic workflow of a Machine Learning classification problem, from loading data to making predictions.

### Workflow

1. Load the Iris dataset
2. Explore the features and target classes
3. Split the data into training and testing sets
4. Train a Logistic Regression model
5. Make predictions
6. Evaluate the model
7. Generate a classification report
8. Visualize the confusion matrix
9. Create a reusable prediction function

## 📊 Dataset

The Iris dataset contains four numerical features:

| Feature | Description |
|---|---|
| Sepal Length | Length of the sepal in cm |
| Sepal Width | Width of the sepal in cm |
| Petal Length | Length of the petal in cm |
| Petal Width | Width of the petal in cm |

### Target Classes

The model predicts:

- `setosa`
- `versicolor`
- `virginica`

## 🛠️ Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## ⚙️ Model Development

### 1. Load the Dataset

The Iris dataset was loaded using Scikit-learn:

```python
from sklearn.datasets import load_iris

iris = load_iris()
X, y = iris.data, iris.target
```

### 2. Split the Data

The dataset was divided into training and testing sets using an **80/20 split**:

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=1
)
```

This produced:

- **120 training samples**
- **30 testing samples**

### 3. Train the Model

A Logistic Regression classifier was used:

```python
from sklearn.linear_model import LogisticRegression

clf_model = LogisticRegression(max_iter=200)
clf_model.fit(X_train, y_train)
```

## 📈 Model Performance

The model achieved an accuracy of:

**96.67%**

```text
Accuracy: 0.9666666666666667
```

### Classification Report

| Class | Precision | Recall | F1-score | Support |
|---|---:|---:|---:|---:|
| Setosa | 1.00 | 1.00 | 1.00 | 11 |
| Versicolor | 1.00 | 0.92 | 0.96 | 13 |
| Virginica | 0.86 | 1.00 | 0.92 | 6 |
| **Accuracy** | | | **0.97** | **30** |

The model correctly classified **29 out of 30** test samples.

## 🔲 Confusion Matrix

The confusion matrix was used to compare the actual flower classes with the model's predictions.

The predictions show that only **one sample** was misclassified: one `versicolor` sample was predicted as `virginica`.

## 🔮 Making a New Prediction

A reusable function was created to predict the species of a flower from its four measurements:

```python
def predict_flower(sepal_length, sepal_width, petal_length, petal_width):
    sample = [[sepal_length, sepal_width, petal_length, petal_width]]

    pred = clf_model.predict(sample)[0]

    species = iris.target_names
    prediction = f'The species of flower is {species[pred]}'

    return prediction
```

### Example

```python
print(predict_flower(5.1, 3.5, 1.4, 0.2))
```

Expected output:

```text
The species of flower is setosa
```

## 📁 Project Structure

```text
flower-prediction/
│
├── flower_prediction.ipynb
└── README.md
```

### `flower_prediction.ipynb`

Contains the complete Machine Learning workflow, including:

- Dataset loading
- Data splitting
- Model training
- Prediction
- Accuracy evaluation
- Classification report
- Confusion matrix
- Prediction function

### `README.md`

Contains the documentation and explanation of the project.

## 🎯 Key Learning Outcomes

Through this project, I practiced:

- Loading and working with a dataset
- Understanding features and target variables
- Performing a train-test split
- Building a classification model
- Using Logistic Regression
- Making predictions with a trained model
- Evaluating model performance
- Understanding precision, recall, and F1-score
- Interpreting a confusion matrix
- Creating a reusable prediction function

## 🚀 Future Improvements

Possible improvements include:

- Comparing Logistic Regression with other classification algorithms
- Applying feature scaling and comparing model performance
- Hyperparameter tuning
- Adding more visualizations
- Building a simple user interface for predictions
- Deploying the model as a web application

## 👩🏽‍💻 About the Project

This project is part of my journey into **Machine Learning and Artificial Intelligence**.

It helped me practice the complete Machine Learning workflow — from preparing data and training a model to evaluating its performance and using it to make predictions.

## 📌 Conclusion

The Logistic Regression model successfully classified Iris flowers using their sepal and petal measurements, achieving **96.67% accuracy** on the test set.

This project represents another practical step in developing my understanding of **Python, Machine Learning, and AI**.

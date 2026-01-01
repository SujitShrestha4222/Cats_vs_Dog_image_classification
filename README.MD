


# 🐶🐱 Cats vs Dogs Image Classification (CNN)

## 📌 Project Overview:
This project is a **Convolutional Neural Network (CNN)** based image classification system that predicts whether an input image is a **Cat** or a **Dog**. The model is built using **TensorFlow & Keras** and trained on labeled image data.

The goal of this project is to understand **image preprocessing, CNN architecture, training, validation, and prediction** in a simple and practical way.

---

## Dataset Used:
Cats vs Dogs dataset--->Download from:Dataset used - https://www.kaggle.com/datasets/salad...

---

## 🧠 Model Type:
* **Deep Learning**
* **Convolutional Neural Network (CNN)**
* **Binary Classification (Cat vs Dog)**

---

## Language & Libraries Used:
* Python
* TensorFlow
* Keras
* NumPy, Pandas
* Matplotlib (for plotting)
* Jupyter Notebook
* Anaconda Env(tensorflow)

---

## 📂 Project Structure:
project-folder/
│── Train/
│    ├── Cat/
│    └── Dog/
│── Test/
│    ├── Cat/
│    └── Dog/
│── model_train.ipynb
│── evaluate_model.ipynb
│── history.json
│── my_model.keras
│── README.md

Here,Place your dataset as:Train/ & Test/

---

## Dataset Loading:
Images are loaded using Keras utility:
i.e
keras.utils.image_dataset_from_directory(
    directory="Train",
    labels="inferred",
    label_mode="int",
    batch_size=32,
    image_size=(256, 256)
)

* Images are automatically labeled based on folder names
* All images are resized to **256×256**
* Data is loaded in batches for better performance

---

## Model Architecture:
The CNN model includes:
* **Conv2D** – extracts image features
* **MaxPooling2D** – reduces image size
* **Flatten** – converts features into 1D
* **Dense layers** – final classification

---

## Model Compilation:
model.compile(
    optimizer='adam',
    loss='binary_crossentropy',
    metrics=['accuracy']
)

* **Adam optimizer** for efficient learning
* **Binary Crossentropy** for two-class classification
* **Accuracy** to measure performance

---

## Model Training:
model.fit(
    train_ds,
    epochs=10,
    validation_data=validation_ds
)

* Model trains for **10 epochs**
* Validation data is used to monitor overfitting

---

## 💾 Model Saving:
The trained model is saved using the new Keras format:
i.e
model.save("my_model.keras")

---


## Saving the training history(loss and accuracy) to a JSON file for later analysis or plotting:
import json

with open("history.json", "w") as f:
    json.dump(my_history.history, f)   
     model.fit()

---

## Loading saved model & saved history:
The saved model can be loaded and used for prediction:
i.e
model = tf.keras.models.load_model("my_model.keras", compile=False)

**and**

import json

with open("history.json", "r") as f:
    my_history_load = json.load(f)

---

## Before predicting on new image:
Predictions are made on new images after resizing and normalization it.

---

## 📊 Visualization:
Training and validation **accuracy & loss graphs** are plotted using Matplotlib to analyze model performance.

---

## ✅ Results:
* Successfully classifies images into **Cat** or **Dog**
* Demonstrates practical use of CNNs for image classification

---

## Conclusion:
This project helped in understanding:
* Image preprocessing
* CNN working principles
* Model training & evaluation
* Saving and loading models

---
# Handwritten Digit Recognition using Deep Learning

##  Project Overview
This project demonstrates how to build a Deep Learning model to recognize handwritten digits (0–9) using a Convolutional Neural Network (CNN). The model is trained using the famous MNIST dataset which contains thousands of handwritten digit images.

The project includes:

- Data Loading
- Data Preprocessing
- Model Building
- Model Training
- Model Evaluation
- Digit Prediction

---

# 🧠 Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Scikit-learn

---

# 📂 Dataset

The project uses the **MNIST Handwritten Digits Dataset**.

Dataset Details:
- 70,000 handwritten digit images
- 28 × 28 grayscale images
- Digits from 0 to 9

---

# 📦 Installation

Install the required libraries using:

```bash
pip install tensorflow numpy matplotlib scikit-learn
🚀 Project Workflow
1. Import Libraries
import tensorflow as tf
import numpy as np
import matplotlib.pyplot as plt
2. Load Dataset
mnist = tf.keras.datasets.mnist
(X_train, y_train), (X_test, y_test) = mnist.load_data()
3. Data Preprocessing

Normalize the image pixel values.

X_train = X_train / 255.0
X_test = X_test / 255.0

Reshape the dataset for CNN.

X_train = X_train.reshape(-1, 28, 28, 1)
X_test = X_test.reshape(-1, 28, 28, 1)
4. Build CNN Model
model = tf.keras.Sequential([
    tf.keras.layers.Conv2D(32, (3,3), activation='relu', input_shape=(28,28,1)),
    tf.keras.layers.MaxPooling2D((2,2)),

    tf.keras.layers.Conv2D(64, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D((2,2)),

    tf.keras.layers.Flatten(),

    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.Dense(10, activation='softmax')
])
5. Compile the Model
model.compile(
    optimizer='adam',
    loss='sparse_categorical_crossentropy',
    metrics=['accuracy']
)
6. Train the Model
model.fit(X_train, y_train, epochs=5)
7. Evaluate the Model
model.evaluate(X_test, y_test)
8. Make Predictions
prediction = model.predict(X_test)

print(np.argmax(prediction[0]))
📊 Model Performance
Training Accuracy: ~99%
Testing Accuracy: ~98%
🎯 Applications
Bank cheque digit recognition
Postal code recognition
OCR systems
Handwriting analysis
Form digitization
 Sample Output
plt.imshow(X_test[0].reshape(28,28), cmap='gray')
plt.show()
📁 Project Structure
Digit-Recognition/
│
├── digit_recognition.py
├── README.md
├── requirements.txt
└── dataset/
 Conclusion

This project shows how Convolutional Neural Networks (CNNs) can effectively recognize handwritten digits with high accuracy. CNN models are widely used in image classification and computer vision applications.

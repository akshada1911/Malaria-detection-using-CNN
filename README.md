# 🦠 Malaria Detection Using CNN  

This project leverages **Convolutional Neural Networks (CNNs)** to detect **malaria-infected** cells from microscopic images. The model classifies images into **infected** and **uninfected** categories, assisting in **early malaria diagnosis** through AI-powered deep learning techniques.  

---  

## 📌 Table of Contents  
- [Introduction](#introduction)  
- [Problem Statement](#problem-statement)  
- [Importance of This Project](#importance-of-this-project)  
- [Dataset](#dataset)  
- [Methodology](#methodology)  
- [Model Architecture](#model-architecture)  
- [Training Process](#training-process)  
- [Results and Performance](#results-and-performance)  
- [Conclusion](#conclusion)  

---  

## 🏥 Introduction  
Malaria is a **life-threatening disease** affecting millions worldwide. **Early and accurate diagnosis** is crucial for effective treatment. Manual analysis of blood smear images is **time-consuming and prone to errors**. This project automates malaria detection using **deep learning and CNNs**, improving diagnostic speed and accuracy.  

---  

## ❌ Problem Statement  
Traditional methods for malaria detection have limitations:  
- **Labor-intensive**: Requires trained professionals  
- **Subjectivity**: Prone to human errors  
- **Time-consuming**: Manual microscopic examination is slow  

This project addresses these challenges with **AI-driven image classification**.  

---  

## 🩺 Importance of This Project  
✅ **Early Detection**: Enables faster treatment decisions  
✅ **Automated Diagnosis**: Reduces reliance on manual examination  
✅ **Higher Accuracy**: CNN-based model improves classification performance  

---  

## 📂 Dataset  
The dataset consists of microscopic images classified into:  
- **🦠 Infected**: Cells containing malaria parasites  
- **🧫 Uninfected**: Healthy blood cells  

Dataset Preprocessing:  
```yaml
- **Resizing**: Images scaled to `64×64` for uniform input  
- **Normalization**: Pixel values scaled to `[0,1]` for efficient training  
- **Data Augmentation**: Flipping, rotation, and contrast adjustments applied  
- **Splitting**: Dataset divided into **80% training** and **20% testing**  
```
### Model Architecture
``` python
from keras.models import Sequential
from keras.layers import Conv2D, MaxPooling2D, Flatten, Dense, Dropout, Activation

model = Sequential()
model.add(Conv2D(32, (3,3), activation='relu', input_shape=(INPUT_SIZE, INPUT_SIZE, 3)))
model.add(MaxPooling2D(pool_size=(2,2)))
model.add(Conv2D(32, (3,3), kernel_initializer='he_uniform', activation='relu'))
model.add(MaxPooling2D(pool_size=(2,2)))
model.add(Conv2D(64, (3,3), kernel_initializer='he_uniform', activation='relu'))
model.add(MaxPooling2D(pool_size=(2,2)))
model.add(Flatten())
model.add(Dense(64, activation='relu'))
model.add(Dropout(0.5))
model.add(Dense(2, activation='softmax'))

model.compile(loss='categorical_crossentropy', optimizer='adam', metrics=['accuracy'])
model.summary()
```
### Training Process
| Parameter         | Value                     |  
|------------------|-------------------------|  
| **Model**        | CNN                       |  
| **Epochs**       | 10                        |  
| **Batch Size**   | 16                        |  
| **Image Size**   | 64×64                     |  
| **Optimizer**    | Adam                      |  
| **Learning Rate** | Adaptive (starting at 0.001) |  
| **Loss Function** | Categorical Crossentropy  |  

### Results and Performance
✅ Loss Analysis
📉 Training & Validation Loss steadily decreased, proving effective learning.

✅ Precision & Recall
✔ Precision improved consistently, reaching 95%.
✔ Recall increased, reducing false negatives.

✅ Confusion Matrix & Classification Report
The model shows high accuracy in distinguishing infected vs. uninfected cells.

### Conclusion
The CNN model successfully classifies malaria-infected cells with high accuracy.
AI-powered malaria detection can significantly reduce diagnosis time and assist healthcare professionals.
Deep learning is a promising tool for medical image analysis.



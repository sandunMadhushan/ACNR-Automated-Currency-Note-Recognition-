# ACNR (Automated Currency Note Recognition) 💵

An image classification project that uses Convolutional Neural Networks (CNN) to automatically recognize and classify different currency notes.

---

## 📋 Project Overview

This project implements a deep learning model to classify currency notes from images using TensorFlow/Keras. The model is trained on a custom dataset and can predict the denomination of currency notes with confidence scores.

---

## ✨ Features

- **Image Classification**: Automatically identifies different currency note denominations
- **Data Augmentation**: Uses validation split for better model generalization
- **Visual Analysis**: 
  - Training/Validation accuracy and loss graphs
  - Confusion matrix visualization
  - Sample predictions with confidence scores
- **Interactive Prediction**: Upload custom images to get real-time predictions
- **Top-3 Predictions**: Shows the top 3 most likely classes with confidence percentages

---

## 📊 Dataset

The dataset contains images of different currency note denominations organized in folders by class.

**Download Dataset:**
[Download from Google Drive](https://drive.google.com/file/d/1GeD_AvjWY-n2F1PU-DkUakdeHr9dmsTW/view?usp=drive_link)

**Dataset Structure:**
```
Dataset/
├── Class_1/
│   ├── image1.jpg
│   ├── image2.jpg
│   └── ...
├── Class_2/
│   ├── image1.jpg
│   └── ...
└── ...
```

---

## 🚀 Getting Started

### Prerequisites

This project is designed to run on **Google Colab** with GPU acceleration.

Required libraries:
- TensorFlow/Keras
- NumPy
- Matplotlib
- Scikit-learn
- Seaborn

### Installation & Setup

1. **Open Google Colab**
   - Go to [Google Colab](https://colab.research.google.com/)
   - Upload the notebook file

2. **Upload Dataset to Google Drive**
   - Download the dataset from the link above
   - Upload `Dataset.zip` to your Google Drive (`MyDrive/`)

3. **Run the Notebook**
   - Execute cells sequentially
   - The first cell will mount your Google Drive
   - The second cell will extract the dataset

---

## 🏗️ Model Architecture

```
Sequential CNN Model:
├── Conv2D (64 filters, 3x3, ReLU)
├── MaxPooling2D (2x2)
├── Conv2D (128 filters, 3x3, ReLU)
├── MaxPooling2D (2x2)
├── Flatten
├── Dense (64 units, ReLU)
└── Dense (num_classes, Softmax)
```

**Hyperparameters:**
- Image Size: 128x128
- Batch Size: 32
- Epochs: 5
- Optimizer: Adam
- Loss: Categorical Crossentropy

---

## 📖 Usage

### Training the Model

1. Mount Google Drive and extract dataset (Cells 1-2)
2. Run the main training cell (Cell 3):
   - Loads and preprocesses images
   - Builds the CNN model
   - Trains for 5 epochs
   - Evaluates on test data
   - Saves model as `money_model_v1.h5`

### Making Predictions

Run Cell 4 to:
- Upload an image of a currency note
- Get top-3 predictions with confidence scores
- View visualization of predicted vs actual class

---

## 📈 Model Performance

The model provides:
- **Accuracy/Loss Graphs**: Monitor training and validation metrics
- **Confusion Matrix**: Visualize classification performance
- **Classification Report**: Precision, recall, and F1-score for each class
- **Sample Predictions**: Visual comparison of predicted vs true labels

---

## 🛠️ Technologies Used

- **Python 3.x**
- **TensorFlow/Keras** - Deep learning framework
- **NumPy** - Numerical computing
- **Matplotlib** - Data visualization
- **Seaborn** - Statistical visualizations
- **Scikit-learn** - Metrics and evaluation
- **Google Colab** - Development environment

---

## 📁 Project Structure

```
ACNR (Automated Currency Note Recognition)/
├── ACNR (Automated Currency Note Recognition).ipynb
├── README.md
└── Dataset/ (extracted from Drive)
```

---

## 🔮 Future Improvements

- [ ] Implement data augmentation (rotation, zoom, flip)
- [ ] Add BatchNormalization and Dropout layers
- [ ] Increase model depth (more Conv blocks)
- [ ] Use learning rate scheduling
- [ ] Train for more epochs
- [ ] Implement transfer learning (VGG16, ResNet, etc.)
- [ ] Create standalone Python scripts for deployment
- [ ] Add real-time camera detection
- [ ] Export model to TensorFlow Lite for mobile deployment

---

## 👥 Contributors

- Lapalu Liyanage

---

## 📝 License

This project is created for educational purposes.

---

## 🙏 Acknowledgments

- Dataset contributors
- TensorFlow/Keras documentation
- Google Colab for providing free GPU resources

---

## 📧 Contact

For questions or suggestions, please open an issue in the repository.

---

**Version:** 1.0.0  
**Last Updated:** February 2026

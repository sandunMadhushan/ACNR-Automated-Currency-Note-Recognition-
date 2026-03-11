# ACNR (Automated Currency Note Recognition) 💵

An image classification project that uses Convolutional Neural Networks (CNN) to automatically recognize and classify different currency notes.

---

## 📋 Project Overview

This project implements a deep learning model to classify currency notes from images using TensorFlow/Keras. The model is trained on a custom dataset and can predict the denomination of currency notes with confidence scores.

---

## ✨ Features

- **Image Classification**: Automatically identifies different currency note denominations
- **Data Augmentation**: Training-only augmentation (rotation, shift, shear, zoom, horizontal flip) — no augmentation leak on validation/test data
- **Separate Train / Val / Test Splits**: Clean evaluation using a dedicated test generator with no shuffling
- **Regularization**: BatchNormalization after each Conv block and Dropout to combat overfitting
- **Smart Training Callbacks**:
  - `EarlyStopping` — restores best weights and stops when val_accuracy plateaus
  - `ReduceLROnPlateau` — halves the learning rate when val_loss stagnates
- **Visual Analysis**: 
  - Training/Validation accuracy and loss graphs
  - Confusion matrix visualization
  - Sample predictions with colour-coded correct/incorrect labels
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
├── BatchNormalization
├── MaxPooling2D (2x2)
├── Conv2D (128 filters, 3x3, ReLU)
├── BatchNormalization
├── MaxPooling2D (2x2)
├── Conv2D (256 filters, 3x3, ReLU)
├── BatchNormalization
├── MaxPooling2D (2x2)
├── Flatten
├── Dense (256 units, ReLU)
├── Dropout (0.4)
└── Dense (num_classes, Softmax)
```

**Hyperparameters:**
- Image Size: 128x128
- Batch Size: 32
- Epochs: up to 30 (EarlyStopping with patience=5)
- Optimizer: Adam (with ReduceLROnPlateau, factor=0.5, patience=3)
- Loss: Categorical Crossentropy

**Data Augmentation (training only):**
- Rotation range: 20°
- Width / Height shift: 0.2
- Shear range: 0.2
- Zoom range: 0.2
- Horizontal flip: enabled
- Fill mode: nearest

---

## 📖 Usage

### Training the Model

1. Mount Google Drive (Cell 2)
2. Extract the dataset (Cell 4):
   - Unzips `Dataset.zip` from Google Drive to `/content/`
3. Run the main training cell (Cell 5):
   - Creates separate train, validation, and test generators
   - Applies augmentation **only** to training data
   - Builds the improved 3-block CNN with BatchNorm and Dropout
   - Trains for up to 30 epochs with `EarlyStopping` and `ReduceLROnPlateau`
   - Evaluates on the clean test set
   - Displays accuracy/loss curves, confusion matrix, and sample predictions
   - Saves model as `money_model_v2.h5` to Google Drive

### Making Predictions

Run Cell 7 to:
- Upload an image of a currency note
- Get top-3 predictions with confidence scores and a bar chart
- View visualization of the uploaded image alongside prediction probabilities

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

- [x] Implement data augmentation (rotation, zoom, flip)
- [x] Add BatchNormalization and Dropout layers
- [x] Increase model depth (more Conv blocks)
- [x] Use learning rate scheduling (ReduceLROnPlateau)
- [x] Train for more epochs (up to 30 with EarlyStopping)
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

**Version:** 2.0.0  
**Last Updated:** March 2026

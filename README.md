# Brain-Tumor-Detection  

This project implements a CNN-based model using TensorFlow and Keras to detect brain tumors from MRI images. The model is trained on a Kaggle dataset with 253 original images, augmented to 2,065 images to address data imbalance. It preprocesses data by cropping, resizing, and normalization, achieving 88.7% test accuracy and a 0.88 F1 score.  

---

## Dataset  
- **Source**: Kaggle Brain MRI Images.  
- **Original Dataset**:  
  - 155 tumorous (positive) images in the `yes` folder.  
  - 98 non-tumorous (negative) images in the `no` folder.  
- **Augmented Dataset**:  
  - Expanded to 2,065 images (1,085 positive, 980 negative) using data augmentation techniques.  

---

## Data Preprocessing  
1. Cropped images to focus on the brain region.  
2. Resized to `240 x 240 x 3`.  
3. Normalized pixel values to the range `[0, 1]`.  
4. Split data into:  
   - 70% training  
   - 15% validation  
   - 15% testing  

---

## Model Architecture  
- Custom lightweight CNN optimized for resource efficiency.  
- **Key Layers**:  
  - Zero Padding  
  - Convolutional  
  - Batch Normalization  
  - ReLU Activation  
  - Max Pooling  
  - Flatten  
  - Dense output with Sigmoid activation for binary classification  

---

## Results  
- **Validation Accuracy**: 91%  
- **Test Accuracy**: 88.7%  
- **Test F1 Score**: 0.88  

---

## Repository Contents  
- **Notebooks**: Includes data preprocessing, augmentation, model training, and evaluation scripts.  
- **Models**: Best model saved as `cnn-parameters-improvement-23-0.91.model`.  
- **Dataset**: Contains both original and augmented images.  

---

## Usage  
1. Clone the repository.  
2. Install required dependencies using `requirements.txt`.  
3. Load the best model:  
   ```python  
   from tensorflow.keras.models import load_model  
   best_model = load_model(filepath='models/cnn-parameters-improvement-23-0.91.model')  

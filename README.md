# **Rooftop Solar Panel Segmentation using CNNs**

## **Project Overview**
This project focuses on using deep learning for rooftop segmentation from satellite images to estimate the potential for solar panel installations. It employs Convolutional Neural Networks (CNNs) to automatically detect rooftops suitable for photovoltaic (PV) panel placement, optimizing the transition to renewable energy.

## **Project Structure**
The repository contains the following key files:

- **`Masking_1.ipynb`**  
  - Generates binary masks for rooftops using OpenStreetMap and manually refined data.  
  - Processes 200×200-pixel image patches to train the CNN.  
  - Addresses misalignment issues between OpenStreetMap building data and satellite images.

- **`Data Augmentation and training the model_2.ipynb`**  
  - Prepares training data for rooftop segmentation using high-resolution images from Ljubljana and Milan.  
  - Implements various data augmentation techniques to enhance model generalization.  
  - Trains the U-Net model with Dice loss and Intersection over Union (IoU) metrics.

- **`Application_of_solar_panels_3.ipynb`**  
  - Implements the analysis of rooftop segmentation for solar panel placement.  
  - Uses a U-Net architecture for deep learning-based segmentation.  
  - Processes satellite images and calculates solar panel feasibility.

## **Methodology**
### **1. Data Collection**  
- High-resolution satellite images were gathered for Ljubljana and Milan using the Mapbox API.  
- Building geometries were extracted using OpenStreetMap and manually refined.

### **2. Mask Generation & Data Augmentation**  
- A sliding window approach was used to create 200×200-pixel patches.  
- Data augmentation techniques (flipping, rotating, scaling) were applied to improve model robustness.

### **3. Model Architecture**  
- A **U-Net CNN** was implemented for rooftop segmentation.  
- Used **Dice loss** to handle class imbalance and **IoU metric** for evaluation.

### **4. Training & Evaluation**  
- The model was trained on Ljubljana data and validated/tested on Milan data.  
- **Training accuracy**: ~95%, **IoU**: ~85%  
- **Validation accuracy**: <80%, **IoU**: ~50% (indicating generalization issues)

### **5. Challenges & Improvements**  
- The model performed well on flat roofs but struggled with sloped roofs.  
- Future improvements include:  
  - Training on more diverse cities to improve generalization.  
  - Masking rooftops with azimuth information to aid panel placement.  
  - Using GPU-based training for better efficiency.

## **How to Run the Project**
1. Run **`Masking_1.ipynb`** to generate binary rooftop masks.

2. Execute **`Data Augmentation and training the model_2.ipynb`** to prepare and train the model.

3. Use **`Application_of_solar_panels_3.ipynb`** to apply the trained model and analyze results.

## **Future Work**
- Improve segmentation of sloped rooftops by incorporating 3D geometry data.  
- Expand dataset with images from more diverse locations.  
- Optimize training pipeline using cloud-based GPU processing.  

---


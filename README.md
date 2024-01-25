# EyeGlasses-Detection

**Project Title: Eye Glasses Detection**

**Overview:**
The "Eye Glasses Detection" project focuses on developing an advanced computer vision system that can accurately identify whether a person in an image is wearing glasses or not. Leveraging state-of-the-art techniques in data preprocessing, model architecture, and tuning, this project contributes to the field of facial feature recognition, with potential applications in security, retail, and accessibility.

**Key Features:**

1. **Data Collection and Cleaning:**
   - Curated a diverse dataset containing images of individuals, categorized based on whether they were wearing glasses or not.
   - Applied data cleaning techniques to handle any noise, outliers, or inconsistencies in the image data.
   - Ensured a well-balanced dataset for effective model training.

2. **Data Preprocessing:**
   - Set a random seed for reproducibility in the experiments.
   - Employed data augmentation techniques to enrich the dataset and improve the model's ability to generalize.
   - Split the data into training and testing sets, facilitating the evaluation of model performance.

3. **Feature Extraction with MobileNetV2 Model:**
   - Implemented a feature extraction pipeline using the MobileNetV2 model.
   - Converted input images from 160x160x3 to 5x5x1280, extracting essential features from the images.
   - Added GlobalAveragePooling2D layers to aggregate feature information efficiently.

4. **Model Architecture:**
   - Developed a model architecture with a Dense layer for classification, indicating whether a person is wearing glasses or not.
   - Included a Dropout layer to prevent overfitting during training.

5. **Model Description:**
```plaintext
Model: "model"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
input_2 (InputLayer)         [(None, 160, 160, 3)]     0         
_________________________________________________________________
sequential (Sequential)      (None, 160, 160, 3)       0         
_________________________________________________________________
tf.math.truediv (TFOpLambda) (None, 160, 160, 3)       0         
_________________________________________________________________
tf.math.subtract (TFOpLambda (None, 160, 160, 3)       0         
_________________________________________________________________
mobilenetv2_1.00_160 (Functi (None, 5, 5, 1280)        2257984   
_________________________________________________________________
global_average_pooling2d (Gl (None, 1280)              0         
_________________________________________________________________
dropout (Dropout)            (None, 1280)              0         
_________________________________________________________________
dense (Dense)                (None, 1)                 1281      
=================================================================
Total params: 2,259,265
Trainable params: 1,281
Non-trainable params: 2,257,984
```

6. **Model Tuning and Compilation:**
   - Fine-tuned the model parameters to optimize performance.
   - Compiled the model using appropriate loss functions and optimizers for binary classification tasks.

**Conclusion:**
The "Eye Glasses Detection" project demonstrates the capability of advanced computer vision techniques to identify specific facial features, such as the presence of glasses. The MobileNetV2-based model, with its efficient feature extraction and lightweight architecture, provides a reliable solution for real-time detection. By utilizing data preprocessing, augmentation, and thoughtful model design, the project ensures accuracy and generalization capabilities. Future work may involve expanding the dataset, exploring additional architectures, and deploying the model in real-world applications for practical use cases.

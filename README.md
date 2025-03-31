# 🎨 Monet Style Transfer with Generative Adversarial Networks (GANs)  

## Overview  
This project implements **style transfer** using **CycleGAN** to transform photos into Monet-style paintings. The model leverages **generative adversarial networks (GANs)** to learn the artistic patterns of Monet’s paintings and apply them to real-world images.

---
## 1. Image Transformations with Augmentation  

- Data augmentation was applied to **reduce overfitting** and improve the robustness of the model.  
- Augmented images helped the model **better recognize artistic patterns** compared to training without augmentation.  
- Techniques included **random flips, rotations, and color jittering** to enhance generalization.  

---
## 2. CycleGAN Architecture  

### Residual Blocks  
- Residual blocks perform **2 convolution layers (3×3)** with:  
  - Reflection padding  
  - Instance normalization  
  - ReLU activation  

### Generator Network  
The generator transforms images from **photo to Monet-style paintings** using:  
- 7×7 convolutional layer to process input images.  
- 2 downsampling layers to reduce resolution.  
- 9 residual blocks to capture **complex artistic patterns**.  
- 2 upsampling layers to restore image size.  
- Final layer generates Monet-style images.  

### Discriminator (PatchGAN)  
- PatchGAN architecture classifies images as **real or fake**.  
- Discriminator loss ensures high-quality style transfer.  
- Convolutional weights are initialized using a **normal distribution**.  

---
## 3. Loss Functions and Optimizers  

- Cycle consistency loss ensures the translated image can be **converted back** to the original image.  
- Identity loss helps retain original image content when mapping between domains.  
- Loss hyperparameters:  
  - Lambda cycle: `10`  
  - Lambda identity: `5`  
- Adam optimizer is used for both **generator and discriminator** with:  
  - Learning rate: `0.0002`  

---
## 4. Model Training  

- The model was trained for **200 epochs**.  
- Checkpoints were saved periodically to retain the best model.  
- Early stopping was applied to **prevent overfitting**.  
- Loss curves were plotted to monitor training progress.  

---
## 5. Output Generation  

- Once training was complete, an **output folder** was generated with transformed Monet-style images.  
- These images were evaluated using the **evaluation script**:  
  ```bash
  266_LAB_1_PART_3_EVALUATION.ipynb

---
## 6. Conclusion  

- The model was trained multiple times with various learning rate, lambda cycle and lambda identity values.

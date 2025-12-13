# FoodNet

FoodNet benchmark for food image classification using lightweight CNNs (MobileNetV3, EfficientNet-B0, ResNet18). Includes transfer learning, training/evaluation pipeline, confusion matrices, and inference-time comparison on a 34-class food image dataset.


## ✨ Features
- Comparative analysis of MobileNetV3, EfficientNet-B0, ResNet18 for offline CPU inference
- Pretrained models fine-tuned on food-101 or custom 34-class dataset
- Training scripts with Weights & Biases logging
- Model evaluation: accuracy, F1-score, inference latency
- Confusion matrices and performance tables

## 📊 Results (20 Epochs, GPU Training)

| Model          | Test Acc | Val Acc (Best) | Inference (ms/img) | Trainable Params (M) |
|----------------|----------|----------------|-------------------|---------------------|
| MobileNetV3   | **68.08%** | 69.61%        | **6.56**         | 1.55               |
| EfficientNet-B0 | **77.68%** | **80.50%**   | 11.04            | 4.05               |
| ResNet18      | 66.46%     | 67.60%        | 8.95             | 11.19              |

**Key Takeaways:**
- EfficientNet-B0 dominates accuracy (77.68% test) with strong generalization
- MobileNetV3 fastest inference (6.56ms) at 68% accuracy - best CPU deployment
- ResNet18 balanced but lags in accuracy despite most parameters



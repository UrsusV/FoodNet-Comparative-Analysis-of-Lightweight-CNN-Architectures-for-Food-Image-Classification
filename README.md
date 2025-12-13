# FoodNet

FoodNet benchmark for food image classification using lightweight CNNs (MobileNetV3, EfficientNet-B0, ResNet18). Includes transfer learning, training/evaluation pipeline, confusion matrices, and inference-time comparison on a 34-class food image dataset.


## ✨ Features
- Comparative analysis of MobileNetV3, EfficientNet-B0, ResNet18 for offline CPU inference
- Pretrained models fine-tuned on food-101 or custom 34-class dataset
- Training scripts with Weights & Biases logging
- Model evaluation: accuracy, F1-score, inference latency
- Confusion matrices and performance tables

## 📊 Results (20 Epochs, GPU Training + Inference)

| Model          | Test Acc | Val Acc (Best) | Inference (ms/img) | Trainable Params (M) |
|----------------|----------|----------------|-------------------|---------------------|
| **EfficientNet-B0** | **77.68%** | **80.50%**   | **4.93**         | 4.05               |
| MobileNetV3   | 68.08%     | 69.61%        | 5.64             | 1.55               |
| ResNet18      | 66.46%     | 67.60%        | 5.37             | 11.19              |

**Key Takeaways:**
- **EfficientNet-B0 is the clear winner**: Highest accuracy + fastest inference
- All models under 6ms/image → **Real-time capable** (170+ FPS on GPU)
- MobileNetV3: Most parameter-efficient for edge deployment


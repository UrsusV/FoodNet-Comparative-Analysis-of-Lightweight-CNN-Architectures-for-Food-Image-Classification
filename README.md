# FoodNet

FoodNet benchmark for food image classification using lightweight CNNs (MobileNetV3, EfficientNet-B0, ResNet18). Includes transfer learning, training/evaluation pipeline, confusion matrices, and inference-time comparison on a **34-class food dataset** [dataset](https://www.kaggle.com/datasets/harishkumardatalab/food-image-classification-dataset).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GPU Training](https://img.shields.io/badge/GPU%20Training-✅-green.svg)](https://pytorch.org/)
[![Real-time Inference](https://img.shields.io/badge/Inference%20<6ms-✅-blue.svg)](https://github.com/yourusername/FoodNet)

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

## 🚀 Quick Start

```bash
git clone https://github.com/yourusername/FoodNet.git
cd FoodNet

# Install dependencies (GPU recommended)
pip install -r requirements.txt

# Download dataset (23,878 images, 34 classes)
kaggle datasets download -d harishkumardatalab/food-image-classification-dataset
unzip food-image-classification-dataset.zip -d data/

# Train EfficientNet-B0 (resumes from checkpoint if exists)
python train.py --model efficientnet_b0 --epochs 20 --wandb --device cuda

# Evaluate all models
python evaluate.py --data_path data/

# Single image inference
python infer.py --image_path test_images/pizza.jpg --model efficientnet_b0

# View results
cat runs/model_comparison.csv



# Plant Disease Detector — MobileNetV2

A lightweight deep learning model that identifies plant diseases from leaf images. Built for mobile and edge deployment.

## Model

- **Architecture:** MobileNetV2 (ImageNet pretrained, fine-tuned)
- **Training dataset:** PlantVillage (~54,000 images, 38 classes)
- **Validation accuracy:** 99.36%
- **Weighted F1 score:** 0.9943
- **Image size:** 160 × 160
- **Parameters:** ~2.4 M (mobile-friendly, ~10 MB)
- **Classes:** 38 disease types across 14 crops (Apple, Blueberry, Cherry, Corn, Grape, Orange, Peach, Pepper, Potato, Raspberry, Soybean, Squash, Strawberry, Tomato)

## Why MobileNetV2?

MobileNetV2 is designed for resource-constrained devices. It uses depthwise-separable convolutions and inverted residual blocks to deliver high accuracy at a fraction of the size and compute cost of larger models like ResNet or EfficientNet — making it ideal for on-device inference on smartphones and edge devices.

## Setup

### 1. Install Python 3.12

Download from <https://www.python.org/downloads/release/python-3128/> (Python 3.13+ is not supported by TensorFlow yet).

During installation, check **"Add python.exe to PATH"**.

### 2. Create virtual environment and install dependencies

```bash

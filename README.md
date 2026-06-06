# Plant Disease Detector — MobileNetV2

A lightweight deep learning model that identifies plant diseases from leaf images. Built for mobile and edge deployment.

## Model

- **Architecture:** MobileNetV2 (ImageNet pretrained, fine-tuned)
- **Training dataset:** PlantVillage (~54,000 images, 38 classes)
- **Validation accuracy:** 99.36%
- **Weighted F1 score:** 0.9943
- **Image size:** 160 × 160
- **Parameters:** ~2.4 M (mobile-friendly, ~28 MB)
- **Classes:** 38 disease types across 14 crops (Apple, Blueberry, Cherry, Corn, Grape, Orange, Peach, Pepper, Potato, Raspberry, Soybean, Squash, Strawberry, Tomato)

## Why MobileNetV2?

MobileNetV2 is designed for resource-constrained devices. It uses depthwise-separable convolutions and inverted residual blocks to deliver high accuracy at a fraction of the size and compute cost of larger models like ResNet or EfficientNet — making it ideal for on-device inference on smartphones and edge devices.

## Setup

### 1. Install Python 3.12

Download from <https://www.python.org/downloads/release/python-3128/> (Python 3.13+ is not supported by TensorFlow yet).

During installation, check **"Add python.exe to PATH"**.

### 2. Create virtual environment and install dependencies

```bash
py -3.12 -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Download the trained model

The model file (~28 MB) is hosted on Hugging Face:

**Direct download:**  
https://huggingface.co/ashikaasriarun/MobileNet-V2-PlantVillage/resolve/main/best_mnv2_pv_original.keras

**Model page:**  
https://huggingface.co/ashikaasriarun/MobileNet-V2-PlantVillage

### 4. Run the app

```bash
python app.py
```

Open <http://127.0.0.1:7860> in your browser. Upload a leaf image to get a disease prediction.

## Files

| File | Description |
|---|---|
| `app.py` | Gradio interface for live inference |
| `labels_pv_original.json` | Class index → name mapping (38 classes) |
| `requirements.txt` | Python dependencies |
| `best_mnv2_pv_original.keras` | Trained model weights (download from Hugging Face) |

## Performance Comparison

MobileNetV2 achieves 99.36% accuracy at ~25% the size of larger models, with comparable performance.

| Model | Accuracy | F1 Score | Size (INT8 TFLite) |
|---|---|---|---|
| **MobileNetV2** | **99.36%** | **0.9943** | **~3 MB** |
| EfficientNet-B0 | 99.71% | 0.9972 | ~5 MB |

## License

MIT — see [LICENSE](LICENSE).

## Citation

If you use this model in your research, please cite the original PlantVillage dataset:

> Mohanty, S. P., Hughes, D. P., & Salathé, M. (2016). Using deep learning for image-based plant disease detection. *Frontiers in Plant Science*, 7, 1419.

# AI Technologies Labs (Технологии искусственного интеллекта)

This repository contains coursework labs for the **AI Technologies** class.

## Labs
- **Lab 1.1 — Mixed Precision Training (MNIST)**  
  Speed up training without losing accuracy by comparing:
  - FP32 compute + FP32 weights (baseline)
  - FP16 compute + FP32 weights (AMP / mixed precision)
  - FP16 compute + FP16 weights (aggressive)

  [Open in Colab]([https://colab.research.google.com/](https://colab.research.google.com/drive/1FDBppNsRYeGGccc58GdenNuWbdgq-E8o?authuser=0#scrollTo=flKjfk0QQTO7)) → use `labs/lab1.1-mixed-precision/mnist_precision_colab.ipynb` or copy the code from the lab README.

- **Lab 1.2 — Mixed Precision for Semantic Segmentation (Vaihingen)**  
  Download the dataset from Kaggle: `https://www.kaggle.com/datasets/naydex/vaihingen-cropped`.  
  Compare:
  - FP32 compute + FP32 weights (baseline)
  - FP16 compute + FP32 weights (AMP / mixed precision)

  **Metrics:** Accuracy, IoU, Categorical Cross-Entropy, epoch time, throughput (img/s), peak CUDA memory, training stability.  
  **Notes:** Keep arrays as `uint8` in RAM and scale to `[0,1]` on the fly to save ~4× memory; consider chunked loading; U-Net is sufficient (or try VGG16/EfficientNet-B0/ConvNeXt-Small backbones).  
    [Open in Colab]([https://colab.research.google.com/](https://colab.research.google.com/drive/1FDBppNsRYeGGccc58GdenNuWbdgq-E8o?authuser=0#scrollTo=flKjfk0QQTO7)) → use `labs/lab1.2-segmentation/` notebook or run the training script below.

## Quickstart (local)
```bash
make setup
make amp   # or: make fp32 / make fp16

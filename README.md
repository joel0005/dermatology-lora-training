**Dermatology Clinical LoRA – Stable Diffusion Fine-Tuning**
**Overview**

This project demonstrates parameter-efficient fine-tuning (LoRA) of Stable Diffusion v1.5 to generate synthetic dermatological pathology images.

**The objective was to:**

Learn domain-specific visual features (inflammatory lesions, erythema, pustules)

Preserve base model knowledge

Avoid full model retraining

Maintain lightweight and modular deployment

The resulting LoRA adapter enables controlled synthesis of dermatological imagery while keeping the base model unchanged.

Model Architecture

**Base Model:**
Stable Diffusion v1.5 (pruned)

**Fine-Tuning Method:**
LoRA (Low-Rank Adaptation)

**Training Framework:**
kohya_ss (sd-scripts)

**Image Resolution:**
512 × 512

**LoRA Rank (network_dim):**
16

**Alpha:**
16

**Learning Rate:**
1e-4

**Batch Size:**
4

**Epochs:**
3

**Mixed Precision:**
FP16

Why LoRA Instead of Full Fine-Tuning?

Full fine-tuning modifies hundreds of millions of parameters, increasing memory usage and deployment size.

**LoRA:

Freezes base model weights

Injects low-rank matrices into attention layers

Reduces trainable parameters dramatically

Produces lightweight adapters (~5–50MB)**

**This allows:**

Faster experimentation

Efficient GPU utilization

Modular deployment

Reusability across multiple checkpoints

Training Framework: kohya_ss (sd-scripts)

Training was performed using kohya_ss, a widely adopted Stable Diffusion fine-tuning framework.

**Repository:**
https://github.com/kohya-ss/sd-scripts

**To clone:**

git clone https://github.com/kohya-ss/sd-scripts.git

**Why kohya_ss?**

Native LoRA support

Memory-efficient training (FP16, xformers)

Fine-grained hyperparameter control

Industry-standard for SD 1.5 and SDXL training

Compatible with DreamBooth + LoRA workflows

kohya_ss enables reproducible, controlled, and production-aligned fine-tuning.

**Dataset Structure**
data/
└── 1_derm/
    ├── image1.jpg
    ├── image1.txt
    ├── image2.jpg
    ├── image2.txt


Each image has a corresponding caption file describing clinical attributes and visual features.

Example caption:

clinical dermatology photograph, severe inflammatory skin lesions, erythema, pustules, medical photography

**Training Command**

See train_command.txt for the full training command used.

**Ethical Disclaimer**

This project generates synthetic dermatological imagery for research and experimentation purposes only.

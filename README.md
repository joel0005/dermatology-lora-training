Dermatology Clinical LoRA – Stable Diffusion Fine-Tuning
* Overview

This project demonstrates parameter-efficient fine-tuning (LoRA) of Stable Diffusion v1.5 to generate synthetic dermatological pathology images.

The objective was to:

Learn domain-specific visual features (inflammatory lesions, erythema, pustules)

Preserve base model knowledge

Avoid full model retraining

Maintain lightweight deployment

* Model Architecture

Base Model:

Stable Diffusion v1.5 (pruned)

Fine-tuning Method:

LoRA (Low-Rank Adaptation)

Training Framework:

kohya_ss

Resolution:

512 × 512

LoRA Rank:

16

Alpha:

16

Learning Rate:

1e-4

Batch Size:

4

Epochs:

3

Mixed Precision:

FP16

* Dataset Structure
data/
└── 1_derm/
    ├── image1.jpg
    ├── image1.txt
    ├── image2.jpg
    ├── image2.txt


Each image has a caption file describing clinical attributes.

* Training Command

See train_command.txt for full command used.

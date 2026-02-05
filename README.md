# TexMobile: A Texture-Aware Lightweight Framework for Campus Scene Classification

TexMobile is a hierarchical, lightweight deep learning framework designed for fine-grained classification in complex campus environments. It addresses the challenges of visual variability and semantic ambiguity by combining global scene context with local texture encoding.

## 🚀 Key Features
* **Hierarchical Architecture**: Employs a dual-head system that jointly models coarse-level (Object vs. Scene) and fine-grained categories.
* **Texture-Aware**: Integrates a Deep Texture Encoding Network (DeepTEN) to capture subtle material cues essential for distinguishing visually similar environments like buildings and laboratories.
* **Lightweight Backbone**: Built on **MobileNetV2**, making it efficient for resource-constrained environments while maintaining high accuracy.
* **Multi-Task Learning**: Uses a weighted joint loss to balance global semantic structure and fine-grained categorization during training.

## 📊 Performance

| Model | Params | Test Accuracy |
| :--- | :--- | :--- |
| MobileNetV2 (Vanilla) | ~2.2 M | 93.42% |
| DenseNet 121 | ~8.0 M | 94.18% |
| GoogleNet | ~6.6 M | 96.69% |
| **Ours (TexMobile)** | **~2.4 M** | **98.07%** |

## 📂 Dataset: Campus Scene Dataset
The framework was validated using a custom dataset collected at the **University of Jordan**, consisting of 2,405 images.

* **Coarse Classes**: Objects, Scenes.
* **Fine-Grained Classes**: Building, Lab, Car, Person, Tree.
* **Data Split**: 70% Training, 15% Validation, 15% Testing.

## 🛠️ Implementation Details
* **Framework**: PyTorch
* **Optimizer**: AdamW with a weight decay of $5 \times 10^{-4}$
* **Learning Rate**: Differential strategy ($1 \times 10^{-5}$ for backbone, $1 \times 10^{-4}$ for heads) with Cosine Annealing.
* **Preprocessing**: Images resized to $224 \times 224$ and normalized using ImageNet statistics.

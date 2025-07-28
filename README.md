# ViT for Image Classification – Deepfake Detection

This project applies a pre-trained Vision Transformer (ViT) model to detect deepfake images using the **FaceForensics++** dataset. The goal is to classify images as either **real** or **fake**, extracted from videos using OpenCV.

---

## Dataset

* **Source**: [FaceForensics++ (FF++)](https://github.com/ondyari/FaceForensics)

* **Structure**:

  ```
  FF++/
  ├── real/   # Videos of genuine faces
  └── fake/   # Deepfake-generated videos
  ```

* **Download Method**: [kagglehub](https://github.com/danielgatis/kagglehub)

---

## Frame Extraction

* Used **OpenCV** to extract multiple frames per video.
* Saved images in the following format:

  ```
  /kaggle/working/frames/
  ├── real/
  └── fake/
  ```

---

## Data Preparation

* Built a **custom PyTorch `Dataset` class** to load the extracted image frames.
* Utilized the `ViTFeatureExtractor` (from HuggingFace) to preprocess images before feeding them into the model.

---

## Model Finetuning

* **Base Model**: `google/vit-base-patch16-224-in21k`
* **Modifications**:

  * Replaced the classifier head for **binary classification** (real vs. fake).
* **Finetuning**:

  * Used HuggingFace’s `Trainer` API to train on the extracted dataset.
  * Applied standard training techniques with appropriate metrics (accuracy, F1 score).

---

## Evaluation

* Evaluated on a validation split of the dataset.
* Achieved:

  * **Accuracy**: \~75%
  * **F1 Score**: \~0.79

---

## Technologies Used

* Python
* PyTorch
* OpenCV
* HuggingFace Transformers
* Kaggle Notebooks

---

## Future Work

* Fine-tune hyperparameters for improved performance.


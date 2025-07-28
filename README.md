# ViT-for-image-classification

Dataset Download
Used kagglehub to download the FaceForensics dataset.
The dataset contains videos in FF++/real and FF++/fake folders.
Frame Extraction
Extracted multiple frames from each video using OpenCV.
Saved frames as images in /kaggle/working/frames/real and /kaggle/working/frames/fake.
Data Preparation
Created a custom PyTorch Dataset to load the extracted images.
Used the HuggingFace ViT processor for image preprocessing.
Model Finetuning
Loaded a pre-trained ViT model (google/vit-base-patch16-224-in21k) from HuggingFace.
Replaced the classifier head for binary classification (real/fake).
Finetuned the model on the extracted image dataset using HuggingFace’s Trainer API.
Evaluation
Evaluated the model on a validation set.
Achieved around 75% accuracy and 0.79 F1 score on the validation set.

Technologies Used
Python, PyTorch, OpenCV
HuggingFace Transformers
Kaggle Notebooks

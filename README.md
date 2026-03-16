# Video-Classification-Using-UCF101

This project focuses on human action recognition using the UCF101 dataset. It follows a complete workflow for preparing video data for classification, including dataset download, extraction, optional synthetic data generation, reduced dataset creation, frame extraction, preprocessing, label encoding, and train-test splitting.

## Project Overview

The aim of this project is to build a video classification pipeline for recognizing human actions from video clips. Since the full UCF101 dataset is large, the project also includes a lightweight approach by selecting a reduced subset of classes and videos for easier experimentation and training.

The workflow prepares video data in a format suitable for deep learning models such as 3D CNNs and CNN-LSTM architectures.

## Dataset

This project uses the **UCF101 dataset**, a standard benchmark dataset for human action recognition.

**Official dataset link:**  
https://www.crcv.ucf.edu/research/data-sets/ucf101/

### Dataset Details
- 101 human action classes
- 13,320 video clips
- Real-world action videos collected from YouTube
- Commonly used for video classification and action recognition research

Examples of action categories include walking, running, diving, playing instruments, and sports-related actions.

## Project Workflow

The project follows these main steps:

1. Download and extract the UCF101 dataset
2. Optionally create a synthetic dataset for low-resource experimentation
3. Create a reduced dataset by selecting a smaller number of classes and videos
4. Extract a fixed number of frames from each video using OpenCV
5. Resize frames to a uniform resolution
6. Store extracted frames as NumPy arrays
7. Encode class labels using `LabelEncoder`
8. Split the dataset into training and testing sets
9. Prepare model input in the form  
   `(batch_size, num_frames, height, width, channels)`
10. Train the data using a suitable deep learning architecture

## Preprocessing

The preprocessing pipeline includes:

- reading videos using OpenCV
- extracting frames from each video
- resizing frames to fixed dimensions
- selecting a fixed number of frames per video
- converting video data into NumPy arrays
- normalizing pixel values if required
- encoding class labels into numeric form

This ensures consistency in the input data before training.

## Model Preparation

The processed data is prepared for deep learning models commonly used in action recognition, such as:

- **3D CNNs** for capturing spatial and temporal features together
- **2D CNN + LSTM** models for extracting spatial features frame by frame and learning temporal dependencies across frames

Labels can also be one-hot encoded for multi-class classification.

## Evaluation

Typical evaluation metrics for this task include:

- Accuracy
- Confusion Matrix
- Precision
- Recall
- F1 Score

For inference, new videos can be processed using the same frame extraction and preprocessing pipeline before being passed to the trained model for prediction.

## Files in This Repository

- `VCU.ipynb` — notebook implementation
- `vcu.py` — Python script version
- output files/images — sample results
- `report.pdf` — project report
- `README.md` — project documentation

Update the file names above if your actual file names are different.

## Technologies Used

- Python
- Google Colab
- OpenCV
- NumPy
- scikit-learn
- TensorFlow / PyTorch

## Conclusion

This project demonstrates a structured approach to video action recognition using the UCF101 dataset. It covers the essential preprocessing and data preparation steps needed before model training and provides a practical foundation for building deep learning-based video classification systems.
## **Table of Contents**
1. [Project Overview](#overview)
2. [Dataset](#dataset)
3. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4. [Preprocessing](#preprocessing)
5. [Data Augmentation](#data-augmentation)
6. [Model Architecture](#model-architecture)
7. [Application](#application)
8. [Tech Stack](#tech-stack)
9. [Contributors](#contributors)
10. [Acknowledgments](#acknowledgments)

## **Project Overview**
This project focuses on building an app classifying infant cries into four categories: hungry, belly pain, discomfort, and tired. It leverages the power of deep learning to understand and differentiate the subtle nuances in infant cries, providing insights that could be invaluable for parents.

## **Dataset**
The primary dataset used is the Donate a Cry Corpus, supplemented with additional data collected from Mendeley Data and YouTube.

Donate-A-Cry-Corpus: [**dataset**](https://github.com/gveres/donateacry-corpus)

## **Exploratory Data Analysis (EDA)**
A comprehensive EDA was conducted to understand the characteristics of the audio data, including:
- Sampling rate and average duration for each class.
- Detailed analysis of the average mel spectrogram, average number of harmonics, average magnitude, and average frequency for each cry class.

## **Preprocessing**
To enhance model performance, a bandpass filter was applied during preprocessing to focus on the most prevalent frequencies observed in the mel spectrograms. This step is crucial for reducing noise and improving the clarity of features relevant to classification.

For more info on BandPass Filter, look through this documentation: [**audiomentation**](https://iver56.github.io/audiomentations/)

## **Data Augmentation**
Given the limited size of the dataset, several augmentation techniques were employed to enrich the data, including Time Stretch, Background Noise, and Pitch Shift. These methods help to simulate a wider range of crying scenarios, thereby improving the robustness of the model.

## **Models used**
The project utilized the **Audio Spectrogram Transformer (AST)** as the primary model due to its state-of-the-art performance in audio classification tasks. In addition to AST, subsidiary experiments were conducted with other models such as **VGG16 (using MFCC features)**, **a Multi-input layer DNN (with inputs from the YAMnet model)**, and **U-net (trained on unlabeled data using reconstructive loss)**. These exploratory models provided valuable insights, though **AST** remained the best performer.

**Pretrained Models Used**
>1. Audio Spectrogram Transformers(AST): [**AST HuggingFace**](https://huggingface.co/docs/transformers/model_doc/audio-spectrogram-transformer)
>2. YAMnet: [**YAMnet Kaggle**](https://www.kaggle.com/models/google/yamnet/frameworks/tfLite/variations/classification-tflite/versions/1?tfhub-redirect=true)

## **Application**
<p align="center">
  <img src="https://github.com/Haikoo96/aiffelton_babycry_classification/blob/main/app_process.png" />
</p>
The app was developed to analyze infant cries in real-time. The model runs on a local pc server(localhost), with inference data sent to the client side using FastAPI and ngrok. The image above describes the process of the app.

#### **APP DEMO VIDEO**
[**APP DEMO VIDEO LINK**](https://youtube.com/shorts/CRE3qGju1T0?feature=share)
- Bear in mind that the video is in Korean


## **Tech Stack**
- PyTorch
- Librosa
- Transformers(HuggingFace)
- TensorFlow
- FastAPI
- Ngrok
- Flutter

## **Contributors**
- **Imgu Khang(Project Lead) ([github link](https://github.com/knggu))**: Modeling
- **Youngjin Kim ([github link](https://github.com/passgiant))**: Server-Side (Backend) Development
- **Philsun Jo ([github link](https://github.com/CHOPHILSUN))**: App Development
- **Dave(Me)**: Modeling, EDA, Preprocessing

## **Acknowledgments**
Special thanks to ModuLabs ([modulabs](https://modulabs.co.kr/)) for providing an opportunity to this project.



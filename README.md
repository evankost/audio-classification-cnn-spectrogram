# Audio Classification using CNN and Mel-Spectrograms

This repository contains a neural network pipeline for classifying music genres. The project transitions from a baseline Feedforward Neural Network (FNN) using Mel-frequency cepstral coefficients (MFCCs) to a Convolutional Neural Network (CNN) architecture using Mel-Spectrograms.

## Feature Extraction: MFCC vs. Mel-Spectrograms

### Mel-frequency Cepstral Coefficients (MFCCs)
MFCCs represent the short-term power spectrum of audio. They are derived by taking the log of the power spectrum, mapping it to the mel scale, and performing a discrete cosine transform. This results in a compressed representation of the spectral envelope, typically used as a 1D input for standard neural networks.


### Mel-Spectrograms
A Mel-Spectrogram visualizes the frequency spectrum over time, mapped to the Mel scale. This project uses Mel-Spectrograms as 2D inputs, allowing the CNN to detect spectral and temporal patterns simultaneously through convolutional filters.


## Implementation Details
* **Feature Processing:** Audio is processed into segments and converted to Mel-Spectrograms using the Librosa library.
* **Architecture:** The model is a CNN utilizing Batch Normalization and Dropout layers for regularization.
* **Inference:** The pipeline includes a utility using `yt-dlp` to download and process audio from YouTube for external validation.

## Model Performance
The CNN model achieved higher theoretical accuracy and F1 scores on the test set compared to the FNN baseline. These results confirm that the convolutional architecture is more effective at capturing the structural dependencies within the training distribution.

## Results and Analysis
Real-world testing showed high accuracy for rhythmic genres like **Hip-Hop**. However, performance was inconsistent for **Blues** and **Classical** tracks. This suggests that while the CNN identifies spectral patterns effectively, its generalization is limited by the variety of the training data.

## License

This project is licensed under the MIT License.
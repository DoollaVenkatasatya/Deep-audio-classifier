# Deep-audio-classifier
Audio classifying using machine learning

Dataset link: https://www.kaggle.com/datasets/kenjee/z-by-hp-unlocked-challenge-3-signal-processing

![dac](https://github.com/DoollaVenkatasatya/Deep-audio-classifier/assets/137089784/65e19076-3ade-47f9-8c3a-0d1765a9e4f3)


This repository is a detailed script for processing audio data, training a model, making predictions, and exporting the results to a CSV file. This script is designed for a binary audio classification task where we are trying to detect specific sounds (capuchin calls) within forest recordings. Here's an overview of what the script does:

Data Preparation:

Audio files are loaded from two different folders (POS and NEG).
A preprocess function is defined to load, preprocess, and convert audio files to spectrograms for model input.
The positive and negative samples are combined into a single dataset called data.
Data augmentation techniques like caching, shuffling, batching, and prefetching are applied to enhance training efficiency.

Model Building:

A CNN-based model is constructed using TensorFlow's Keras API.
The model includes convolutional layers, max-pooling layers, and dense layers.
The model is compiled with the 'Adam' optimizer and appropriate loss and metrics for binary classification.

Training the Model:

The model is trained using the train_data dataset for a specified number of epochs.
Training metrics, such as accuracy, loss, precision, and recall, are tracked and plotted.

Making Predictions on Test Data:

A sample batch of test data is used to make predictions using the trained model.
Predictions are thresholded (0.5) to convert logits to class labels.
The ground truth labels are extracted from the test data.

Converting MP3 to WAV:

Additional functionality is provided to convert MP3 files to WAV format.
This is useful for preparing the audio data to be fed into the model.

Predicting on Forest Recordings:

Forest recordings (in WAV format) are loaded from a specified folder.
Each recording is split into audio slices for prediction.
The model predicts on these audio slices, and the results are collected.

Post-Processing and Result Export:

The predictions are post-processed using a threshold of 0.99.
The post-processed results (the number of detected calls) are collected for each recording.
The results are exported to a CSV file named "results.csv" for easier access.



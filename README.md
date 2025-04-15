SignalAndSystemProject

Music genre recognition using concepts from Signals and Systems lessons
📂 Project Structure

    Augmentation Audios: Module related to applying audio effects to the dataset

    FeatureExtract: Responsible for extracting audio features and converting the data to .csv

    Model: XGBoost

🔍 Feature Extraction

The feature extraction process is divided into three main domains:
1️⃣ Time Domain
🔹 Low-Level Features

    Energy: Measures the total energy of the signal within a given time interval.

    Zero-Crossing Rate: Indicates the rate at which the audio signal crosses zero.

    Amplitude Envelope: Represents the variation of amplitude over time.

🔹 High-Level Features

    Tempo (Rhythm): Determines the main pulse of the audio, useful for rhythmic analysis.

2️⃣ Frequency Domain
🔹 Low-Level Features

    Mean of Weighted Frequencies: Calculates the average frequency, weighted by the amplitude of each sample within each analysis frame using the Fast Fourier Transform (FFT).

    Bandwidth: Measures the "spread" of the audio spectrum in each frame.

🔹 High-Level Feature

    MFCC (Mel-Frequency Cepstral Coefficients): Extracts the Mel-frequency cepstral coefficients, calculating statistics such as mean and standard deviation.

3️⃣ Features from Spectrogram Images

In addition to features extracted directly from the audio signals, the project also analyzes spectrogram images to extract descriptors based on Histogram of Oriented Gradients (HOG).
🔹 HOG Extraction from Spectrograms

The get_hog(spectrogram) method performs the following steps:

    Resizes the spectrogram image.

    Computes the Histogram of Oriented Gradients (HOG).

    Returns statistics from the extracted features.

🏋️ Model

The model performs the following:
🎲 Data Loading and Visualization

    Using pandas, the CSV file is loaded and visualized as a table, helping to understand the structure and characteristics of the data.

    Then, a preprocessing step normalizes the data and maps the class labels to numeric values.

🔍 Exploratory Data Analysis

    Through various plots, an exploratory analysis of the data is conducted, displaying genre-wise average Time, RMS, and Amplitude Envelope in bar charts.

    A confusion matrix is then used to evaluate the accuracy of the model's predictions.

🤖 Modeling and Evaluation

    Prepares the dataset and splits it into training (80%) and testing (20%) sets.

    Trains a GradientBoostingClassifier model.

    Evaluates accuracy and feature importance.

How to Run

    Change the default directory variable named "path_root" or "new_path" to the directory containing the "Data" folder available at:
    https://drive.google.com/drive/folders/1vxzl9tmki-r60igYsUWLxvowS1Rzasab?usp=sharing
    Make a copy of this folder to your personal workspace.

    You don’t need to run the FeatureExtract or Augmentation modules, as the processed data is already provided in this folder.

    All necessary visualizations are available in the Model.ipynb notebook.

If you encounter any issues, please contact mas11@cin.ufpe.br.

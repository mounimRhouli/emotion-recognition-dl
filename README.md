
# Face-Expression-Recognition-using-Deep-Learning

This project implements a convolutional neural network (CNN) to recognize facial expressions across seven categories: angry, disgust, fear, happy, neutral, sad and surprise. The model is trained on a face expression recognition dataset (FER-style layout).

Dataset (example source): https://www.kaggle.com/datasets/jonathanoheix/face-expression-recognition-dataset

## Requirements

- Python 3.11
- keras~=2.12.0rc0
- tensorflow
- numpy~=1.23.5
- matplotlib~=3.7.0
- pandas~=1.5.3
- seaborn
- opencv-contrib-python==4.7.0.68

See `requirements.txt` for the full list used during development.

## Installation

1. Install Python (3.11 recommended).
2. Create and activate a virtual environment and install dependencies:

```powershell
python -m venv .venv
.\\.venv\\Scripts\\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Usage

1. Clone or download the repository.
2. Install dependencies.
3. Run the real-time detector:

```powershell
python .\\main.py
```

The script launches the default webcam and performs real-time emotion detection. Press `q` to exit the application.

## Files

1. `main.py` — Entry point for real-time inference. Loads `model.h5` and the Haar cascade XML to detect faces and predict emotions via webcam.
2. `emotion_recognition_cnn.py` — Training script that defines, compiles and trains the CNN using Keras ImageDataGenerator. Saves the best model to `model.h5`.
3. `HaarcascadeclassifierCascadeClassifier.xml` — Haar Cascade XML for frontal face detection (OpenCV format).
4. `model.h5` — Keras model file containing trained weights (binary).
5. `requirements.txt` — Dependency manifest.

## Dataset layout (expected for training)

The training script expects a dataset with the following folder structure:

```
face-expression-recognition-dataset/images/
  train/<emotion_label>/*.jpg
  validation/<emotion_label>/*.jpg
```

## Model and training notes

- Input images are processed as 48x48 grayscale images.
- Training uses Keras callbacks including ModelCheckpoint, EarlyStopping and ReduceLROnPlateau. Default training parameters in the script: `batch_size=128`, `epochs=48`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


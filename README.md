# Brain Tumor Detection

A Flask-based brain tumor classification web app built with Keras/TensorFlow. The app loads a trained CNN model, accepts uploaded MRI images, and returns a prediction of whether a brain tumor is present.

## Project Structure

- `temp/`
  - `app.py` - Flask web application entrypoint
  - `mainTrain.py` - model training script for dataset images
  - `mainTest.py` - standalone script for testing a saved model on a single image
  - `BrainTumor10Epochs.h5` - trained model used by `app.py`
  - `BrainTumor10EpochsCategorical.h5` - trained model saved by `mainTrain.py`
  - `datasets/` - labeled image folders for training
    - `no/` - images without tumors
    - `yes/` - images with tumors
  - `uploads/` - folder where uploaded images are saved by the app
  - `static/` - CSS and JavaScript assets
  - `templates/` - Flask HTML templates

## Features

- Upload MRI image through browser UI
- Predicts `No Brain Tumor` or `Yes Brain Tumor`
- Uses a CNN trained on 64x64 RGB images
- Web UI built using Bootstrap and jQuery

## Requirements

- Python 3.x
- TensorFlow / Keras
- OpenCV (`opencv-python`)
- Pillow
- Flask
- Werkzeug
- scikit-learn

## Installation

1. Create and activate a Python virtual environment.
2. Install dependencies:

```bash
pip install tensorflow keras opencv-python pillow flask werkzeug scikit-learn
```

## Running the App

1. Ensure the trained model file `temp/BrainTumor10Epochs.h5` exists.
2. Run the Flask app from the `temp/` folder:

```bash
cd "c:\Users\yash kadole\Desktop\Brain tumor detection\temp"
python app.py
```

3. Open `http://127.0.0.1:5000/` in your browser.
4. Upload a `.png`, `.jpg`, or `.jpeg` image and click `Predict!`.

## Training the Model

If you want to retrain or extend the dataset:

```bash
cd "c:\Users\yash kadole\Desktop\Brain tumor detection\temp"
python mainTrain.py
```

This reads images from `temp/datasets/no/` and `temp/datasets/yes/`, trains a CNN for 10 epochs, and saves a model as `BrainTumor10EpochsCategorical.h5`.

## Testing a Saved Model

Use `mainTest.py` to test a saved model on a single hard-coded image path. Update the image path and run:

```bash
python mainTest.py
```

## Notes

- `app.py` currently loads `BrainTumor10Epochs.h5`.
- The training script saves `BrainTumor10EpochsCategorical.h5`; verify the correct model file for your deployment.
- Uploaded images are stored in `temp/uploads/`.

## License

This repository does not include a license file. Add one if you plan to share or publish the project.

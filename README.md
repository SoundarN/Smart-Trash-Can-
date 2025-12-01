# 🗑️ Smart Trash Can – AI-Based Waste Classification & Management

This project implements an AI-powered Smart Trash Can that automatically classifies waste using a deep learning model and helps automate waste management. It uses TensorFlow, OpenCV, MongoDB, and optional ESP32/Arduino hardware for real-time classification, storage, and automated actions.

⭐ Key Features

Real-Time Waste Classification using a trained MobileNet-based model.

Image Capture Support through a webcam (OpenCV).

MongoDB Storage for saving images, predictions, timestamps, and confidence scores.

Hardware Automation (Optional) using Serial communication (ESP32/Arduino).

Dataset Handling with automated split using splitfolders.

Model Training Scripts included (train_model.py).

Prediction & Retrieval Tools (smart_trash_can.py, retrive_image.py).

📁 Project Structure
smart_trash_can-main/
│
├── smart_trash_can.py           # Main script for prediction & classification
├── train_model.py               # Model training script
├── setup_mongodb.py             # MongoDB configuration
├── retrive_image.py             # Retrieve stored images from MongoDB
├── mongo.py                     # MongoDB connection handler
├── waste_classification_model.h5
├── best_waste_classification_model.h5
│
├── DATASET/                     # Raw dataset (images)
├── DATASET_SPLIT/               # Train/Val/Test after splitting
├── query/                       # MongoDB query outputs
│
├── test_script.py               # Testing utilities
├── README.md                    # (Your README will replace this)
└── *.spec                       # PyInstaller build files

🧠 How It Works

Camera captures an image of the waste.

The model predicts the waste category (e.g., organic, plastic, metal, paper).

Results are stored in MongoDB with:

Image (binary),

Predicted label,

Confidence level,

Timestamp.

If a microcontroller is connected, the system sends signals to automatically sort waste.

🚀 Getting Started
1. Install Dependencies
pip install tensorflow opencv-python pymongo split-folders pyserial

2. Set Up MongoDB

Edit the credentials inside setup_mongodb.py or mongo.py.

Run:

python setup_mongodb.py

3. Run Real-Time Classification
python smart_trash_can.py

4. Train the Model (Optional)
python train_model.py

🧪 Hardware Support (Optional)

The project can communicate with ESP32/Arduino via serial port to automate:

Opening lids

Sorting waste

Triggering indicators/buzzers

📊 Future Enhancements

Add IoT dashboard for remote monitoring

Add auto-sorting mechanism using servo motors

Deploy model on edge devices (ESP32-CAM, Raspberry Pi)

📝 License

Open-source for educational and non-commercial use.

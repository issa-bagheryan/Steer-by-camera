# Steering Angle Prediction (A2D2)

<sub>🚧 Work in Progress</sub>

An experimental computer vision project exploring steering angle prediction from camera images using the [Audi Autonomous Driving Dataset (A2D2)](https://www.a2d2.audi).

The goal is to train a deep learning model that can estimate a vehicle's steering-wheel angle from a single front-center camera frame. The project combines camera data with vehicle CAN-bus signals to create aligned image-label pairs for supervised learning.

Currently, the pipeline uses an ImageNet-pretrained ResNet-18 to perform steering angle regression. The notebook covers data retrieval, signal processing, timestamp alignment, preprocessing, model training, and evaluation.

### Current Pipeline

1. Retrieve camera frames and vehicle signals from the public A2D2 dataset on AWS S3.
2. Reconstruct signed steering angles from CAN-bus signals.
3. Validate steering direction against gyroscope yaw measurements.
4. Align camera timestamps with steering measurements.
5. Preprocess and resize images for training.
6. Fine-tune an ImageNet-pretrained ResNet-18.
7. Evaluate predictions against simple baseline models.

### Technical Stack

- Python
- PyTorch & Torchvision
- ResNet-18
- NumPy & Pandas
- Matplotlib
- Pillow
- Boto3 (AWS S3)
- Google Colab (NVIDIA T4 GPU)

### Current Limitations

- Training and validation currently use a single driving scene.
- Only the front-center camera is used.
- The model relies on individual frames rather than temporal information.
- Steering angle distribution is heavily imbalanced, with most observations concentrated around straight driving.
- Generalisation to unseen

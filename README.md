# Behavioral Cloning of Human Driving Behavior using Deep Learning

## Abstract

In this paper, we present a baseline workflow for behavioral cloning of human driving behavior using deep learning, specifically an end-to-end implementation. The proposed workflow involves training an artificial neural network of the convolutional type, which is then deployed on two different driving behavior models. These models are subsequently simulated in a virtual environment. The training process encompasses data collection, augmentation, preprocessing, and the training of a neural network. The trained model is then deployed onto an ego vehicle to predict steering commands based on real-time camera feed input.

**Keywords**: Autonomous Vehicles, Deep Learning, Behavioral Cloning

## I. Introduction

Behavior planning in autonomous driving involves designing high-level driving actions or maneuvers to safely achieve driving objectives under various scenarios. This planning must consider interactions with static and dynamic elements in the environment while ensuring safety and efficiency. This paper focuses on end-to-end imitation learning for autonomous driving, which has shown potential but also limitations. The study explores the behavior planning system in the context of diverse driving scenarios.

## II. Background

### Simulation System

The proposed pipeline is validated using an open-source simulator by Udacity.

### Driving Scenarios

The study involves cloning two distinct driving behaviors, basic driving, and rigorous driving, using end-to-end learning. These behaviors are tested on specialized simulated environments tailored to their characteristics.

## III. Implementation

### Training Phase

The training phase comprises data collection, augmentation, preprocessing, and neural network training.

#### Data Collection

Datasets are acquired by manually driving the ego vehicle in different scenarios. Each dataset includes timestamped frames from the center, left, and right cameras, along with corresponding steering angle measurements.

#### Data Augmentation

Various augmentation techniques are applied to the collected data, including zoom, pan, brightness, and flip, to improve the robustness of the training dataset.

#### Data Preprocessing

Images are preprocessed through scaling and standardization operations to prepare them for input into the neural network.

##### Zoom Augmentation
![Zoom Augmentation](images/zoom_augmentation.png)

##### Pan Augmentation
![Pan Augmentation](images/pan_augmentation.png)

##### Brightness Augmentation
![Brightness Augmentation](images/brightness_augmentation.png)

##### Flip Augmentation
![Flip Augmentation](images/flip_augmentation.png)

#### Data Preprocessing

##### Original vs. Preprocessed Images
![Preprocessed Images](images/preprocessed_images.png)


#### Training

The training pipeline is implemented using a Jupyter notebook. Data is shuffled, balanced, and augmented in real-time during training.

#### Neural Network Architecture

A shallow CNN architecture is adopted to predict steering angles from camera frames.

### Deployment Phase

The deployment phase involves data preprocessing and longitudinal vehicle control loop.

#### Data Preprocessing

Images are resized and normalized to prepare them for input into the trained neural network.

#### Longitudinal Vehicle Control

Throttle commands are determined based on the predicted steering angles, enabling vehicle control.

## IV. Results

The computational details, including training time and deployment latencies, are provided. Simulated field results show activation maps and demonstrate the neural network's ability to make intelligent steering predictions based on learned features.

## V. Conclusion

The paper presents a lightweight pipeline for training and deploying strong driving behavior models using end-to-end imitation learning. It emphasizes cooperative control and proposes evaluation criteria for assessing the pipeline's efficiency and resilience. Future work includes investigating hardware implementations, gathering diverse datasets, and exploring alternative techniques for generalization.

For video demonstrations of the experiments, visit [YouTube link](https://youtu.be/1K9myehD6DY).

![Activation Maps](images/activation_maps.png)

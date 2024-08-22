# CNN Autoencoder for MNIST Dataset

## Project Overview

This project implements a Convolutional Neural Network (CNN) autoencoder for the MNIST dataset, using an Encoder-Decoder architecture. The model compresses and reconstructs images from the MNIST dataset.

## Encoder Class

The `Encoder` class compresses input images into a lower-dimensional representation using three convolutional layers.

### Convolutional Layers

1. **First Convolutional Layer**:
   - **Input Channels**: 1
   - **Output Channels**: 16
   - **Kernel Size**: 3x3
   - **Stride**: 1
   - **Padding**: 1
   - **Output Size**: 16x28x28

2. **Second Convolutional Layer**:
   - **Input Channels**: 16
   - **Output Channels**: 32
   - **Kernel Size**: 4x4
   - **Stride**: 2
   - **Padding**: 1
   - **Output Size**: 32x14x14

3. **Third Convolutional Layer**:
   - **Input Channels**: 32
   - **Output Channels**: 64
   - **Kernel Size**: 16x16
   - **Stride**: 2
   - **Padding**: 1
   - **Output Size**: 64x1x1

### Forward Method

Applies ReLU activation after each convolutional layer to produce the encoded representation.

## Decoder Class

The `Decoder` class reconstructs images from the encoded representation using three transposed convolutional layers.

### Transposed Convolutional Layers

1. **First Transposed Convolutional Layer**:
   - **Input Channels**: 64
   - **Output Channels**: 32
   - **Kernel Size**: 9x9
   - **Stride**: 1
   - **Padding**: 1
   - **Output Size**: 32x9x9

2. **Second Transposed Convolutional Layer**:
   - **Input Channels**: 32
   - **Output Channels**: 16
   - **Kernel Size**: 4x4
   - **Stride**: 1
   - **Padding**: 1
   - **Output Size**: 16x12x12

3. **Third Transposed Convolutional Layer**:
   - **Input Channels**: 16
   - **Output Channels**: 1
   - **Kernel Size**: 4x4
   - **Stride**: 1
   - **Padding**: 1
   - **Output Size**: 1x15x15

### Forward Method

Applies ReLU activation after each transposed convolutional layer to reconstruct the image.

## Autoencoder Class

The `Autoencoder` class combines the `Encoder` and `Decoder` classes to perform end-to-end compression and reconstruction.

### Forward Method

Processes the input through the Encoder and then the Decoder to reconstruct the image.

## Training Process

The training process involves minimizing the reconstruction error between the original and reconstructed images.

### Steps to Train the Autoencoder

1. **Define Loss Function**:
   - Use Mean Squared Error (MSE) loss.

2. **Set Up Optimizer**:
   - Use the Adam optimizer with the autoencoder's parameters.
   
3. **Training Loop**:
   - Iterate through the dataset for a defined number of epochs.
   - For each batch, perform forward pass, compute loss, backpropagate, and update parameters.
   


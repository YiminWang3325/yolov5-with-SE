# yolov5-with-SE


## Attention Mechanism Overview

The concept of **attention mechanisms** originates from the study of **human vision** in cognitive science. Due to bottlenecks in information processing, humans selectively focus on a portion of all available information while ignoring other visible information. 

This ability stems from the fact that different parts of the human retina have different information processing capabilities—that is, different parts have different acuities. The **fovea** of the human retina has the highest acuity. To make rational use of limited visual information processing resources, humans need to select a specific part of the visual area and focus on it. 

For example, when people watch movies on a computer screen, they focus on and process the vision within the scope of the computer screen, while the vision outside the computer screen (such as the keyboard, computer background, etc.) is ignored.



## Attention Mechanisms in Neural Networks

There are many ways to introduce attention mechanisms in neural networks. Taking **convolutional neural networks (CNNs)** as an example, you can:

- **Spatial Attention**: Introduce attention mechanisms in the spatial dimension
- **Channel Attention**: Introduce attention mechanisms in the channel dimension  
- **Mixed Attention**: Add attention mechanisms in both spatial and channel dimensions simultaneously



## SE (Squeeze-and-Excitation) Block Structure

![SE Block Structure](https://user-images.githubusercontent.com/120677884/207951728-b85f94dd-e95f-42c9-a681-5b3293f15b8d.png)

### 1. Squeeze
Encodes the entire spatial feature on a channel into a global feature. Uses **global average pooling** to compress the two-dimensional feature (H×W) of each channel into a real number.

### 2. Excitation
Dynamically generates a weight value for each feature channel. It uses **two fully connected layers** to form a Bottleneck structure to model the correlation between channels and outputs the same number of weight values as the input features.

### 3. Scale
The normalized weights learned by the excitation are weighted to the features of each channel.

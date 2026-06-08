# Fully Matrix-Based Backpropagation for MNIST

## Objective

The objective of this project is to implement a fully matrix-based mini-batch backpropagation algorithm for a neural network trained on the MNIST handwritten digit dataset. The goal is to improve computational efficiency by processing an entire mini-batch simultaneously using matrix operations.

## Dataset

* MNIST Handwritten Digits Dataset
* Input Size: 784 features (28 × 28 grayscale image)
* Output Classes: 10 digits (0–9)

## Network Architecture

* Input Layer: 784 neurons
* Hidden Layer: 30 neurons
* Output Layer: 10 neurons
* Activation Function: Sigmoid

## Original Implementation

The original implementation used stochastic gradient descent where each training sample in a mini-batch was processed individually. The backpropagation algorithm was executed once for every sample in the mini-batch, resulting in additional Python loop overhead.

### Original Results

| Metric               | Value          |
| -------------------- | -------------- |
| Training Time        | 106.44 seconds |
| Validation Accuracy  | 95.27%         |
| Final Epoch Accuracy | 94.65%         |

## Matrix-Based Implementation

The implementation was modified to process an entire mini-batch as matrices. Feedforward propagation and backpropagation were performed using vectorized NumPy operations, eliminating sample-wise loops during gradient computation.

### Matrix-Based Results

| Metric               | Value         |
| -------------------- | ------------- |
| Training Time        | 29.94 seconds |
| Validation Accuracy  | 95.22%        |
| Final Epoch Accuracy | 95.06%        |

## Performance Comparison

| Metric               | Original   | Matrix-Based |
| -------------------- | ---------- | ------------ |
| Training Time        | 106.44 sec | 29.94 sec    |
| Validation Accuracy  | 95.27%     | 95.22%       |
| Final Epoch Accuracy | 94.65%     | 95.06%       |

## Performance Improvement

* Speedup: **3.55× faster**
* Training time reduced by **71.87%**
* Accuracy maintained while significantly improving training speed

## Conclusion

The fully matrix-based implementation successfully leverages NumPy's optimized linear algebra operations to process complete mini-batches simultaneously. The modified approach achieves a substantial reduction in training time while maintaining comparable classification accuracy on the MNIST dataset.

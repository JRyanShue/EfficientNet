
# EfficientNet
This model is built for image classification. 
Implementation of the paper "EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks" (2019) from scratch.
The code will train the 5.3M-parameter EfficientNet-B0 for compute efficiency. 
The goal will be to match the accuracy attained by the official implementation of EfficientNet-B0 on ImageNet.

## MBConv
Like the original EfficientNet implementation, this model will use MBConv bottleneck layers as the convolutional layers.
MBConv layers first apply a 1x1 convolution layer with ReLU activation, then perform a depthwise convolution with ReLU that expands the representation into 6 times more channels than the input. Finally, a linear 1x1 convolution layer (no nonlinearity) compresses the representation into the original dimension. A residual connection is applied between the two 1x1 convolutional layers. 
MBConv layers were proposed in the paper "MobileNetV2: Inverted Residuals and Linear Bottlenecks" (2018) and the implementation here will be built from scratch. 

## ResNet
This model may include an implementation of the ResNet-50 version of EfficientNet, which achieved 78.8% Top-1 accuracy on ImageNet in 2020. 
The first testable version may just be a ResNet with the hyperparameters of EfficientNet. 
If used, the ResNet architecture will be taken from the paper "Deep Residual Learning for Image Recognition" (2015) and built from scratch.

## Squeeze-and-Excitation
EfficientNet uses Squeeze-and-Excitation blocks, which compress feature maps into scalars via global pooling. The resulting values are used to scale each feature map based on the gated activations of the other feature maps in the same convolutional layer. 
Squeeze-and-Excitation blocks were proposed in the paper "Squeeze-and-Excitation Networks" (2017). The SE blocks in this implementation will be built from scratch. 

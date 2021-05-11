# GAN You Feel the Love Tonight

This repository contains materials related to the semester-long project for CMPE 255 (Data Mining).

## Team

* Brian Ho ([hobriandh](https://github.com/hobriandh))
* Chinmay Kamerkar ([mercury297](https://github.com/mercury297))
* Pratik Kasle ([PRKKILLER](https://github.com/PRKKILLER))
* Andrew Selvia ([AndrewSelviaSJSU](https://github.com/AndrewSelviaSJSU))

## Presentation

We presented the core principles of GANs to the class on March 9th. You can review our presentation at Andrew's GitHub. Since we were the first to present, we had no time to implement any of our ideas, thus this report presents details about our implementation strategies.

## Abstract

Our research focuses on *Generative Adversarial Networks* (GANs). We chose to divide the work so we could explore two unique applications of GANs. This way, we could compare and contrast the efficacy of different architectures and approaches. Andrew and Brian chose to focus on training a GAN to generate pictures from text; in other words, text-to-image. Chinmay and Pratik chose to focus on...

## Super Resolution (SR) GANs

### Approach

Super resolution GANs aims to increase the resolution of images.  SR GANs applies a deep neural network in combination with an adversary network to produce these images.  During the training, a high-resolution image is sampled along with a low-resolution counterpart.  The deep neural network acts as a generator which takes in the low-resolution image and outputs its own high-resolution image.  This generated image is then put into the discriminator network to determine whether the generated image is close enough to the ground truth or if it is just a generated image.

![Network](models/model.jpeg)

This machine learning project was run locally on a NVIDIA GeForce RTX 2060 graphics card.  In order to run on a local machine using a graphics card, there are some necessary drivers to install for tensorflow.  First, the [NVIDIA GPU Drivers](https://www.nvidia.com/download/index.aspx?lang=en-us) are needed.  Then the [NVIDIA CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit-archive) is needed.  This project was run on CUDA v10.0 to work with the Tensorflow v2.0.0b1.  Lastly, the [NVIDIA cuDNN](https://developer.nvidia.com/rdp/cudnn-archive) version that matches the machine's CUDA version is needed.  Once all of these packages are installed, the user can run the program.

To start training, the user needs to run the train script:
```bash
python train.py
```

The initial generator was run for 50 epochs with 6 steps and each step took around 14.5 seconds.
In the second pass that included the discriminator, the model was run for 100 epochs with 12 steps and each step took around 65 seconds.

### Results

After training on the [DIV2K - bicubic downscaling x4 competition](https://data.vision.ee.ethz.ch/cvl/ntire17//) images, we were able to produce some higher quality results.

### Conclusion



### References

* [Google: Introduction to GANs](https://developers.google.com/machine-learning/gan)
* [TensorLayer approach to creating SR GANs](https://github.com/tensorlayer/srgan)

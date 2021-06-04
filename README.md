# Low Resolution to High Resolution Image and Video Upconversion with Convolutional Neural Networks and Variational AutoEncoders.

![convolutional image logo](/image_space.png)


*We report on the conversion of low-resolution images to higher resolution with the use of several convolutional network inspired architectures. We first show that we can achieve low mean-squared-error (MSE) scores of \begin{math}<\end{math}0.01 with Convolution neural network architectures serving as the encoder-decoder network with convolution 2D transpose. We further show improved performance of the architectures through optimization of the Convolutional Neural Network (CNN) architectures with batch normalization, drop-out, Kaiming initialization parameters as well as through the exploration of several loss functions including the VGG loss function. Finally, we report on the use of Variational Auto-Encoder (VAE) and CNN decoder to achieve superior enhancement in image resolution from intial 256x256 to a 512x512. In addition to using MSE for measuring algorithm performance during training, we also explored the use of peak signal to noise ratio (PSNR), structural similarity index for image quality assessment (SSIM) to regulate the loss functions in our models and evaluate model performance.  The proposed architectures were then evaluated on short movie frame to show inference latency and image quality on video rendering from low resolution to high resolution.*


## Organization of this GitHub Repository.
This repository is organized into folders that have .ipynb notebooks.

1. The VAE folder contains notebooks that show the training pipeline that was used to train the algorithm for variational autoencoder.
   Please note that for this project the team explored 2 variations of Variational autoencoders.
   * Variational autoencoder without residual connections between the Encoder and Decoder
   * Variational autoencoder with residual connection between the Encoder and the Decoder

2. The CNN folder contains notebooks that show the training pipeline that was used to train the convolutional neural network, autoencoder.


## Low Resolution Video 
![original_lr_video](/original_lr_real_video_.gif)

## Upconverted High Resolution Output using Convolutional regressive Autoencdoer trained for 50 Epochs with Sigmoid activation function
![Model Output](/enhanced_real_video_cnn_finale.gif)

## The actual video at High resolution
![Model_Output_CNN](/original_hr_real_video.gif)

## The End-2-End data pipeline for up-conversion from low-res to High-res Image/Video

Data generation involves the conversion of high resolution video into high resolution frames at 1980x1080.
Each frame is then converted to a high reslution image of 512x512.
The low resolution counterpart is obtained using pixelation and Gaussian noise. The low resolution counterpart is then reshaped to a 256x256

The low resolution image and it's high resolution pair are then provided as the training data set to the CNN,VAE model.
The model's output is an enhanced (denoised and upconverted) sample of the low resolution input at 512x512.

THe Model can then be run on frames of images to give enhanced frames and enhanced video as shown above.
![pipeline](/pipeline.jpeg)

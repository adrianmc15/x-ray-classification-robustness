# Modelling Robustness towards Noise in Tuberculosis detection through Chest X-Rays

The purpose of this project is to try to improve the robustness of a CNN to noise in x-ray image data, specifically when it comes to the noise associated with low doses in x-ray.

This project has the following structure fitting with different stages of the project. The order and summary of these stages is listed below:
1. **preprocessing_and_baseline/baseline_no_noise.ipynb**
    
    This file is the starter baseline, and consists of a CNN model adapted from https://www.kaggle.com/code/pisitjanthawee13/tuberculosis-detection-cnns-with-lime as a baseline for the project.

2. **preprocessing_and_baseline/test_set_noise_only.ipynb**

    This file is used to test the generalization of the previous model (trained on no-noise data) to a noisy dataset.

        Result was 51% Accuracy on Test Set

3. **training_with_noise/**

    This file both trains and tests the model on noisy data.

        Result was 90% Accuracy on Test Set
    
    And then a mixed dataset approach is also tested:

    Tasks:
    
        [x] try on completely noisy dataset
        [x] create a mixed dataset
        [x] try with mixed dataset:
            -> try train = mixed, test = noise (95%)
            -> try train = mixed, test = mixed (96%)

4. **apply_denoising.ipynb**

    This file includes denoising techniques in the preprocessing for the model

    Tasks:
    
        [ ] Try one basic denoising technique

5. **loss_function_adjustment.ipynb**

    This notebook explores the adjustment of the loss function to better generalise and train the model to work with noise to noise architecture.

        [x] *Autoencoder -> try to interpret results
            -> create autoencoder noisy-to-noisy
            -> feed encoder output into CNN
            -> see how good that is
            -> try different losses (apparently MAE and Huber are better for noise)
            -> Future Goal: try to find a way to manually find the latent representation, or find a latent representation that will help with this (applying wavelet, fft)

            Accuracy: 96.6 %

        [ ] using different losses (MAE and Huber)
        [ ] More Aggressive Regularization
        [ ] *Wavelet Transform Layers

        [ ] (FFT w/ filter representation?)

6. **Other Techniques**

    This will include a variety of other techniques for improving the network:
    - lung segmentation


## Plan for the Paper

**Main Question:**
What new representation of the images can we apply to the CNN to get the best results for the classifier?

### Structure of the paper
1. **Preprocessing the Data and Modelling Noise**

    - Poisson-Gaussian Model from that paper
    - How Noise amounts were chosen

2. **The CNN Used**
    
    - describe the model
    - show initial results

3. **Experiments and Baselines**

    Basically to discuss the different more basic experiments:
    - explain different basic approaches
    - adding noise to the training data (different levels of noise)
    - using some denoising

4. **Model Design and Adjustment**

    - Autoencoder -> try to interpret results
    - using different losses (MAE and Huber)
    - More Aggressive Regularization
    - Wavelet Transform Layers
    - (FFT w/ filter representation?)

5. **Other Approaches**

    - lung segmentation

Papers to look at wrt Step 4:
- https://www.analyticsvidhya.com/blog/2021/07/image-denoising-using-autoencoders-a-beginners-guide-to-deep-learning-project/
- https://openaccess.thecvf.com/content_CVPR_2020/papers/Li_Wavelet_Integrated_CNNs_for_Noise-Robust_Image_Classification_CVPR_2020_paper.pdf
- https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6705590
- https://ieeexplore.ieee.org/abstract/document/9508165?casa_token=OXw1dfgH2GMAAAAA:keFGl9O1BjLdLCsk1ZwSuxFXmW9bROQFHb2ULdRY7nEO9_CBrHa0oB2HLLIzTMh8PuhMRKubyA
- https://www.frontiersin.org/articles/10.3389/fninf.2023.1074653/full
- https://research.nvidia.com/sites/default/files/pubs/2017-03_Loss-Functions-for/NN_ImgProc.pdf 
- https://towardsdatascience.com/deep-learning-image-enhancement-insights-on-loss-function-engineering-f57ccbb585d7

Lung Segmentation:
https://github.com/IlliaOvcharenko/lung-segmentation (can be fed back into CNN)


more aggressive in regularization
find the commonalities among -> new representation

attempt to include a latent representational model 


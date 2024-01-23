# Plan going forward with the Project

This document describes the further developments on the project in light of the presentation and Professor Ruan's Suggestions.

The following are the areas that are going to be explored in this section.
1. **Image Quality Metrics**
    
    Assess the different image enhancement metrics:
    PSNR, SSIM, MSE, MAE

        We want to calculate these metrics for the noisy images and assess how closely they correlate to the accuracy of the model -> maybe try different levels of noise

        [ ] calculate the metrics for the noisy model and more noise
        [ ] calculate the metrics for the denoised models
        [ ] produce into neat results table

    Ask for advice and info going forward:
    
        [ ] send email to professor 

2. **Other Approaches**
    
    The noise2noise is a good approach to use. Also continue thinking about increase robustness in the cost/objective or networks structure. One of the outcomes is that we will be equipped with insight to talk about sequential processing (denoise + well-trained SOTA identification network) vs end-to-end. This should result in a good paper.

3. **Accurately Modelling Noise**

    We should discuss what are the best direction to spin: the current noise model, whether they are additive poison or Gaussian is still a bit artificial. More realistically, we want to include both, and at reasonable value range. How about read a bit on what is the best \lambda, and sigma to put with some literature survey? I can introduce radiologist/radiology physicists to the discussion if needed. We also have access to collaborators who can do semi-analytical simulation to extend this work to low-dose CT.


2. **preprocessing_and_baseline/test_set_noise_only.ipynb**




    This file is used to test the generalization of the previous model (trained on no-noise data) to a noisy dataset.

        Result was 51% Accuracy on Test Set

3. **training_with_noise/**
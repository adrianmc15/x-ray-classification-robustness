# Modelling Robustness towards Noise in Tuberculosis detection through Chest X-Rays

The purpose of this project is to try to improve the robustness of a CNN to noise in x-ray image data, specifically when it comes to the noise associated with low doses in x-ray.

This project has the following structure fitting with different stages of the project. The order and summary of these stages is listed below:
1. **baseline_no_noise.ipynb**
    
    This file is the starter baseline, and consists of a CNN model adapted from https://www.kaggle.com/code/pisitjanthawee13/tuberculosis-detection-cnns-with-lime as a baseline for the project.

2. **test_set_noise_only.ipynb**

    This file is used to test the generalization of the previous model (trained on no-noise data) to a noisy dataset.

        Result was 51% Accuracy on Test Set

3. **train_test_model_noise.ipynb**

    This file both trains and tests the model on noisy data.

        Result was 90% Accuracy on Test Set
    
    Notes: Maybe try doing a mixture of noisy and non-noisy training data? See how that fairs

4. **apply_denoising.ipynb**

    This file includes denoising techniques in the preprocessing for the model

5. **loss_function_adjustment.ipynb**

    This notebook explores the adjustment of the loss function to better generalise and train the model to work with noise to noise architecture.

more aggressive in regularization
find the commonalities mong -> new representation

attempt to inc;ude a latent representation 


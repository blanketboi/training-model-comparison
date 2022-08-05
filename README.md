# Training Model Comparison
Comparing the performance of different ML models on large image datasets

Requires CIFAR 100 training_images and testing_images in order to run

## Methodology
To ensure we were achieving the best possible results, we developed models using two different methods. The models were first used in lab work and converted to be used with the current dataset. As the CIFAR dataset was pre-split with 50,000 images for training and 10,000 for testing, the data only needed to be transposed and normalised before it could be used by both of the following CNN and SVM models. 
We avoided models such as K-means as it’s clustering of outliers can be a cause of misidentifying images, additionally the model would not work on the dataset due to the large number of features. Linear Regression was another model we avoided because of its linear nature and inaccuracy when it comes to real world classification data that does not conform to trends.
The training and testing data is first transposed to make it compatible with the model and graphing tool, as without that, the model believes that the image trying to be read has the X axis of the size of the dataset. In this case we can use the NumPy library to manipulate the data easily with the transpose function that allows us to specify the axis of the dataset to permute.

We then prepare the data for normalising by converting the existing dataset (presumed float) into float32, allowing us to keep accuracy after normalising. Converting is also a requirement as trying to normalise will result in an error as the current datatype is not large enough to store the decimal places. The astype function is also part of the NumPy library.
The last step before we can use the data is to normalise it, we must do this because the models used deal in sizes between 0 and 1. Another reason for normalising is to bring all the images in the dataset to a common scale so that the model does not have to change its parameters for each image.

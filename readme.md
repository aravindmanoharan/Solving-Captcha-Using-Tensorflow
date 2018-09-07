# Solving-Captcha-Using-Tensorflow

A CAPTCHA is a type of challenge-response test used in computing to determine whether or not the user is human. There are so much development in Deep Learning that we can train a model to predict the text in a captcha image.

## Dataset

The Dataset which I have used are hand picked from certain websites using web scrapping methods. I'm not providing the code for collecting captcha in this repository. But you can find the 10,000 captcha images and also the preprocessed images in this repository. Let's look at few sample captcha images.

<p align="center">
  <img width="200" height="150" src="https://user-images.githubusercontent.com/35612880/44631813-16225400-a926-11e8-9628-dd7ecdf77216.png">
</p>

Each of the captcha images have six letters and they are only alphabets. To train the model, we have to preprocess these images and split the image into six separate letters. After preprocessing the images, the six letters looks like this.

<p align="center">
  <img width="300" height="100" src="https://user-images.githubusercontent.com/35612880/44631979-9649b900-a928-11e8-819a-861d2371c4b2.png">
</p>
 
## Requirements

We are using Tensorflow framework to implement the CNN model. 
```
pip install tensorflow
```
Please check the requirements.txt file for all the packages whcih you need to install. Most of the packages can be installed using the pip package manager.

## Simplifying the problem

We simplify the problem by splitting the captcha image into single letters. Now, we only have to train the neural network to recognize a single letter at a time.

<p align="center">
  <img width="700" height="300" src="https://user-images.githubusercontent.com/35612880/44632814-28a48980-a936-11e8-89c2-5f9d84d6b72e.png">
</p>

We can automate the process of splitting the images into separate letters. In image processing, we often need to detect “blobs” of pixels that have the same color. The boundaries around those continuous pixels blobs are called contours. OpenCV has a built-in findContours() function that we can use to detect these continuous regions.

## Training the model

Since the captcha images are split into letters, a simple convolutional network would be sufficient to achieve a better prediction. The architecture which is used here consists of two convlutional layers and two fully connected layers.

<p align="center">
  <img width="700" height="300" src="https://user-images.githubusercontent.com/35612880/44632803-feeb6280-a935-11e8-8397-695a4a33cfe7.png">
</p>

## Using the model to solve CAPTCHAs

After training the model, predicting captcha becomes simpler.

1. Split the captcha image into separate letters.
2. Use the trained model to predict the letters separately.
3. After the predictions of all six letters, combine the predictions to form the captcha output.

## Have questions? Need help with the code?

If you're having issues with or have questions about the code, [file an issue](https://github.com/aravindmanoharan/Solving-Captcha-Using-Tensorflow/issues) in this repository so that I can get back to you soon.

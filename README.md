# Emotion Detection - Implementation of a CNN model for facial emotion recognition4

Convolutional Neural Networks are useful for a wide range of tasks, which shows how far deep learning has come in a short period of time. In this project, I will be developing a model to detect emotions from facial features.

# Dataset
I used the FER 2013 dataset from Kaggle for my project. The only readily accessible dataset I could find for this purpose was this one. The emotion labels in the dataset are mapped to the corresponding pixel values in the current image using CSV files.

It has seven emotions or classes (0 = angry, 1 = disgust, 2 = fear, 3 = happy, 4 = sad, 5 = surprise, 6 = neutral).

![image](https://user-images.githubusercontent.com/103538049/213875859-cdba4937-f82b-45a8-8e49-73c5b44f6d71.png)

As we can see from the above figure, the classes are a little skewed.

# Preprocessing the pixel values

In order to create an image, we must translate the pixel values into their image form in Google Colab. In order to complete this task, I have used a the function. The function takes as input the dataset's pixels column and transforms each entry from a string to an array of integers that is then moulded into the images that will be used for training. 

Because some classes in the dataset contain a lot more examples than others, the dataset is a little bit skewed. Using RandomOverSampler, which oversamples the classes that are in lower numbers in a dataset, is one technique to get around this. It essentially replicates cases in the minority classes at random, which aids in balancing out the dataset. I have used RandomOverSampler to balance the dataset.

#Creating CNN Model
I have used a CNN model to detect the emotions. Before training the model,the image emotion labels were converted to one-hot encoded, using to_categorical.Here we have 7 categories. And then, the model was trained for 30 epochs.


# Predictions

To predict the emotions I used two methods. In the first method I am predicting the emotions directly by giving the file path. Few of the results are shown below

![image](https://user-images.githubusercontent.com/103538049/213876533-33e5179f-ab4c-41bc-8e9f-d042af84b58a.png)

![image](https://user-images.githubusercontent.com/103538049/213876553-8d28c32a-b672-472f-8211-be7b4180c4d8.png)

![image](https://user-images.githubusercontent.com/103538049/213876563-59cac80d-bb85-4466-8296-cb5a849c14ac.png)


While, image 3 is predicted as sad, it actually represents 'angry'. So to understand how the algorithm is predicting images, next I am predicting the top 3 predicts for a given image and the reults are given below.

![image](https://user-images.githubusercontent.com/103538049/213876950-365307cb-b320-4e6f-8fcd-a46b0bee6b8a.png)

![image](https://user-images.githubusercontent.com/103538049/213876982-c0c944e1-9d66-4cd0-9854-6c6f4e92f4dd.png)

![image](https://user-images.githubusercontent.com/103538049/213877026-08de02bb-29b3-43cc-b0ec-25c69d7e24f9.png)





# Gender-Race-Age-detection-MultiLabel-MultiOutput

## Goal:-
If we want to know the gender, race and age of a person, we generally build 3 different models each for gender, race and age classification. This can lead to a computionally much expensive task, since we would be training 3 different models. If we think about these 3 features of a person, we can observe the all 3 features i.e. gender, race and age are primarily dependent on the person's face. So, we can use a base model to capture the salient features of a person's face and use these extracted features to train a model for all the 3 features. Here, the goal of this project is to build a multi-class multi-label classification model which can detect a person's gender, race and age.


### Approach:-
Here, i have used a dataset from kaggle which contains around 90,000 images. But, here i have used a sample of size 20000 because of insufficient resources. I observed that the dataset is quite imbalanced with respect to the age. So, i have applied augmentation techniques with certain criterion which could ultimately handle the imbalance problem. I have used the pretrained weights of the InceptionResnetV2 model as a base model in order to extract the salient facial features. These are then flattened and fed into multiple dense layers which ultimately produces 3 outputs each for gender, race and age classification. In order to achieve this, i have used Keras Functional API.

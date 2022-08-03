# Gender-Race-Age-detection-MultiLabel-MultiOutput

## Goal:-
If we want to know the gender, race and age of a person, we generally build 3 different models each for gender, race and age classification. This can lead to a computionally much expensive task, since we would be training 3 different models. If we think about these 3 features of a person, we can observe the all 3 features i.e. gender, race and age are primarily dependent on the person's face. So, we can use a base model to capture the salient features of a person's face and use these extracted features to train a model for all the 3 features. Here, the goal of this project is to build a multi-class multi-label classification model which can detect a person's gender, race and age.

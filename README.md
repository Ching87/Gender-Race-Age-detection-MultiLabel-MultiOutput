# Gender-Race-Age-detection-MultiLabel-MultiOutput

## Goal:-
If we want to know the gender, race and age of a person, we generally build 3 different models each for gender, race and age classification. This can lead to a computionally much expensive task, since we would be training 3 different models. If we think about these 3 features of a person, we can observe the all 3 features i.e. gender, race and age are primarily dependent on the person's face. So, we can use a base model to capture the salient features of a person's face and use these extracted features to train a model for all the 3 features. Here, the goal of this project is to build a multi-class multi-label classification model which can detect a person's gender, race and age.


### Approach:-
Here, i have used a dataset from kaggle which contains around 90,000 images. But, here i have used a sample of size 20000 because of insufficient resources. I observed that the dataset is quite imbalanced with respect to the age. So, i have applied augmentation techniques with certain criterion which could ultimately handle the imbalance problem. I have used the pretrained weights of the InceptionResnetV2 model as a base model in order to extract the salient facial features. These are then flattened and fed into multiple dense layers which ultimately produces 3 outputs each for gender, race and age classification. In order to achieve this, i have used Keras Functional API which allows to create multiple inputs or outputs. Since, i have used Kaggle Notebook and it allows only 16 GB of RAM, even the sample dataset could not be loaded at once into the RAM. So, i have sequentially loaded the images on a batch of 32 and passed them into the model for training.

![image](https://user-images.githubusercontent.com/96677288/182716226-6dbc2dc7-9202-4fe2-8010-f763d6efd369.png)
Plot of various age range. Here, we can see that it is imbalance

![image](https://user-images.githubusercontent.com/96677288/182716412-da10e85c-107c-4f78-9554-e390aa1ac242.png)
Plot for gender is almost balanced

![image](https://user-images.githubusercontent.com/96677288/182716557-7d197b76-c918-4856-b499-2ea77c0f6dbf.png)
Plot for race also looks quite balanced

#### After applying augmentation to remove imbalance nature of age
![image](https://user-images.githubusercontent.com/96677288/182717341-80ef4e16-6431-44c5-9685-e2c43d219352.png)
Now, the plot for age ranges looks quite balanced



### Evaluation:-
Able to achieve an accuracy of around 93% (gender) , 47% (race) and 56% (age) on 10,000 test images.
![image](https://user-images.githubusercontent.com/96677288/182717685-2c319a3d-14b8-4508-af70-dbf0e53b17bd.png)


#### Prediction
![image](https://user-images.githubusercontent.com/96677288/182717773-364f8c3f-3ac3-4b42-8319-0c1fca236bc4.png)



##### The model architecture visualization
![model_architecture](https://user-images.githubusercontent.com/96677288/182718417-23e6a74b-5ff8-4a26-a92f-e28e00e990a5.png)




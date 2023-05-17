# Determining the age of customers

## Project Description

The chain supermarket "Bread-Salt" introduces a computer vision system for processing customer photos. Photo fixation in the checkout area will help determine the age of customers in order to:

* Analyze purchases and offer products that may be of interest to buyers of this age group;
* Monitor the integrity of cashiers when selling alcohol.

Build a model that will determine the approximate age of a person from a photo. At your disposal is a set of photos of people with age indication.

## Conclusions:
The type of task is Regression.

The study of age categories suggests that ages from 1 to 100 years are represented, while some three ages are not represented - they have to be found. In addition, there are ages significantly deprived of photos – from one to 15 photos per age. 75% of all ages will have at least 128 photos per age. In general, there is enough data to train models capable of recognizing most of the customers' faces. In addition, the distribution in the dataset is similar to the distribution in the Pyramid of the population of the Russian Federation (roughly correlates with the "aging" population), which is generally suitable for recognizing a "random" client. The target age for business is also, let's assume, sufficiently represented by the dataset.

The first 50 least represented ages are derived in order to estimate how many of the "deprived" elderly people, and how many are children. The worst thing is with photos of the elderly over 60 and the age of puberty.

There are 7591 faces in total. At the same time, there are no faces of children under one year old and relatively few faces of teenage children who vary greatly in their group in life. Few people are over 60 years old and very few are over 80. Probably, the model will not cope very well with these categories on real data. Three ages are not represented in the data – 92, 98 and 99 years.

The photos have not undergone any preprocessing except for highlighting the face in the photo. People of all races, in accessories and partially with a covered face, which correlates with real data. 

Research analysis has shown that the model may not work well on children and the elderly. The ages of 92.98 and 99 are not represented at all. The model is trained using ResNet50, the top is replaced for regression. 

The ResNet50 architecture was used as the backbone, the weights were pre-trained, freezing was not carried out. 
10 epochs turned out to be enough, while the model did not retrain. batch_size is set in ResNet50, and the number of steps is equal to the sample size. 

The model significantly exceeded the threshold quality in the test sample – MAE reached a value of 6.3121
The trained model is suitable for assessing the age of the buyer from the photo.

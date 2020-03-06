---
layout: post
title: Predicting the Type of School Shooting
subtitle: School Shootings Data from 1999-2019
bigimg: /img/HighSchool.jpg
---

School shootings continue to happen and it seems there is no predictor as to when or if they will stop. I previously looked
into school shootings and discovered a few things (i.e the type of school that has a higher chance of a shooting, when it is
more likely to be shot) and was left with more questions. In my effort to try to further understand and possibly contribute
to any solution, I found more school shootings data and ran a few more tests.

I decided I would try to create several models to try and predict the type of school shooting and see what insights I 
could gather. I established a **majority class baseline of roughly 59%** (the amount of times I would get it correct by 
guessing if the school shooting was 'targeted').

Now that I had established a baseline it was time to create some models to remove the guess work. I created a **linear model
using cross-validation** that gave me an accuracy for predicting the school shootings type of roughly **66% accuracy** and 
a few other **tree based models using cross-validation** that gave me accuracies within the **61-62% range**. All of my 
models turned out to be better than guessing.

### Insights

Using one of my models I looked into my feature with the most importance(based off permutation importance) and found this:

Class 0: Indiscriminate

Class 1: Other

Class 2: Targeted

It seems as the number of caucasion students increase the probability of a shooting being 'indiscriminate' or 'other' increase,
but the probability of the shooting being 'targeted' decreases.

![White Class Data](/img/white_class.png)

Looking at the same feature combined with our 'casualties' feature we have a more detailed look at the probabilites
individually and see the correlation between the two specific features. Similar results.

![White vs Casualties Data](/img/casualties_white.png)

I tried another combination of features as well to see the probablities and correlation between the two features. Here I found
that in my model's prediction there seems to be a higher probability of casualties/injuries when the shooting is not
'targeted'.

![Injured vs Casualties Data](/img/casualties_injured.png)

There is many more possibilites to be tested, but I believe this could be a starting to point to finding some great insights
into trying to solve some of the reasons why these shootings are happening. Hopefully in the future we can altogether eradicate
school shootings.

[My Work](https://colab.research.google.com/drive/1KGFHKC3uPqWF3CMgf1VVhmwl8yIkbj78)

[Data Source](https://github.com/washingtonpost/data-school-shootings/blob/master/school-shootings-data.csv)

# 【双语字幕+资料下载】用 Python 和 Numpy 实现最热门的12个机器学习算法，彻底搞清楚它们的工作原理！＜实战教程系列＞ - P9：L9- 决策树第 1 部分 - ShowMeAI - BV1wS4y1f7z1

Hi， everybody。 Welcome to a new machine learning from Sc tutorial。 Today。

 we are going to implement a decision tree using only built in Python modules and nuy。

 A decision tree is a very simple but powerful concept。

 The idea is to build a tree that splits our data such that we have the best separation of our classes。

 A decision tree is also the basis for the very popular random forest model。

 which we will implement in the next tutorial。 So I hope you will stick with me。😊，And as always。

 we will start with the theory first。 So let's look at an example to understand the concept and the math behind the decision tree。

 Let's say we want to predict if a person is walking or taking the bus to go to work。

 and we have 10 observations or 10 samples with two different features。

So we have the feature if it is raining and then we have the feature， how much time do they have？

And then we have the prediction or the class label， yes or no。



![](img/e1b43f93535591fc8a4dc158e9ae735d_1.png)

And now we want to build our tree that splits our data。

 so we put all the samples in the root node and then we apply a question so we ask if it is raining and if the answer is yes。

 then we go to the right and we put all the samples where the answer is yes。

 so these three into the right note and if the answer is no。

 then we go to the left and put all the other samples in the left node。



![](img/e1b43f93535591fc8a4dc158e9ae735d_3.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_4.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_5.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_6.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_7.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_8.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_9.png)

And here on the right， we can immediately say that the answer is no， They don't walk。 So we put the。



![](img/e1b43f93535591fc8a4dc158e9ae735d_11.png)

Or return the class label 0。 And here on the left， we can further split the data and grow our tree。

 So we ask the next question。 So do they have more than 10 minutes and again。

 if the answer is yes and we go to the right and put all of the。



![](img/e1b43f93535591fc8a4dc158e9ae735d_13.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_14.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_15.png)

Samples where where they have more than 10 minutes in the right note and all the other ones in the left note and then again here we can say that the answer is yes or the class label is1 and here the class label is 0。



![](img/e1b43f93535591fc8a4dc158e9ae735d_17.png)

And we could also stop with the growing here and return the most common class label。

 So here we can say that it's more likely that they will walk。

m but we could also further split our data and but we don't want to grow our data too much because we don't want to overfit our data。

 but we also want to have a good prediction。

![](img/e1b43f93535591fc8a4dc158e9ae735d_19.png)

So this is the concept of how the decision tree works and now the only thing that we have to find out is at what at which node we want to apply which question so why do we ask for rain at first and not for the time and why do we ask for the time is greater than 10 and why don't we ask for if it's greater than 5 or greater than 20。

 so this is the best the so-called best。

![](img/e1b43f93535591fc8a4dc158e9ae735d_21.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_22.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_23.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_24.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_25.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_26.png)

Split feature and best split value or split threshold that we want to find out。



![](img/e1b43f93535591fc8a4dc158e9ae735d_28.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_29.png)

So， the concept is to。At each note， we want to find the best split value and the best split threshold and store them。

And this is our training phase and later when we want to predict a new test sample。

 then we start at the top and then we traverse our tree and apply the questions or the features that we start and go to the left or to the right until we reach a leaf node so a leaf node the node at the bottom。

 and then we apply the most common label that we stored based on our test samples。



![](img/e1b43f93535591fc8a4dc158e9ae735d_31.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_32.png)

So this is the concept。 And now how do we find out the best split。 So for this， we need some math。

 So we calculate the entropy and the entropy is also is the a measure for uncertainty。

 So the formula is minus， and then we have the sum of p of x times lock of p of x and p of x is the number of occurrences over the total number of samples。

 So in our example we have 110 samples and five times the answer is or the label is 0 and five times the answer is。



![](img/e1b43f93535591fc8a4dc158e9ae735d_34.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_35.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_36.png)

1。And then we have its， our entropy is minus5 over 10 times lock of 5 over 10 minus。

 And then we look at the next。Label， so one again， we have five labels。

 so minus5 over 10 times lock of 5 over 10。 And if you calculate this， then this is one。

 So this is the worst possible case here in our in the first note we cannot make a prediction which are if it is one or0。

 because we have an equal amount of both。

![](img/e1b43f93535591fc8a4dc158e9ae735d_38.png)

Samples or both classes here。So one is the worst possible case and like here the entropy here would be0。

 so this is the best case here we are very certain that we have the class0。



![](img/e1b43f93535591fc8a4dc158e9ae735d_40.png)

And now so we calculate the entropy and then we split our data and calculate the entropy for our childs。

And then we calculate how much information we gain through this split and this measure is actually really called information gain。

 And this is calculated by the entropy of the parent minus weighted average of all the child entroies。

 So like in our example， we have the root note with our 10 observations。



![](img/e1b43f93535591fc8a4dc158e9ae735d_42.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_43.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_44.png)

And then on the left side， we have 7 observations with here，2 zeros。And5 one。 And on the right side。

 we have three zeros。 So our entropy is the entropy of the parent-7 over 10 times the entropy on the left side plus 3 over 10 times the entropy of the right side。

 So this is the information gain。

![](img/e1b43f93535591fc8a4dc158e9ae735d_46.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_47.png)

And now we do a greedy search， so we go over all the possible features and over all the possible feature values or thresholds。

 so for rain we check if it's yes or no or it means one or zero and if the answer and for the time feature。

 we check for5， 10， 15， 20， 25 and 30 so we do a greedy search。



![](img/e1b43f93535591fc8a4dc158e9ae735d_49.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_50.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_51.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_52.png)

And then， we store。Or select and store the best feature and the best threshold。 So this is the。



![](img/e1b43f93535591fc8a4dc158e9ae735d_54.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_55.png)

Concept， so let's look at the approach a little bit more in detail。 So first。

 we have the training phase where we want to build our tree。 So we start at a top node。

 and at each node， we select the best split based on the best information game。



![](img/e1b43f93535591fc8a4dc158e9ae735d_57.png)

And we do a greedy search， so we loop over all features and over all thresholds。

Then we saved the best split feature and split threshold at each node and we built the tree recursively。



![](img/e1b43f93535591fc8a4dc158e9ae735d_59.png)

And we also have to apply some stopping criteria to stop growing。 And in our example。

 we will use a maximum depth。

![](img/e1b43f93535591fc8a4dc158e9ae735d_61.png)

So for example， we say if the depth three is5， then we would stop。



![](img/e1b43f93535591fc8a4dc158e9ae735d_63.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_64.png)

And we use a minimum samples at a node。 So， for example。

 we could say if we have less than five samples in a node then we don't split any further。



![](img/e1b43f93535591fc8a4dc158e9ae735d_66.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_67.png)

And if we have no more class distribution in a node like here。

 then we can no longer split because we only have class 0 labels here。

 So these are our stopping criteria that we need。 And then when we have a leaf node。

 then we store the most common class label of this node。 So here we store 0，1 and 0。



![](img/e1b43f93535591fc8a4dc158e9ae735d_69.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_70.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_71.png)

![](img/e1b43f93535591fc8a4dc158e9ae735d_72.png)

So this is our training phase and then later when we do the testing with new samples。

 then we traverse the tree and we also do this recursively。

 so we implement a function that calls itself。And at each note。

 we look at the best split feature of the test feature vector and go left or right， depending on if。

The value of this feature。Is smaller or equal than our threshold that we stored？

And then when we reach the leaf node or the bottom， we return the stored most common class label。

 So this is the concept of the。

![](img/e1b43f93535591fc8a4dc158e9ae735d_74.png)

Decis 3。 And now I think I will stop this video here。

 and we will continue in the next part or in the second part with the implementation。

 So see you then。

![](img/e1b43f93535591fc8a4dc158e9ae735d_76.png)
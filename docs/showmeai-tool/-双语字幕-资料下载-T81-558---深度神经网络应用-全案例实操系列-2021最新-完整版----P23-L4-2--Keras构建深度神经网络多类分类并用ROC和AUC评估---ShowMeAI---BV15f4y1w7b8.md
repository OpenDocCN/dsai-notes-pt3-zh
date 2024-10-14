# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P23：L4.2- Keras构建深度神经网络多类分类并用ROC和AUC评估 - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Heaton， welcomelcome to applications of deep neural networks with Washington University In this video I'm going to show you how to do both binary class and multi class classification。

Neurural networks with Kias for the latest on my AI course and projects。

 click subscribe and the bell next to it to be notified of every new video In the next two videos。

 we're going to look at classification and regression。 This video focuses on classification。

 We subdivide this into two parts。 There's binary classification。

 and then there's multiclass classification。

![](img/0c3de78b0d0924709e45c8de93aa7c5d_1.png)

We'll start by looking at binary classification， binary classification。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_3.png)

We're going to look at rock charts and see how to measure false positives， false negatives。

 and look at the special ways that we evaluate binary classification。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_5.png)

Very often you can think of this as a medical test。

 so we're going to look at the Wisconsin breastreast cancer database， it has measurements of tumors。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_7.png)

And then a target column that says if they're malignant or benign， these are all malignant。

 but there's also bees， which are benign。 We're going to start by looking at how we would measure the success of a model based on this with ature Now you could just do accuracy you could say I am going to calculate have the neural network predict malignant or benign for each of these。

 and it will simply come back with a percent。 It got 90% correct or it got 70% correct。 However。

 that's only one side of the of the coin。 You might care how many times it was wrong when it said somebody had a cancerous tumor or you might care how many times it was wrong when it said somebody did not because those are two completely different things and you may want to calibrate differently。

 It may be much worse for somebody who falsely was。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_9.png)

Told they did not have cancer to forego medical treatment。

 then simply doing extra medical treatment on somebody who did not have a disease。

Or the flip could be true if the treatment is particularly horrendous for the individual。

 so for rock curves， we look at false positives and false negatives。

 a false positive is when something came back positive。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_11.png)

But it was not false negative is when something came back negative。

 but it was not then there's also the true positives where the test truly identified positive or true negative where it truly identified negative true positive where it truly identified positive and true negative where it truly identified negative there's other names for these type 1 and type 2 error also sensitivity and specificity sensitivity is how good the model is at predicting that you do have the condition or positives correctly specificity is how good the model is at detecting if you don't have the condition accurately and taken together both of those are just the overall accuracy typically for some of these we need to define a cutoff and this is where rock charts come and come into play a cutoff might be because most of these most of these tests will come back with some sort of number。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_13.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_14.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_15.png)

This is the output from your from your output neuron maybe zero means it's somewhat on the fence。

 maybe a high number means that you are positive， maybe a negative number means your negative and you have to decide where you're going cut that off you may not cut it off just at zero it may not be it may not be even or if you want to wait towards you prefer false positives or you prefer false negatives obviously prefer neither but if you have to have one would you prefer false positive or false negative then you can optimize your threshold towards sensitivity or specificity so I'm going to run this block of code this block of code is not really that important it's just used to display this diagram now this diagram shows what the output of your neural network might look like maybe this neural network outputs zero if it's really not that sure if your negative or positive for the condition and。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_17.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_18.png)

Puts a negative value if if you're more negative so you don't have the condition and it outputs positive if you more likely do have the condition now these lines specify where you might set your cut point or your threshold when you move that line you're tuning the sensitive of your model that is how you are balancing between false alarms and it actually catching cases where where it truly was positive if you put your line here。

 you're making this very sensitive if you set your line here you're making it very specific the reason that is if you make it sensitive。

 then you're tuning towards false you're tuning towards getting correct positive result So the entire positive curve is over here if you're tuning towards specific then the entire negative curve is over here obviously you probably don't want to put it either here here you want it somewhere in the middle。

Completely balanced is is right here。 So that's an important thing to realize on this。

 You can get a perfect sensitivity or a perfect specificity， but you do very。😊。

Bad results to the to the other side of the coin， if you want to be sure that your that your model is completely sensitive and picks up every case where the person would have the disease simply classify everybody as positive you'll never miss anybody and the same thing for negative。

 but obviously that's not particularly useful， but that shows the extremes of these two。

Of these two ranges by the way the aes of these the X is the output from the neural network or the test and that's how you read the test as far as negative or positive and then the y is simply how many values we have in each of these categories they're not always normally distributed like that but it makes a diagram look good and this is a classic diagram that you see in statistics by the way。

 if you want to read more or see more about this is is a great Khan Academy video that that my diagram here is very much based on this is also a common interview question in machine learning data science we give you that diagram and we ask you to say okay which of these two lines sometimes will not have the middle line。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_20.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_21.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_22.png)

Is a more sensitive versus a more specific test。 So now let's go ahead and we're going to load in the binary data for this test。

 I'm going to run this section that simply loads in the data This is important to see down here where we're preparing X and Y's。

 notice how I do the Y's。 This is how you do it for a binary classification。

 I'm mapping the malignance to one and the benigns to0。

 Now we're going to define two functions that we're going to use later。

 I'm not going to go too much into these functions or more along the lines of plotting。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_24.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_25.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_26.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_27.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_28.png)

I can do an entire course on plotting， but this is going to basically draw a rock chart and draw a confusion matrix Both of these are very useful for classification neural networks Now let's look at a rock chart example we're going to have to train a neural network for binary classification。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_30.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_31.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_32.png)

Now for binary classification， we use binary cross entropy。

 very important and we want to have just the one output Norra like like we've had before for for regression but this is not a regression。

 It looks like a regression and it' it's definitely some similarities but this is only use when you're doing classification with a binary outcome and don't do dummy variables。

 you don't want to do two so that's why up here for the x we did not do dummy or for the y I'm sorry we did not do dummies。

 we simply have a column matrix of zeros and ones。 we're going to go ahead and run this we'll use early stopping All right we have early stopped and we'll see more about cross validation in the next module it's a way to be able to get out of sample or results that are not in the training set across the entire data set So let's get our predictions and plot the rock chart All right this is the rock chart so this。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_34.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_35.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_36.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_37.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_38.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_39.png)

Showing basically how your model is performing irregardless of where you set that threshold and looking at the rock chart can。

Some let show you the the overall landscape of how you're predicting on false positives because you've got the false positive rate and the true positive rate。

Where you set the threshold at different value now what you usually want to look for in a rock chart is how close this is down to this dashed line。

 the dashed line just shows random predictions。

![](img/0c3de78b0d0924709e45c8de93aa7c5d_41.png)

So that would be a very inefficient model if you're below this and that can happen。

 your model is even worse than random predictions and that's really bad。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_43.png)

The higher it is to this upper point here， the more accurate the better your model is you measure the area under the curve if the area under the curve is the whole thing then it's 1。

0。 So this area under the curve A you see it's typically called is 1。

0 so that's a perfect nearly perfect model This is not it's in the 99% I think on accuracy and sensitivity and specificity both but this is a relatively relatively easy and quick to train data set for breast cancer So that is binary class classification。

 let's look at multiclass classification here we're going to use that simple data set that that I've given before。

 this is a more difficult data set， so it looks a little more interesting because it gets things wrong Here we're going to build a categorical cross entropy So this is very important。

 This is one of the most common questions that students ask me about all the time in previous semesters。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_45.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_46.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_47.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_48.png)

They'll set up a classification neural network when the data is regression or they'll have a multiclass classification like this and they'll use binary cross entropy。

 you want to use categorical cross entropy because you have a multiclass classification problem here。

And you don't want to have one output neuron you want to have as many output neurons as you have classes。

 so now let's let's go ahead and run this， it'll train as I recall this gets about a 70% accuracy a little it actually did a little bit above so that's that's that's cool it has to do with the random weights accuracy Yeah。

 it's around 70% is usually what this gets Okay so it trains and the accuracy for this is usually around 70% and you can see it's it's more or less there。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_50.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_51.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_52.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_53.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_54.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_55.png)

At early stops， we'll calculate the accuracy on that。

 which will be the same value that we had up there。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_57.png)

Accuracy is 70%。 We'll go ahead and we'll calculate a log loss。 Lo loss is different than accuracy。

 Sometimes the output from accuracy is similar to log loss。 However。

 the range is quite different accuracy is  zero to1。

 log loss is0 to usually around three or four is about the highest I've seen these。

 I've never really looked at where the actual upper limit was was for that if you're above about one or two and log loss' you're in trouble。

 So let's calculate， let's see how we would actually calculate the log loss。

 we'll do our prediction here， and we'll use nuumpy to to calculate it。 The log loss is 0。74。

 which is not horrible， but it's not perfect， perfectfect as  zero， of course。

 that's how you calculate it。 that's pretty much the same call almost as accuracy except you're doing log loss。

 You're passing in the Ys that you know are correct in your predictions and it calculates it for you。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_59.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_60.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_61.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_62.png)

What is different about log loss， though， than accuracy is it takes into account confident the neural network is in wrong answer。

 So here are the outputs from the predictions。 So each row is one prediction。

 Each column is one class that it was trying to predict on。

 We can look at the bottom one because I multiplied it by 100。

 And this is essentially the predictions。 So it's saying that with 70% likelihood。

 it is the third class， not 100% sure it's it's also thinking it might be the second or the fourth one as well。

 So the way that log loss works is we tally up a bunch of log values for each of these。

 And we look at so here in this case， if this was the correct value， it is going to get the log of 0。

7 added to。The accumulator that it's going to eventually take the average of the negative of that log is the logs are negative。

 So if you think about it， if this was in the training， this would have been a one。

 we would have put a one here and all these other zeros， that would have been perfect。

 So a log of one is0 the problem with that though if you're wrong。

 And if you're wrong with absolute certainty So if if the first class would have been correct。

 we would have added the log of0 log of0 is negative infinity so you'd be infinitely bad score so it punishes you greatly for overconfidence and a wrong value。

 That is why internally when this is calculated the zeros。

 it's going to move them up a little bit past zero so that your log your score is going to get decimated。

 but it's not going to become an invalid number that's essentially all there is to calculating it。

 you take the correct one and add the negative of that particular log so。Closer you get to one。

 the closer your log addition is going to be to zero and zero is good。

 so that's how it punishes you for being overly confident。

 but accuracy is very harsh because there's no partial credit with accuracy if this one can if this next one over here the fourth one was the correct answer and you pick this one inaccur you'd get no points for this and log loss。

 at least you get some points for this because you would add the log of 0。

22 the negative log of that Here's the more formal mathematical equation for how to calculate thatEssential what's happening is all the values going across the entire data set so that's the dividing it by n。

 the negative accounts for the negativeness of log functions。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_64.png)

And then we're essentially looking at using the Y coefficients。

 so the y's are always going to be zero or1， so the correct one is going to have a one coefficient and all the others is going to have a zero coefficient and cancel out so you basically end up with just one of these and the rest of these canceling out and that does the same thing is effectively taking the log of the correct value。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_66.png)

Again， this function is not really needed。 I mean， you don't need to pay attention to the code。

 We're interested in the graph of the log， so you can see that if you're close to if if you're predicting zero on the correct answer it falls off very。

 very fast so you can see that a negative or that a four is we would take the absolute value。

 a four log loss is really pretty bad you're on your way almost two to the dropoff negative two and I'm sorry2 and one and smaller values below one are the more desirable log results and of course you can't be more correct than one So this this is the entire range of the log function that we use for error evaluation So now let's look at a confusion matrix we previously defined this confusion matrix function here so we're going to plot it now what you want to see in a confusion matrix is。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_68.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_69.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_70.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_71.png)

Strong diagonal so this the diagonal is the cases where it's getting them correct You can see this on the on the confusion matrix down here this is the true label and this is the predicted label where your' and it's a little you usually want to look at the normalized one this other one's just counts but this is the normalized one so this shows you some potential some potential problems with this if the true label is a and it predicted a then that's that's a good thing。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_73.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_74.png)

However， G， for some reason， was being classified。Incorrectly is a a fair amount and you can also see that the predicted values EF and G have considerable problem here。

 so these are some of the things that you would want to look at as you try to optimize this model and your your feature engineering to try to move some of this over to here and that's a confusion matrix confusion matrixes。

 they can be used for binary classification if that's the case then it's just going to be a two by two。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_76.png)

![](img/0c3de78b0d0924709e45c8de93aa7c5d_77.png)

But if you've got multiple classes， then this a good model or a good visualization to look at for your model。

 Thank you for watching this video。 In the next part。

 we're going to see how to do the same thing with a regression neural network。



![](img/0c3de78b0d0924709e45c8de93aa7c5d_79.png)

This content changes often， so subscribe to the channel to stay up to date on this course and other topics in artificial intelligence。


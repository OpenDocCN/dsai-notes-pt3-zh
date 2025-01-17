# P58：L8.7.2- OneHot 编码和多类别交叉熵代码示例 - ShowMeAI - BV1ub4y127jj

Yeah， as promised， let me know show you a brief code example illustrating the concept of the cross entropy in code using Pytorch。



![](img/14371a06bf9967fe12243d8bb8196325_1.png)

So I have prepared a notebook I will share it with you。 You can find the link， as usual on canvas。

Or here， just on Github。Me execute this just。

![](img/14371a06bf9967fe12243d8bb8196325_3.png)

Regular boiler platelate。 So here I have a function for implementing the 1 hot encoding in Pytorch。

 It looks a little bit arbitrary with this scatter function。



![](img/14371a06bf9967fe12243d8bb8196325_5.png)

I don't really need to go over this because I think there is no other context where I think this scatter function is really that useful so you don't have to really memorize how this works if you ever need a1 hot encoding yourself。

 you can just copy and paste this function It will do it for you and also。

When we do train a softm regression model later， I will show you also code example for that and the same for multilay perceptrons and so forth。

The loss functions in Pythwach， they already do the1 hot encoding for you。

 so you actually never have to worry about it yourself。



![](img/14371a06bf9967fe12243d8bb8196325_7.png)

But if you ever have to do it yourself here you can just copy and paste this function。

 So this is just yeah how it works。 This is exactly the same example that I showed you on the slides where we have the class labels 0。

12 and 2。 and I have a total number of class labels here。

 This is the highest class label or the number of classes the same thing。

 So here we have three possible class labels right0，1 and2。



![](img/14371a06bf9967fe12243d8bb8196325_9.png)

![](img/14371a06bf9967fe12243d8bb8196325_10.png)

Also， note that your class labels should always start with 0。 So in this case， yeah。

 what we get back is for the four training examples here，4 rows。

 and each has this indicator whether it's。

![](img/14371a06bf9967fe12243d8bb8196325_12.png)

![](img/14371a06bf9967fe12243d8bb8196325_13.png)

This class， the one is denoting the class and 0 is， yeah， it's just the placeholder。

 So for the first training example， this represents class 0， class 1， class 2 and class 2。



![](img/14371a06bf9967fe12243d8bb8196325_15.png)

Then here's this softmax activation。 Oh， sorry， this is actually the net inputs。 So this is。



![](img/14371a06bf9967fe12243d8bb8196325_17.png)

AMatri of net inputs。 I created them just arbitrarily。

 So each row is again for each training example。 We have four training examples。

 So we have four rows。 and this is how our net inputs might look like。



![](img/14371a06bf9967fe12243d8bb8196325_19.png)

So these are if I go maybe to the slides。

![](img/14371a06bf9967fe12243d8bb8196325_21.png)

These are the net inputs here， these。And then now we have to apply this softm here。

 and then we get these activations。

![](img/14371a06bf9967fe12243d8bb8196325_23.png)

So yes， just for reference how the softm function looks like。



![](img/14371a06bf9967fe12243d8bb8196325_25.png)

And here's a code implementation of the softm function。So again。

 there is actually a soft mix in Pywach。 So you actually shouldn't use your own implementation because in the implementation Pywach is yeah。

 more efficient， faster。 it's more optimized， but it's here again to just illustrate how it works。

 So what we have is in the numerator this。

![](img/14371a06bf9967fe12243d8bb8196325_27.png)

Poential term so。I'm going to go here E to the power of Z。 And then in the numerator。

 we sum over these exponential terms for all the activations。 If we have three classes。

 it will be a sum over。

![](img/14371a06bf9967fe12243d8bb8196325_29.png)

3。

![](img/14371a06bf9967fe12243d8bb8196325_31.png)

So that's what we have here。

![](img/14371a06bf9967fe12243d8bb8196325_33.png)

Now let's do that。 So we have our Z here。 We have three classes，1，2，3 and four training examples， 1。

2，3，4。

![](img/14371a06bf9967fe12243d8bb8196325_35.png)

So these are then the softm activations that yeah that we get back。

 Not that the columns should sum to one。Can just double check that。嗯。This。



![](img/14371a06bf9967fe12243d8bb8196325_37.png)

So you can see they all sum to one。No， columns。

![](img/14371a06bf9967fe12243d8bb8196325_39.png)

Looking good。 Allright， now just to illustrate how we get the class table。

 So if we look at this one again， I mentioned we have an arcm here。 arcm is you can think of it。

 Maybe I should demonstrate this。

![](img/14371a06bf9967fe12243d8bb8196325_41.png)

![](img/14371a06bf9967fe12243d8bb8196325_42.png)

It's giving you the position。哦。The highest value。So if I have an example。Let's say torch tensile。1，2。

3，4。 The archex would be the highest value。 So in this way， the archx should give me 0，1，2，3。

 the value 3。

![](img/14371a06bf9967fe12243d8bb8196325_44.png)

嗯。Weird here， okay， what's going on？

![](img/14371a06bf9967fe12243d8bb8196325_46.png)

Oh， okay， sorry。I I should。

![](img/14371a06bf9967fe12243d8bb8196325_48.png)

4 yeah。 So yeah， I was just。Not paying attention。 Alright， so this gives me the value 3 as expected。

 So if I put。

![](img/14371a06bf9967fe12243d8bb8196325_50.png)

A5 here， this would return 0 now because now the zeroth position has the highest value。

If you have a tie， I honestly don't know what happens when we have a tie。

 what I suspect is it will pick the first value， the lower value。Yep， that's exactly the case。

 So if we have a tie， it will always pick。

![](img/14371a06bf9967fe12243d8bb8196325_52.png)

The lowest value。ok。So。

![](img/14371a06bf9967fe12243d8bb8196325_54.png)

But yeah， in practice， it will be very unlikely that you have a tie here， I mean。Might happen， but。

 I mean， there could be something like this for the other classes where we have a tie。

 but usually it's， it's rare。

![](img/14371a06bf9967fe12243d8bb8196325_56.png)

Alright， and this is， yeah， also only a tie because I put this as a tie。

 Usually it's very rare that you have exactly the same values because that means that the feature vectors look exactly the same。



![](img/14371a06bf9967fe12243d8bb8196325_58.png)

![](img/14371a06bf9967fe12243d8bb8196325_59.png)

And the vector that the weight vectors are exactly the same。



![](img/14371a06bf9967fe12243d8bb8196325_61.png)

Allright。It'sConvers to class labels。 This is just to double check。



![](img/14371a06bf9967fe12243d8bb8196325_63.png)

So。ThisThese were all true labels from the one encoding。

 is this just to double check that we that this one indeed converts back to this one。



![](img/14371a06bf9967fe12243d8bb8196325_65.png)

![](img/14371a06bf9967fe12243d8bb8196325_66.png)

And here， these are our predictions。 So we used the arc max to get the column with the highest probability。

 So we get this one。

![](img/14371a06bf9967fe12243d8bb8196325_68.png)

This one。This one。 and this one。

![](img/14371a06bf9967fe12243d8bb8196325_70.png)

And you can see there's one wrong prediction if we would compare those， right，0 and0。

 this is correct，1 and one is correct。Predicted class A 0。 The true label is2。 This is incorrect。



![](img/14371a06bf9967fe12243d8bb8196325_72.png)

This one is correct。 So we make one mistake， actually。So it's also， I mean。

 I did this on purpose to show you how this whole thing works， because if we wouldn't make a mistake。

 we would get a loss of zero， which would be kind of boring， I think。



![](img/14371a06bf9967fe12243d8bb8196325_74.png)

Alright， so yes， again， the cross entropy。 again， recall that there are two sums。

 So if I go back here。 So we have these two sums here， I kind of entangle them a little bit。

 So we have。

![](img/14371a06bf9967fe12243d8bb8196325_76.png)

![](img/14371a06bf9967fe12243d8bb8196325_77.png)

This is sum over the training examples。 And this one is the cross entropy for the。



![](img/14371a06bf9967fe12243d8bb8196325_79.png)

![](img/14371a06bf9967fe12243d8bb8196325_80.png)

10 en codingding。 So this one is the， you know。Not one here。So let's compute first the cross entro P。

For each training example， so。

![](img/14371a06bf9967fe12243d8bb8196325_82.png)

What I'm doing here is， I'm computing these。

![](img/14371a06bf9967fe12243d8bb8196325_84.png)

Terms。

![](img/14371a06bf9967fe12243d8bb8196325_86.png)

I actually said that this loss will be zero， but that I don't know why I said that， the loss。

 even though you match the right class labels shouldn't be necessarily be zero except。



![](img/14371a06bf9967fe12243d8bb8196325_88.png)

If your activations match exactly。Here one hot encoding matrix。

Because remember from the logistic regression lecture。

 we want to maximize the probability for the correct class。

 but it's only maximized if the probability is 100% right， so here even this is correct。

 even if 0 is the right class。 This is not 100% probability。 So here we still have a loss right。

 because it's minus lock 。37 just wanted to clarify， sorry， Where were we。



![](img/14371a06bf9967fe12243d8bb8196325_90.png)

![](img/14371a06bf9967fe12243d8bb8196325_91.png)

Yeah， so here for the training examples， the losses we get is 0。96。881。05 and 。83。 So this is。



![](img/14371a06bf9967fe12243d8bb8196325_93.png)

Computing this one， really the inner loop。 So these correspond。



![](img/14371a06bf9967fe12243d8bb8196325_95.png)

To these computations here。

![](img/14371a06bf9967fe12243d8bb8196325_97.png)

Alright， so。

![](img/14371a06bf9967fe12243d8bb8196325_99.png)

That is how we would implement this。Now， maybe I can just briefly show you also how that looks like。

 we are just taking the lock of these softm activations and then multiply it by the target。

 and remember the targets are just zeros and ones， right。



![](img/14371a06bf9967fe12243d8bb8196325_101.png)

I didn't define it。 That's interesting。 Oh， it's in， sorry， it's。ItShould be。

 I'm calling it as y ink， which gets passed to Y target。 So let me。



![](img/14371a06bf9967fe12243d8bb8196325_103.png)

Like this。 So it's zeros and ones。

![](img/14371a06bf9967fe12243d8bb8196325_105.png)

So。I can maybe also print it if you and curious。 So this would would be。

One value and the other one should be zeros。

![](img/14371a06bf9967fe12243d8bb8196325_107.png)

So one value and the other one zeros and each。Wron， there's only one。Value that is not0 in each row。

And then we are summing， we are just summing over this。 This is the auto sum here。 So the first row。



![](img/14371a06bf9967fe12243d8bb8196325_109.png)

Would be 。68。So and so， Second row would be 0。88 then 1。05。 This is actually what we see here， right。

 So the summing is actually just selecting it's just selecting the yeah， the value here。



![](img/14371a06bf9967fe12243d8bb8196325_111.png)

Okay。

![](img/14371a06bf9967fe12243d8bb8196325_113.png)

Yeah， I'm cleaning this up here because when I upload this。

 so you have the clean version without my weird interjections here。 Alright， so in Pythrch。



![](img/14371a06bf9967fe12243d8bb8196325_115.png)

There is a function called an L， L loss。Which。Takes the lock soft next as input。 So this function。

 the negative lock likelihood loss expects。

![](img/14371a06bf9967fe12243d8bb8196325_117.png)

![](img/14371a06bf9967fe12243d8bb8196325_118.png)

The lock of the softm values。 I'm just saying that we will use them in practice。

 We will actually use the cross entropy in practice。

 but I'm yet trying to explain how these functions and pythage work。

 So you can see this negative lock likelihood loss is the same as our cross entropy here。



![](img/14371a06bf9967fe12243d8bb8196325_120.png)

Like， I explained in。

![](img/14371a06bf9967fe12243d8bb8196325_122.png)

When we go up， I think I had a video on that in logics and cross entropy so。



![](img/14371a06bf9967fe12243d8bb8196325_124.png)

Where I mentioned that the negative log likelihood and binary cross entropy equivalent in Pyr is's actually the negative log likelihood and the multicatery cross entropy equivalent I mean。



![](img/14371a06bf9967fe12243d8bb8196325_126.png)

![](img/14371a06bf9967fe12243d8bb8196325_127.png)

In a way， you can also think of it as a multi category 1。

 the multinial logistic regression then this would be still true。 So they are equivalent。



![](img/14371a06bf9967fe12243d8bb8196325_129.png)

嗯。But notice it's really important to pay attention to this is that it takes the lock soft Max input。



![](img/14371a06bf9967fe12243d8bb8196325_131.png)

So this might be counterintuitive because。There is aria lock inside， right。But。The Py version。

Does not perform this look here。 It expects that you perform at Flor pytorch。So。Pytorch， really。

Things you provide this serious input instead of the activation。



![](img/14371a06bf9967fe12243d8bb8196325_133.png)

Just want to clarify this it's important to note because here we give the softm input。

Here we give the locks of nexus input。Right， because when I just give the softm input。

 I will get wrong results。 I will get some。I just luckily my glass was empty。 alright， sorry。

 So you notice that now we have negative values here right， So this is not what we want。

 So you have to pay attention that this is actually the lock。



![](img/14371a06bf9967fe12243d8bb8196325_135.png)

I'm just emphasizing this because it's a common mistake in practice when people implement deep neural networks。

 they accidentally sometimes provide the wrong inputs and then get weird results and then the networks are not training。



![](img/14371a06bf9967fe12243d8bb8196325_137.png)

In practice， actually， I recommend using this cross entropy function over the negative look likelihood function。

This is numerically more stable。 So if you train a deep neural networks。

 the gradients and everything will be more stable if you use that one。Mathematically。

Everything would be equivalent。If we use negative look like or cross entropy in Pythrarch。

 but numerically like stability wise on the computer， the cross entropy1 is more stable。

So and also for this one。Really pay attention to this one。 It's taking the los at as input。

 So it's taking our net inputs as input。 So here， again， this is our net input matrix。



![](img/14371a06bf9967fe12243d8bb8196325_139.png)

![](img/14371a06bf9967fe12243d8bb8196325_140.png)

![](img/14371a06bf9967fe12243d8bb8196325_141.png)

When we compute the cross entropy， because we use the mathematical formulas。

 we compute first the softmax and then。

![](img/14371a06bf9967fe12243d8bb8196325_143.png)

From the softm， we compute the cross entropy in Pytorch。

 they do all that work for us inside this function。 They do it for us。

 So here we give it the net inputs。

![](img/14371a06bf9967fe12243d8bb8196325_145.png)

![](img/14371a06bf9967fe12243d8bb8196325_146.png)

And you can see。Our function takes the softm， it gets the same results。

It's these other functions right， so they should be all identical。

 but in practice this is more stable， I recommend using this one。



![](img/14371a06bf9967fe12243d8bb8196325_148.png)

![](img/14371a06bf9967fe12243d8bb8196325_149.png)

And notice that I set reduction to none， which means it does not apply the sum or the average。

 which is this outer one here。

![](img/14371a06bf9967fe12243d8bb8196325_151.png)

![](img/14371a06bf9967fe12243d8bb8196325_152.png)

So by default， when you use this cross entropy。

![](img/14371a06bf9967fe12243d8bb8196325_154.png)

It will perform the average you can test it like this， see it's the same same value。



![](img/14371a06bf9967fe12243d8bb8196325_156.png)

If you wanted to， you can also say reduction to。Consider reduction to sum。sorry。这边X。

So you can see you can also do the sum， it's equivalent。

 but in practice I recommend using the mean because like I said。

 it's more stable in terms of choosing a good learning rate。

 it's easier to find a good learning rate if you use the mean compared to the sum。



![](img/14371a06bf9967fe12243d8bb8196325_158.png)

Right， so this is like a core example of how all these types of losses and pagerotch work。

I recommend you just to play around with that。When we implement a softmax regression in a later video。

 I will use this function。 And also when we use later on。

 multilay perceptrons and convolution networks we will be using。



![](img/14371a06bf9967fe12243d8bb8196325_160.png)

This function。 Allright， so in then in the next video。

 I will go over how we yeah compute the gradients for such mixed regression。



![](img/14371a06bf9967fe12243d8bb8196325_162.png)
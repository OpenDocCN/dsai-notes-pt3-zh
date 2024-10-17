# P55：L8.5- PyTorch 中的逻辑回归 - 代码示例 - ShowMeAI - BV1ub4y127jj

Yeah， before we move on and talk about the multi class example of logistic regression。

 the so called softmax regression， let's just wrap up everything we here talked about in the previous four videos in a code example。

 So I prepared a code notebook。 You can find it on Gith。 I will share the link on canvas。😊。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_1.png)

Where I have implemented two things。 So the first thing is logistic regression from scratch。

 just yeah， from the ground up， low level implementation of logistic regression。

 really like implementing。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_3.png)

The learning rule that we talked about here。And then I will show you how we can do that using the Pythr utilities。

 the module API that we talked about last week where we have this N dot linear layer and so forth。

 This is something we would do in practice when we have， of course， more complicated networks。

 but I thought from scratch implementation is still useful from the learning perspective so you get a better feeling of how logistic regression works。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_5.png)

So， let's get started。So， of course， first my watermark， you can ignore the torch version。

 this torch version doesn't exist。 actually， I yesterday。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_7.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_8.png)

Compiled torch from sources to test something。 So this should also work on torch of 1。

7 so no worries can ignore that。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_10.png)

Yeah， so。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_12.png)

B的。Po of matpotlet， which we'll be using Ny， we will be using。

 And then the torch stuff we will be using。 So just some inputs to get them out of the way。

 we will be using some simple toy data set。 That's like， yeah， just。

 I think that is what I gave you also for the homework， to be honest。 I have to double check。

 I made multiple of these toy data sets。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_14.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_15.png)

But， that's just a simple binary classification dataset set。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_17.png)

Now here is my logistic regression implementation。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_19.png)

So how does it work？ So I'm using the roughly same way how we would implement that using Pytorch with a module API。

 So here I am implementing forward and backward manually。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_21.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_22.png)

These are the two methods where forward is， yeah， the forward pass and backward is the gradient descent computing。

Yeah， the gradient of the loss function。I actually let me modify this。

 Let's call that loss with respect to。 So W RT means with respect to。 I think it makes it clearer。

 So that's done。Graing of the loss with respect to the output， and so forth。

We'll just modify it everywhere here。And then。Let's do it step by step here。

 So then here in the init function， this is like the function or method that get ex gets executed when we instantiate a new object from this class。

 What we have is the weights and the bias unit。So the weights we initialize them to to zeros。

 so we use the zeros function to initialize them to zeros。 It's a vector， a one， it's a row vector。

 basically a one times nu features vector， so matrix。 so it's essentially a row vector so。

Numb features is the number of features in the dataset。

 So the number of weights is equal to the number of features just like an Adeline。

 and we only have one bias unit。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_24.png)

Alright， so the forward method， yeah， this is computing the net input， right， So this is。

The net input can also call it Z。Can。😔，We could technically call it an a。

 but you know what we mean right， I mean， I can rewrite this maybe。Doesn't really matter。

I can just leave it like that。 I think I'm underestimating you。

 I think it's probably all clear to you。 I don't have to use these different words。 alright。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_26.png)

Sorry， so。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_28.png)

The backward method is， yeah computing these gradient terms。

 This is going back to what we've done here。 So here I'm computing the gradient of the loss with respect to the output。

 So this is essentially this part。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_30.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_31.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_32.png)

Here。Then the grain of the loss with respect to the weight， this is。This part here。

Where I put those two things together so。This should probably be with respect to the the and Z。

 the net input， this may be clearer instead of saying output。

So this is matrix modificationification between。X。And this term。

 I just rearranged that to make the dimensions match， which is why I have the transpose。 you。

 to be honest， don't have to memorize these details。

 You will probably find out by tinkering with the code if you ever implement something from scratch because here this is really for one weight。

 And here I have that vector implementation for multiple weights， right because we have。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_34.png)

The number of weights equal to the number of features。 It's a bit more complicated。

 but the concept is the same。 So this line here really is this part here。

I can actually also maybe go to this part here。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_36.png)

This， this part here， this。Is essentially this one here。

 the gradient of the loss with respect to the weight。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_38.png)

And then the same for the bias， which would correspond to this part here。

Here this is the threshold function， predict labels。

 So I'm calling forward that gives me the probabilities a， so a is the probabilities Pros。

 I call them Pros because in the lecture I said also it was a bit complicated when we had Y hat and it was confusing so。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_40.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_41.png)

Referd to a as the probabilities。That's the sigmoid activation here。

And this is the threshold function where if the probabilities are greater than 0。5。

 return class label 1。 Otherwise， return class label 0。 I could， however， also。

Do it as with the net inputs， I could say if the net inputs。

Let's call them 0 are greater than 0 than return 1。 Otherwise，0。 This is because。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_43.png)

What we discussed here。So here's the threshold function。 And because。The probabilities with that 。5。

 the net input is 0。 So either we can operate directly on the net input or the probabilities here。

 So you have that with the probabilities， but doesn't really matter that much。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_45.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_46.png)

Okay， so here's just an evaluation function， so this is not super interesting。

Here I'm predicting the labels， which in in turn uses this method here。

 which computes forward and then the threshold function here。So we can call it a threshold。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_48.png)

Fction。And then， in order to compute the accuracy， we。Some。Over the correct predictions。

 So every time the class label matches the。The predicted labels here。

Matches the actual class tables every time they match。We sum it up。

 So this is a number of correct predictions and then divide by the size of the training set。

 So it's a value between 0 and 1。 It's the proportion of correct predictions。 Why do I do float here。

 It's because the class labels are integers。 And yeah， in Pythage。

 it's a little bit tricky to compute or compare things like floats， The labels are floats here。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_50.png)

And then this is Integer。 I think I could have omitted this here。

 It's maybe a little bit complicated。 I could have was think done。That。

 and it would also have the same effect。So， but anyways。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_52.png)

Okay， anything else。 Yeah， this is a sigoid function， which you have seen a lot of times。

 So there is this function here。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_54.png)

Yeah， the loss function。 That's the negative look likelihood， which we have。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_56.png)

Right here at the bottom， that's the。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_58.png)

We'll just take a cost function。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_60.png)

And here's the training function， so here。Again， let me jump back to this one。We are right here now。

 So for every training apoch。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_62.png)

For E in the number of epochs， we compute the outputs， which is here。 That's the probabilities。

 the A's。 So this is really this should be an a actually。 So remember。

 this was copied from the a line should have。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_64.png)

Probably adjusted it to an A here。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_66.png)

But you probably know what I mean。 Then we compute the gradients。 So these are under B。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_68.png)

Here。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_70.png)

Then we update the weights， which is C this part here。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_72.png)

And this is it。 And this is just for， yeah， logging。

 just keeping track of everything like looking at the results and the loss score。

 which can be useful。 So let's actually do that。 Let's。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_74.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_75.png)

Yeah， do that here。 What I'm doing is I'm converting the numpey。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_77.png)

A racese to torch tensors。 because if you go up here。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_79.png)

You can see， I。Use nuy here。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_81.png)

So to load of data。 So here I'm just converting them to torch tensrs。

 Then I'm initializing my logistic regression model。 So this will be actually step  one initializing。

And then Im calling train train would be everything under two here。

And then I'm printing the model parameters， the weights in the bias just to take a look at them。

 and I'm training for 30 epochs。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_83.png)

With a learning rate of 01。So I think that's the mistake I always make I talk through this。

 but I usually forget to execute this。 Okay， now we are。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_85.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_86.png)

Running the code， okay， we've got an arrow here。Okay， I yeah， I changed the。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_88.png)

Name one second。 Let me fix that。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_90.png)

Alright， so it's training。 You can see it's blazing fast。

 It starts with already a very high accuracy after the first epoch， to be honest。 So it's yeah。

 it's actually training super fast。 The cost is very low。

 but you can see if I do more epochs that goes even lower。

 the accuracy goes up to 100% here even but you can see even though the training accuracyies or 100%。

 the loss still goes down。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_92.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_93.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_94.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_95.png)

I could have trained more and would go maybe down further。

 but that at that point might not be necessary。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_97.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_98.png)

Might be overfitting。嗯。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_100.png)

Wanted to execute this part。Okay， theres some message here。

 I think this message comes from Ny because I recently installed a very recent version of Ny。

 and it must be something in Matpl here。 You can actually ignore that that this is not。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_102.png)

Arrow message that is just a warning。 So if you see warning or deprecation warning。

That means things are still working。 so don't worry about them。 But in future。

 if there's an even newer version of a software library in Python， this may not work anymore so。Here。

 this is nothing we are doing wrong。 This is probably something inside Matpro lip。

 and I'm sure they are already aware and working with that。 so don't worry about this warning。

 Everything still works fine。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_104.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_105.png)

There will be probably a new met product version that addresses this issue at some point。

 but everything is fine。 Yeah， you can see here is how the lock， yeah。

 the negative look likelihood loss looks like。 So it should be the negative。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_107.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_108.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_109.png)

Not likelihood loss to be precise。 And then over the number of epos。

 you can see maybe it will go down further。 You can see it's actually going steep down。

 But whether it's actually helping， I don't know because we already get 100% training accuracy。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_111.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_112.png)

So let's take a look at the test accuracy， it's only 96%。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_114.png)

For completeness， we will also take a look at the。Yeah， it this year。 So yeah。

 we can see actually here on the training set， the decision model looks quite good。

So it's dividing both classes class0 and class1 on the test that yeah。

 it's not performing so well because there's this one outlier point， right so here。

This one is not classified correctly。 So if this decision body would go a little bit more to the right。

 then we might get this one correct。 but at this point。

 this model only see a training that I doesn't know of this point here on the right hand side。

 So in this case， I think training the model further wouldn't really help because this is already doing a good job here actually maybe putting a little bit more to the right would help actually because then would be more here。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_116.png)

没有。😔，Anyways， this is just an example， of course I just implemented this quickly in a way that I didn't really find tune in anything。

 and this is a toy data set anyway， so don't over interpretterpret this Okay so the goal here was really to show you if I scroll up again to show you how we implement this from scratch like the most interesting part I would say is the backward function which is a little bit different from the Adeline function。

 the rest should be all the same as in the Adeline implementation so it's not that new to you I hope。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_118.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_119.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_120.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_121.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_122.png)

Now， I want to show you， though， how we yeah， use the module API to implement this logistic regression module so here。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_124.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_125.png)

This should do exactly the same thing， but now I'm relying on in build or build in pytorch functions。

 So I'm using this self dot linear here to refer to my torch dot in end dot linear layer。

 This is a layer that computes the net input。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_127.png)

However， note that by default， this will initialize the weights to small random numbers。 Later on。

 this will be very useful， but it is not that useful to compare it to our model above because if you recall above I initialized my weights and bias to 0。

 So I want to do the same here。 so I can compare the two models。

 So what I'm doing is manually assigning。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_129.png)

0 to the weights， and by unit。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_131.png)

嗯。Yeah， and then we have the forward method。 So here the forward method。

 we compute the logicits via the self to linear， which is this fully connected layer or linear layer。

 and then we have built in py function that computes the sigmoid activation function。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_133.png)

So you can see a logistic regression model is actually super simple， actually， we can also。

 it would train just fine if we have this one。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_135.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_136.png)

Just for comparison person reasons I have this one， but you can see how simple it is。

 and it will already implement the backward function for us。 We don't have to do it ourselves。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_138.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_139.png)

Here we are using the stochastic gradient descent。嗯。Optimizer， so this will update the weights then。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_141.png)

So this will compute the gradients via other the backward and update the weights。

 So we are just specifying what weights we want to train。 This is the model parametersus here。

 Model 2。 So this is。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_143.png)

Model 2 or one logistic regression model 2 Model 1 was the from scratch implementation。 right。

 so here is just an accuracy function to compute the prediction accuracy。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_145.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_146.png)

We are training also for 30 epochs。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_148.png)

Like before， what Im doing is I am casting the nuy。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_150.png)

A raised to a tensor， I've already done that， so it's probably redundant。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_152.png)

And now here' is my training loop in Pytorch。So， for each epoch。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_154.png)

I compute the outputs。 These are the probabilities。 This is from the forward pass。 This is。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_156.png)

These probabilities here。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_158.png)

Then I use this cross entropy， binary cross entropy function。

 and this is essentially why I spent some time in the last lecture， last video here when we had it。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_160.png)

When we had this topic here， why I spend some time Yeah just telling you that the negative log likelihood and binary cross entropy are equivalent。

 same thing。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_162.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_163.png)

Here I'm saying reduction sum， because that's what we have done here。 It's a sum。

 or we can also do the average。 Actually， if I change this， it will be the average or。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_165.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_166.png)

Mean by the default。 But since we implemented above the sum2， and I have the sum here， I'm also。

 for comparison reasons use the sum here in practice， I think using the mean is more stable。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_168.png)

For with regard to learning rates and different batch sizes。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_170.png)

Yeah， and then this is really like what we have done in the last week when we trained Adeline using these automatic things。

 we。Have the following， we compute the loss。I。Traditionally use the term cost。

 but I think loss is more natural now nowadays than we。Yeah， set the optimizer。0 gra。

 which will yeah reset the gradients from the previous round。

 Otherwise the gradients will accumulate， I I explained last week。

Then we compute the gradients for the current round and then update the weights。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_172.png)

And this is essentially it。 Let's run this。Alright， error。 Model 2 is not defined。 See。

 I always forget to execute things。 Alright， let's execute this one。 and then this one。 Yeah。

 it trains。 Okay， so and you can see if you recall， these have the same values as we've seen before。

 I can just scroll up in a second and just to show you。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_174.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_175.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_176.png)

And also take a look at these weight parameterss。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_178.png)

Can just copy and paste them。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_180.png)

So yeah you can see they are exactly the same， so we learned exactly the same using Pyhar。

 which gives us confidence， I hope that we understand gradient descent correctly and implemented。

 yeah， the gradientding here correctly。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_182.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_183.png)

So it's the same as in Pytorch。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_185.png)

Allright。Yeah， and this is it essentially。 So evaluating the model， same tester accuracy。



![](img/eb410a541f0e309c0b9d6e6b05498cf9_187.png)

Because it's the same weights and bias， so it should be the same decision boundary。

 which we can see here。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_189.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_190.png)

Yeah， so this is how we implement logistic regression。

 I hope that was helpful like understanding a little bit better how these different concepts here in the slides work。

 You may also want to work through this more slowly。 I think that might be also helpful。 but yeah。

 that's it。 So the next video we will then talk about how we can generalize these concepts to multiple classes。

 That means like more than two classes。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_192.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_193.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_194.png)
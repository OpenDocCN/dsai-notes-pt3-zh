# P149：L68.3- 梯度惩罚 - ShowMeAI - BV1Dg411F71G

So now that we saw an application let's go ahead and play around with the loss function and let's go back to what they' trying GNs and try to improve it。

 try to improve its training process let's recap what GANS was doing this is GANs you have a discriminator which is discriminating between real and fake images and then you have a generator that you training and Xtilda here is just G of Z Z you're sampling from a normal from a simple distribution and then we learned that this is going to give you the gensen channel dirgence and then we saw that if you use the original objective you're going to have trouble converging because this is going to saturate at least initially during training so let's just change that rather than minimizing that objective we respect to G let's maximize with this speak to G and this is your new objective function that's GANS and this we covered this was a quick recap because I want you to compare the math in one slide。



![](img/2734b9299324eb0b2b6b318b8e29284a_1.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_2.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_3.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_4.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_5.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_6.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_7.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_8.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_9.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_10.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_11.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_12.png)

This was a astr again we know that it was related to the Earth mover distance you had the intuition for the Earth mover distance or at least where the name is coming from is because you are transporting mass from one distribution to the other distribution and you wanted to have the minimum cost and the cost is mass times the transpose distance the transport distance and mass here is your probability or probability distribution mathematicalally let's use the same notation previously we were using F let's use D to see the similarity between the two objectives here this was a discriminator now you're going to call it a critic because this is not a discriminator anymore this is not going to give you probabilities as output now you can see that you are getting rid of the log in this new objective the first term is the first is the same as the first term of the first term up there basically you can rename log of D to be your new D and then。



![](img/2734b9299324eb0b2b6b318b8e29284a_14.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_15.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_16.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_17.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_18.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_19.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_20.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_21.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_22.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_23.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_24.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_25.png)

This plus is changing into a minus maybe because you have a minus here so that plus is turning into a minus and then you are getting the log you are getting rid of the lock so these two objective functions are very similar and youre getting rid of the seatoid and the lock in your v restrain can but then you had a cache here this D was the space of lips shits con functions so D is a set of one lipsheds functions and one is the lips sheets continuity constant and in the original paper we we know that this is a big problem in neural networks it's a little bit hard to enforce lips sheets continuity maybe one at hard method is to clip the weights of the critic to be inside a inside a box that you choose but then it's not going to be one lip sheet it's going to be klips the idea here is that you're going to use gradient and penalty there is this theorem in the paper。



![](img/2734b9299324eb0b2b6b318b8e29284a_27.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_28.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_29.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_30.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_31.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_32.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_33.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_34.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_35.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_36.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_37.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_38.png)

And it's actually not there the theorem is not theirs。

 they're borrowing it from another paper in the literature and what does it say it says that if you have a differentiable function and we know that neural networks are differentiable okay it is gonna be one liphes if and only if so this is a two sided it's gonna be one lips sheet if it has gradients because this is where you're going to need the differentiability if it's differentiable you're gonna know its gradients theyre gonna have a norm that is as big as one at most as big as one okay perfect now you have a theorem that you can use if you have a differentiable function it is gonna to be one lips sheets if and only if it has gradients with norm that is at most one everywhere let's use that this is your original cr loss function。

 this is what you have up there and then here you're going to put a gradient penalty you don't want the norm because you need to have a norm you don't want。



![](img/2734b9299324eb0b2b6b318b8e29284a_40.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_41.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_42.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_43.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_44.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_45.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_46.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_47.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_48.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_49.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_50.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_51.png)

Norm of the gradients of your critic to become bigger than one。 So that's a penalty。 Actually。

 this penalty is trying to make all of them as close as possible to one okay you put a gradient penalty with some penalty parameter and now this is trying to enforce the lipsiate continuity using this theoryorem So you're modifying your loss function slightly and you might wonder what is this x tilda x tilda are coming from the generator x is coming from the real data distribution and this x hat is just a linear interpolation between the two it's a random point between these two points So youre enforcing it on that you have the real data you have you have the real data you have the generated data and you have a bunch of data in between where you are enforcing this objective okay it says that the previous method clipping the weights of the。



![](img/2734b9299324eb0b2b6b318b8e29284a_53.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_54.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_55.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_56.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_57.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_58.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_59.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_60.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_61.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_62.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_63.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_64.png)

Gadient is trying to modify the architecture of your neuron network by clipping the weight。

 This one is not modifying the architecture of the neural network。

 it is just penalizing if your neuron network during training is violating the one liphes continuity property you're going to penalize it in an indirect fashion through this theorem Why is this penalty two sided shouldn't you just penalize gradient norms that are greater than one Yes。

 that's a good that's a good question but then that's going to be hard to enforce it at least this one it's easier to enforce Basically what you're saying is that if the gradient of this cr is approximately equal to one then this is going to be atmost one sometimes it's going to go above。

 sometimes it's going to go below but then it's going to be approximately equal to one and then you're going to use this theorem go backward and that's going。



![](img/2734b9299324eb0b2b6b318b8e29284a_66.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_67.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_68.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_69.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_70.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_71.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_72.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_73.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_74.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_75.png)

You wants so it's not the entire family of leafute functions it's just the ones whose gradients are equal to one but then at least this is the intuition you want it to be approximately equal to one according to this theoryorem so you are not respecting this theorem line by line you are respecting it approximately okay does that answer your question yeah so I guess I guess it empirically it perform just as well that makes sense but intuitively I could also simply take the max of the norm minus1 and zero and then that would be one sided you are right but then the problem with using such functions such as max etc is that they are not differential so you want your objective function to be nice as well Okay so it answers my question so yeah it's one matter to write a loss function and it's another matter for the loss function to be trainable now this is a loss function that is trainable。



![](img/2734b9299324eb0b2b6b318b8e29284a_77.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_78.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_79.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_80.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_81.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_82.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_83.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_84.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_85.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_86.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_87.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_88.png)

I'm not saying max is not going to be trainable， but then it's going have maybe it's gonna to have a harder time converging Okay I I'm still confused about this X the sampling uniform and straight lines between x x total So the question is where you're going to enforce this because you want this to be almost everywhere you cannot sample your entire space because that's going to be too big remember these are high dimensional images you're not going to be able to sample the entire space you want to compute this expectation in an efficient way maybe the efficient way is just look at the line between the real example that you just saw and the generated example and then look at the line between the two just sample do your expectation on that line got it otherwise the space is too big it's not going to be possible to span the entire space I think we are finishing right on time for those。



![](img/2734b9299324eb0b2b6b318b8e29284a_90.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_91.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_92.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_93.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_94.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_95.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_96.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_97.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_98.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_99.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_100.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_101.png)

If you want to leave it can leave and for those of you who want to stay and ask questions I'll be around I a question on the previous slide I don't know if you can go back to that just so I can so I understand like with these loss function I sort of I understand each individual one but I'm a little confused how they's sort of being pieced together it seems like we have this this first loss function which is LSR and then we're defining LSR up to the right but what how does this like regularganAN loss function fit into that that you have below on the left here Okay thisganN loss function here is gonna to help you train D okay yeah that's for training D once you know D you're gonna be able to train G and that's this loss function here the LSR G is exactly what you have up there as well Okay okay so that part is clear the generative part。



![](img/2734b9299324eb0b2b6b318b8e29284a_103.png)

![](img/2734b9299324eb0b2b6b318b8e29284a_104.png)

Is clear with some coefficient you're just multiplying and waiting it properly Now the question is what is this you have multiple options for that you can use MSE you can use vg G Yeah and that part makes sense to me so with this bottom left loss function we're just looking at training theta D in that will give us this And then once we start training theta G that will be this LSR G exactly it's going to give you that Okay and by the way。

 you are not going train this all the way you're going do。

partial training so you're going to do a sequential training you train G for a bunch of iterations then you train D then you train G etc and hopefully by the end of the training you have the last function that you need out of D okay the perfect scenario would have been to train D perfectly per each sample that you generate or per each iteration that you update the parameters of your G but then it's not feasible so you're going to do the consecutive training you train that for a bunch of iterations then then you train the other way yeah okay thanks yeah sure。


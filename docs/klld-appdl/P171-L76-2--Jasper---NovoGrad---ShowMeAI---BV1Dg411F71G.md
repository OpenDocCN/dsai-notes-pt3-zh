# P171：L76.2- Jasper & NovoGrad - ShowMeAI - BV1Dg411F71G

That case we move on the previous paper was about data and your loss here we are going to go back to CTC loss but then work on the design of our convolution on neural network or our neural network in general this is an engineering paper so there is gonna to be a lot of trial and error going on so that in the end you get a better performance in terms of your order rate so you are going to do a lot of experimentation so this is not magic that they come up with this architecture they put a lot of time and GPU hours to produce these results and B test data of the art you take your spectraltrogram you do convolution baed on rearlu with a kernel width of 11 and these many filters to56 so that's the first convolution the next ones are going to be a bunch of residual blocks so one residual plug you repeat。



![](img/6b5a3fdad65b9332b4b1adf66cbc4050_1.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_2.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_3.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_4.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_5.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_6.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_7.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_8.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_9.png)

B times and then the last residual block the first one is pro log。

 then you're going introduce an epi log for your convolution。

 there is gonna be another convolution there another convolution a one by one convolution that's going give you your vocabulary size and then a CTC you see the architecture is just fit forward There is no encoder decoder going on and then you do a lot of work on your CTC loss and you just write it down What is this block doing it's gonna be one deconvolution batch norm value dropout and then you want to add a residual connection to the last guy。

 this one you are repeating r times but after repeating these stuff R times the dimensions are gonna to get messed up the dimension。

 the number of channels that you have so you're going fix the dimension by one by one convolution you do batch norm and then you add the input to the output here and then you continue there is a this is resnet type run。



![](img/6b5a3fdad65b9332b4b1adf66cbc4050_11.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_12.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_13.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_14.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_15.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_16.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_17.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_18.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_19.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_20.png)

Lettwork there there is a very good architecture that we cover in part one of the course and that is about dense nets this is a combination of the two this is a combination of dense nets and resnet and theyre calling it dense residual so for dense net you' are going to take these outputs from the previous layer these are coming from I don't know the first layer and then the second layer and so on and then let's say you're here now you want to combine them for dense net youre going to concatenate and then multiply by a bunch of weights here you are just going to add them together okay perfect in terms of a details of the architecture you have one block of your pro log and then you have B1 B2 B3 B4 B5 these are your B blocks and then you are going to have a kind of two here and these are all one dimension all convolutions。



![](img/6b5a3fdad65b9332b4b1adf66cbc4050_22.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_23.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_24.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_25.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_26.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_27.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_28.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_29.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_30.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_31.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_32.png)

And then you do acon3， acon4， and then you're going output the number of the size of your vocabulary and then you play around with your dropout ratio and then the number of sub blocks is this R that you're seeing here or when you're repeating R times and that's hence the name whenever you see Ja per B times R you're going have B blocks and R subpl okay perfect you wrote down an architecture you gave it some data you write down your loss function。

 you start training and you're going to use Adam and then it's not converging so you did everything that you could but then it's not converging as you expected one might say how about changing our optimization scheme so Nova grad is very similar to Adam but Adam is doing its adaptive operations per each single weight that you have so each weight in your training in your neuraln network is' going to have its own。



![](img/6b5a3fdad65b9332b4b1adf66cbc4050_34.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_35.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_36.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_37.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_38.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_39.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_40.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_41.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_42.png)

Adaptive rate Maybe that's not a good idea。 Maybe it's a better idea to combine a bunch of weights and then have a common adaptive rate for those subset of weights So how we're going to do it We know that the adaptivity in atom is coming from the gradients of our weights the gradient of your loss we respect to the weight for at you are just a squaring this for every single weight basically a derivative of your loss with respect to every single weight。

 you just square it and that's going to give you your adaptivity per every weight but now we are putting the weights in a layer in one vector and then have a common adaptive rate for that layer So it's gonna to be shared it's gonna to be a shared learning rate and that's coming from the L2 norm of your gradient So now your gradient is a vector you can compute its norm previously per single weight that's just a scalar and you're taking that the scalar。



![](img/6b5a3fdad65b9332b4b1adf66cbc4050_44.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_45.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_46.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_47.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_48.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_49.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_50.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_51.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_52.png)

Squaaring it but now this is a vector and then the adaptivity comes from taking the square root of this VTL that you just computed here and this is just to give you the momentum so the rest of it is very similar to a usual atom optimizer and at the same time you can add some weight decay So weight decay is equivalent to having the L2 norm or penalizing the L2 norm of your weight you can implement it in terms of weight decay because as you take the derivative of the L2 norm of a weight you're gonna to get this term because that's going to cancel out the two is going to cancel out and so on and now you just update now that you have a vector it's giving you a direction to go you' just going that direction you take a step and now you are going downhill so the only change is you you have an adaptive learning rate per each layer not per each weight that's going to help a stabilize the training because this is a very deep。



![](img/6b5a3fdad65b9332b4b1adf66cbc4050_54.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_55.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_56.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_57.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_58.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_59.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_60.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_61.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_62.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_63.png)

Model if you think about it it's B times R it's the depth of the model plus all of these convolutions Some of these papers let's compare the performance on a speech on library speech in terms of word error rate all of these some of them are end to end training some of them are not so you have to split the training into two parts。

 but the ones that are end to end deepest speech2 we covered the other ones we didn't have to we didn't have time to cover and this one is the previous paper listen at an and spell plus the data augmentation technique。



![](img/6b5a3fdad65b9332b4b1adf66cbc4050_65.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_66.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_67.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_68.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_69.png)

Each one of these guys are using a different type of a language model for decoding 5 gra is the simplest language model that you can come up with then there is a SM convolution language models and RNs but we know that these days we have better language models we covered them like transformer Excel and they' are going to help this model per form the best okay on all of these different cases you can do Wallace Street journal and a better language model is helping you can do H5 and then we can have different language models these are N to end they're using neural own network N to end training and whenever you see for instance 10 by5 it corresponds to Jasper B by R so you have B blocks are sub blocks and the other thing that you're seeing here is DR and data stands for tense residual so that's the architecture that you're using for these data and these other data set here。



![](img/6b5a3fdad65b9332b4b1adf66cbc4050_71.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_72.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_73.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_74.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_75.png)

Question is visually speaking what is the effect of your language model if you use a better language model the perplexity is going to go down For instance this could be your five gram language model this could be your RNN and this could be a transformer Excel and they're giving you better and better perplexity so for perplexity the lower is better and then your word error rate is highly correlated with the language model that you're using the better your language model the less mistakes you're going to make and how can you compare residual with dense residual with dense net versus dense Rnet residual net while being fair so this is trying to be fair for them to have the same number of parameters and two different data sets and you can see that the dense residual which is this architecture here is doing the best but these numbers are very close to each other here you' are seeing most of the performance gain。

Any questions。 I had a quick question Sure， in the， the farthest， the table on the far left， it。

 it seems that the L S model is performing the best。 Am I， I interpreting that correctly。

 even though it doesn't have data for everything。So you mean this LAS model yeah the one we covered earlier so yes。

 they are not reporting these numbers so we don't know what those numbers are， but yes。

 you are right here it's giving you 2。5 here and then 5。8 here。

But this is using a different type of framework a different type of a loss function and then at the same time doing augmentation data augmentation is this I don't know if we'll talk about this later but I mean will we see that these encoder decoder type architecture's outperform the type of architecture that we're considering here that uses the CTC loss and not necessarily so they usually compete against each other so these are two different frameworks that they compete against each other maybe the performance game is because of the augmentation Okay but yes I want what I want you to know is I want you to know both of them I don't want you to stay in your comfort zone because this is easy this we covered in for our text but I wanted you guys to know that there is a different way of writing your loss function and we're gonna to hear about that a lot so I wanted you guys to know what is CTC if you read it somewhereber。

And I think both of them are useful， any other questions？


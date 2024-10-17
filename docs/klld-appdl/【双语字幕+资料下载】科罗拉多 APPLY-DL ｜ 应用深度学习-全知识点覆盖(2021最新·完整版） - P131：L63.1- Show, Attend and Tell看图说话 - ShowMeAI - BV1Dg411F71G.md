# P131：L63.1- Show, Attend and Tell看图说话 - ShowMeAI - BV1Dg411F71G

We all know that attentions are important， but to be honest。

 this is one of the first papers that introduced attention and this was for images。



![](img/617262a339eed8504a813be6f1cd053e_1.png)

![](img/617262a339eed8504a813be6f1cd053e_2.png)

And let's try to go through that you're going to show an image you're going to attend to the part of the image that are relevant and then you're going to talk about them。

 you're going to generate a caption for the encoder。

 you want to generate captions so your captions or sequences of length C so I'm just introducing notation H Y I here is a one of K encoded word K is the size of your vocabulary C is the length of the caption a you take an image and then turn it into a set of feature vectors using a Cna so this is going to become more clear if I give you an example let's take an image and that image is going be 256 by 256 these are the number of pixels the height and the width of your image and it's going have three channels so each image is a tensor it is going to be 256 by 256 and3 you take an image and then you push it through a bunch of。



![](img/617262a339eed8504a813be6f1cd053e_4.png)

![](img/617262a339eed8504a813be6f1cd053e_5.png)

![](img/617262a339eed8504a813be6f1cd053e_6.png)

![](img/617262a339eed8504a813be6f1cd053e_7.png)

![](img/617262a339eed8504a813be6f1cd053e_8.png)

![](img/617262a339eed8504a813be6f1cd053e_9.png)

![](img/617262a339eed8504a813be6f1cd053e_10.png)

![](img/617262a339eed8504a813be6f1cd053e_11.png)

![](img/617262a339eed8504a813be6f1cd053e_12.png)

![](img/617262a339eed8504a813be6f1cd053e_13.png)

![](img/617262a339eed8504a813be6f1cd053e_14.png)

![](img/617262a339eed8504a813be6f1cd053e_15.png)

And then layers and in the end you're going to get another image so an image goes in and another image is going to come out of your convolutional neural networks So what's going to happen you're reducing the number of pixels in the end it's going to be 14 by 14。



![](img/617262a339eed8504a813be6f1cd053e_17.png)

![](img/617262a339eed8504a813be6f1cd053e_18.png)

![](img/617262a339eed8504a813be6f1cd053e_19.png)

And then you're going to have rather than three features you're gonna to have 512 features。

 so an image goes in another image is going to come out so that's another image so what is cool now the pixels in this new image they are going to be 512 dimensional so D here is 512 L you can take those pixels and then you can concatenate them you can turn them into a vector basically you flatten it and then I's going to give you 196 vectors and this is your L this is your set that you're going to end up it and image goes in and you're going to get a set of vectors but what is cool here the pixelel sitting at location2 and5 of these feature map it is one pixel at this layer but it's going to correspond to multiple pixels on the original image okay and that is going to be called a receptive。



![](img/617262a339eed8504a813be6f1cd053e_21.png)

![](img/617262a339eed8504a813be6f1cd053e_22.png)

![](img/617262a339eed8504a813be6f1cd053e_23.png)

![](img/617262a339eed8504a813be6f1cd053e_24.png)

![](img/617262a339eed8504a813be6f1cd053e_25.png)

![](img/617262a339eed8504a813be6f1cd053e_26.png)

![](img/617262a339eed8504a813be6f1cd053e_27.png)

![](img/617262a339eed8504a813be6f1cd053e_28.png)

![](img/617262a339eed8504a813be6f1cd053e_29.png)

![](img/617262a339eed8504a813be6f1cd053e_30.png)

![](img/617262a339eed8504a813be6f1cd053e_31.png)

![](img/617262a339eed8504a813be6f1cd053e_32.png)

each one of these is going to correspond to multiple multiple pixels。

 A big portion of your image is getting summarized into one pixel at this location so is everything here up until this point and image goes in another image is going come out perfect We all know about the soft attention what you saw now I'm going to explain the hard attention This was the first attention that was introduced What is the stochastic attention you want to know how much attention to pay to this pixel AI how much attention to pay to each one of these pixels at the feature map at the last layer of your convolution What you can do is you can multiply them by a bunch of numbers and previously these were deterministic you had an attention span of one and you will span it across these vectors now whatever were going to do now。

 this is gonna to be a random variable is gonna have the distribution。



![](img/617262a339eed8504a813be6f1cd053e_34.png)

![](img/617262a339eed8504a813be6f1cd053e_35.png)

![](img/617262a339eed8504a813be6f1cd053e_36.png)

![](img/617262a339eed8504a813be6f1cd053e_37.png)

![](img/617262a339eed8504a813be6f1cd053e_38.png)

![](img/617262a339eed8504a813be6f1cd053e_39.png)

![](img/617262a339eed8504a813be6f1cd053e_40.png)

![](img/617262a339eed8504a813be6f1cd053e_41.png)

![](img/617262a339eed8504a813be6f1cd053e_42.png)

![](img/617262a339eed8504a813be6f1cd053e_43.png)

![](img/617262a339eed8504a813be6f1cd053e_44.png)

![](img/617262a339eed8504a813be6f1cd053e_45.png)

Its own and then you're going model the distribution a better notation here would have been Z hat of T is equal to the summation of S AI。

 but let's stick to the notation of the paper What is ST it's a random variable and is this is going to be one if you are paying attention to location I so S is going to be1 if you're paying attention to location I and it's going to be zero otherwise so now you're going to see you are seeing why this is a hard attention you generate a random vector S most of the times it's zero and sometimes it is one and a single location it's going be one and Z hat is going be AI so this is hard attention okay let's model this distribution if STI is supposed to be one at a location you can model that probability by a bunch of alphas so this is going to be give you the probability of ST。



![](img/617262a339eed8504a813be6f1cd053e_47.png)

![](img/617262a339eed8504a813be6f1cd053e_48.png)

![](img/617262a339eed8504a813be6f1cd053e_49.png)

![](img/617262a339eed8504a813be6f1cd053e_50.png)

![](img/617262a339eed8504a813be6f1cd053e_51.png)

![](img/617262a339eed8504a813be6f1cd053e_52.png)

![](img/617262a339eed8504a813be6f1cd053e_53.png)

![](img/617262a339eed8504a813be6f1cd053e_54.png)

![](img/617262a339eed8504a813be6f1cd053e_55.png)

![](img/617262a339eed8504a813be6f1cd053e_56.png)

![](img/617262a339eed8504a813be6f1cd053e_57.png)

![](img/617262a339eed8504a813be6f1cd053e_58.png)

I beinging one at that location at location I and this is going to give you a vector per time you're going have a vector you're going have and this is the element of your vector if you put everything in one vector its going to give you alpha T and then we know that because it's a probability it has to add up to one so you're going to use your soft max on a vector and this vector you need to model and we are going to model that like we were modeling it before using it's going to give us the scores and we are going to use usual multilayer per so it's fully connected neural network with some non nonlinearity so a or think of a as your image and think of H as the hidden state of an underlying a LM because we are processing sentences okay so there is going to be an underlying asN the objective here is not to go into details of the LsM but rather this attention mechanism。



![](img/617262a339eed8504a813be6f1cd053e_60.png)

![](img/617262a339eed8504a813be6f1cd053e_61.png)

![](img/617262a339eed8504a813be6f1cd053e_62.png)

![](img/617262a339eed8504a813be6f1cd053e_63.png)

![](img/617262a339eed8504a813be6f1cd053e_64.png)

![](img/617262a339eed8504a813be6f1cd053e_65.png)

![](img/617262a339eed8504a813be6f1cd053e_66.png)

![](img/617262a339eed8504a813be6f1cd053e_67.png)

![](img/617262a339eed8504a813be6f1cd053e_68.png)

![](img/617262a339eed8504a813be6f1cd053e_69.png)

![](img/617262a339eed8504a813be6f1cd053e_70.png)

![](img/617262a339eed8504a813be6f1cd053e_71.png)

I a hard attention according to this distribution， you are going to sample1 S and that S is going to be one at a particular location at0 we are everywhere else and therefore you are paying a hard attention to that portion of your image Now the question is how we're gonna model in the end we are not interested in S we are interested in the probability or the log probability of the sentence of the caption given the image that's what we are interested in in the end it means that because S is a stochastic variable。

 it's a random variable we need to marginalize it out So we are going to have to integrate it out and that's exactly what we are going to do you have a log think of this as your integration and then you are integrating out S you're integrating over S you're integrating it out You have P of Y given S and a is your attention A is your image。



![](img/617262a339eed8504a813be6f1cd053e_73.png)

![](img/617262a339eed8504a813be6f1cd053e_74.png)

![](img/617262a339eed8504a813be6f1cd053e_75.png)

![](img/617262a339eed8504a813be6f1cd053e_76.png)

![](img/617262a339eed8504a813be6f1cd053e_77.png)

![](img/617262a339eed8504a813be6f1cd053e_78.png)

![](img/617262a339eed8504a813be6f1cd053e_79.png)

![](img/617262a339eed8504a813be6f1cd053e_80.png)

![](img/617262a339eed8504a813be6f1cd053e_81.png)

![](img/617262a339eed8504a813be6f1cd053e_82.png)

![](img/617262a339eed8504a813be6f1cd053e_83.png)

![](img/617262a339eed8504a813be6f1cd053e_84.png)

Why is your caption if I know the attention， if I know the image。

 I'm going to be able to produce the caption and then for each image。

 you're gonna to have the corresponding attention。 There is going to be a distribution and that distribution on the attention given the image Okay perfect so you're going to marginalize this out so you guys know that the log of a product is going to give you the summation of a bunch of logs that we know we have been using this forever but what you didn't know is that the log of the summation it is definitely not equal to the summation of logs so it that's not going to happen there is this genense inequ which says that the log of an integral is the integral of the log so it's bigger than or equal to the integral of the log and this summation in addition to this probability you can think of that expectation so you're taking an expectation with respect to S so log of the。



![](img/617262a339eed8504a813be6f1cd053e_86.png)

![](img/617262a339eed8504a813be6f1cd053e_87.png)

![](img/617262a339eed8504a813be6f1cd053e_88.png)

![](img/617262a339eed8504a813be6f1cd053e_89.png)

![](img/617262a339eed8504a813be6f1cd053e_90.png)

![](img/617262a339eed8504a813be6f1cd053e_91.png)

![](img/617262a339eed8504a813be6f1cd053e_92.png)

![](img/617262a339eed8504a813be6f1cd053e_93.png)

![](img/617262a339eed8504a813be6f1cd053e_94.png)

![](img/617262a339eed8504a813be6f1cd053e_95.png)

![](img/617262a339eed8504a813be6f1cd053e_96.png)

![](img/617262a339eed8504a813be6f1cd053e_97.png)

Expected log of the expectation is bigger than or equal to the expectation of the log because log is a concave function so that's what the genen inequality is going to tell us okay we're going to use that rather than maximizing this because we couldn't compute it this was a hard formula to compute we are going to compute L it is easier to compute and I'm going to tell you why it is easier to compute and then you're going to maximize L if you maximize L of S you're going to maximize your likelihood if you push this part up the other part should go up as well so we want to maximize this and whenever you want to maximize you're going to do gradient essence you need your gradients let's take the gradients of your lower bound we respect the parameters of our model so each one of these propertiesba are going to be parameterized using an LSDM and using these attention mechanism and using the parameters of our CNnM so there are going to be some parameters。



![](img/617262a339eed8504a813be6f1cd053e_99.png)

![](img/617262a339eed8504a813be6f1cd053e_100.png)

![](img/617262a339eed8504a813be6f1cd053e_101.png)

![](img/617262a339eed8504a813be6f1cd053e_102.png)

![](img/617262a339eed8504a813be6f1cd053e_103.png)

![](img/617262a339eed8504a813be6f1cd053e_104.png)

![](img/617262a339eed8504a813be6f1cd053e_105.png)

![](img/617262a339eed8504a813be6f1cd053e_106.png)

![](img/617262a339eed8504a813be6f1cd053e_107.png)

![](img/617262a339eed8504a813be6f1cd053e_108.png)

![](img/617262a339eed8504a813be6f1cd053e_109.png)

![](img/617262a339eed8504a813be6f1cd053e_110.png)

Okay， let's take derivatives the derivative of L with respect to W there is a summation here。

 it's gonna be the summation of this P and the gradient of this log with respect to W so that's the first term plus this other term times the gradient of P with respect to W and there is this nice trick that I want you guys to learn about We know that what you need is going be log of this and the gradient of p that's the term that youre looking for but here you don't have it you have this complicated looking P of p times log times the gradient of the log let's see what happens let's take the gradient of the log with respect to W what do you get you get the gradient of P with respect to W divided by P because the derivative of log is1 over P derivative of log of z is going be1 over Z so that's just the derivative of。



![](img/617262a339eed8504a813be6f1cd053e_112.png)

![](img/617262a339eed8504a813be6f1cd053e_113.png)

![](img/617262a339eed8504a813be6f1cd053e_114.png)

![](img/617262a339eed8504a813be6f1cd053e_115.png)

![](img/617262a339eed8504a813be6f1cd053e_116.png)

![](img/617262a339eed8504a813be6f1cd053e_117.png)

![](img/617262a339eed8504a813be6f1cd053e_118.png)

![](img/617262a339eed8504a813be6f1cd053e_119.png)

![](img/617262a339eed8504a813be6f1cd053e_120.png)

![](img/617262a339eed8504a813be6f1cd053e_121.png)

![](img/617262a339eed8504a813be6f1cd053e_122.png)

![](img/617262a339eed8504a813be6f1cd053e_123.png)

Okay you get the gradient of P with respect to W in the numerator in the denoerator you have P P here is going to cancel with this P here and then you get exactly what you needed。

 you have log of P times the gradient of P so why did we do that Why are we doing this？



![](img/617262a339eed8504a813be6f1cd053e_125.png)

![](img/617262a339eed8504a813be6f1cd053e_126.png)

![](img/617262a339eed8504a813be6f1cd053e_127.png)

![](img/617262a339eed8504a813be6f1cd053e_128.png)

Because now you can think of this term here as expectation it is the expectation of some term and now you can use Monte Carlo you can generate samples from S you can turn this integral or this expectation into a summation now you have some samples from this hard distribution if you remember this has a distribution so you're going to keep sampling from it and that's the term that you have so is everything clear so far so why am I going through this math because we are building our way towards reinforcement learning as well and this trick you' are going to see that over and over again the derivative of the log you can related to the derivative of the enumerator divided by derivative the divided by the argument and we're going to use that over and over again so is everything clear okay perfect so we are going do Monte Carlo estimation and then this is the gradient that we need this is an estimate of the gradient and what are these asns youre going to keep sampling。



![](img/617262a339eed8504a813be6f1cd053e_130.png)

![](img/617262a339eed8504a813be6f1cd053e_131.png)

![](img/617262a339eed8504a813be6f1cd053e_132.png)

![](img/617262a339eed8504a813be6f1cd053e_133.png)

![](img/617262a339eed8504a813be6f1cd053e_134.png)

![](img/617262a339eed8504a813be6f1cd053e_135.png)

![](img/617262a339eed8504a813be6f1cd053e_136.png)

![](img/617262a339eed8504a813be6f1cd053e_137.png)

![](img/617262a339eed8504a813be6f1cd053e_138.png)

![](img/617262a339eed8504a813be6f1cd053e_139.png)

![](img/617262a339eed8504a813be6f1cd053e_140.png)

![](img/617262a339eed8504a813be6f1cd053e_141.png)

From this multiomial distribution that you just created So you're gonna to sample from that So there is a question about this hard attention。

 we are introducing a random variable that is going be one or zero it's going to be one at location I and it's going to be zero everywhere else What happens if that this attention is going to be hard because you're paying attention only one to only one portion of your image to the portion that corresponds to AI and you have a distribution on S。

 it's a random variable， we can sample from it and exactly here you're sampling from it Does it answer your question and then I'm going to compare this to the previous attention that we know of to the selfat shortly So we are going to get there today but if you want to properly model attention。

 this is how you're going model it you're going you're going put a random variable here sometimes it is one most of the times it is zero and you're paying attention to one。



![](img/617262a339eed8504a813be6f1cd053e_143.png)

![](img/617262a339eed8504a813be6f1cd053e_144.png)

![](img/617262a339eed8504a813be6f1cd053e_145.png)

![](img/617262a339eed8504a813be6f1cd053e_146.png)

![](img/617262a339eed8504a813be6f1cd053e_147.png)

![](img/617262a339eed8504a813be6f1cd053e_148.png)

![](img/617262a339eed8504a813be6f1cd053e_149.png)

![](img/617262a339eed8504a813be6f1cd053e_150.png)

![](img/617262a339eed8504a813be6f1cd053e_151.png)

![](img/617262a339eed8504a813be6f1cd053e_152.png)

![](img/617262a339eed8504a813be6f1cd053e_153.png)

![](img/617262a339eed8504a813be6f1cd053e_154.png)

of your image while predicting the text so this is Monte Carlo， there is a problem with that。

 This is going to be an unbiased estimate， this righthand side is an unbiased estimate of your gradients so it's a good estimate it's unbiased It's expected value is equal to the actual number that you're interested in to the actual derivative but there is a catch it has a huge variance so it's going to oscillate a lot when you keep sampling from this multi newly distribution。

 it's going to sample a lot to reduce the variance。

 There is a trick that you can subtract a number from this log of p and then play around with the variance and try to reduce it so you can use this is a moving average of these log terms so it's a moving average of these logs so you're going subtract the average from this term and this is a moving average it is going to be your baseline and then youre measuring your deviation。



![](img/617262a339eed8504a813be6f1cd053e_156.png)

![](img/617262a339eed8504a813be6f1cd053e_157.png)

![](img/617262a339eed8504a813be6f1cd053e_158.png)

![](img/617262a339eed8504a813be6f1cd053e_159.png)

![](img/617262a339eed8504a813be6f1cd053e_160.png)

![](img/617262a339eed8504a813be6f1cd053e_161.png)

![](img/617262a339eed8504a813be6f1cd053e_162.png)

![](img/617262a339eed8504a813be6f1cd053e_163.png)

![](img/617262a339eed8504a813be6f1cd053e_164.png)

![](img/617262a339eed8504a813be6f1cd053e_165.png)

![](img/617262a339eed8504a813be6f1cd053e_166.png)

![](img/617262a339eed8504a813be6f1cd053e_167.png)

From the average and then don't worry about this entropy for a second， we have these terms here。

 There is a summation， the log part we didn't touch。

 we are gonna subtract the baseline from this log term here so we're gonna subtract the baseline from here as the expected value of those terms and then you can have an additional hyperparameter this could be one mathematically this should be one but you can put a parameter there and then play around with with its value you can use some validation data and set this so this is a hyperparameter and then the rest of it is the same as before so what you're doing is just subtracting the mean from these values so these are just oscillations around the mean that you're taking into account。

 It turns out that this estimator it is still unbiased and it has a lower variance and there is another catch for reinforcement learning so this is very close to reinforcement learning you want your agent to be able to。



![](img/617262a339eed8504a813be6f1cd053e_169.png)

![](img/617262a339eed8504a813be6f1cd053e_170.png)

![](img/617262a339eed8504a813be6f1cd053e_171.png)

![](img/617262a339eed8504a813be6f1cd053e_172.png)

![](img/617262a339eed8504a813be6f1cd053e_173.png)

![](img/617262a339eed8504a813be6f1cd053e_174.png)

![](img/617262a339eed8504a813be6f1cd053e_175.png)

![](img/617262a339eed8504a813be6f1cd053e_176.png)

![](img/617262a339eed8504a813be6f1cd053e_177.png)

![](img/617262a339eed8504a813be6f1cd053e_178.png)

![](img/617262a339eed8504a813be6f1cd053e_179.png)

Explore and at the same time exploit so it has to balance the trade off between exploiting and exploring the entropy if you add it it's going to help your method explore more so it's going to help it sample more diverse samples from the multinuly distribution so you're just increasing the entropy of your samples。

 this is exactly the algorithm that they call reinforce。



![](img/617262a339eed8504a813be6f1cd053e_181.png)

![](img/617262a339eed8504a813be6f1cd053e_182.png)

![](img/617262a339eed8504a813be6f1cd053e_183.png)

![](img/617262a339eed8504a813be6f1cd053e_184.png)

![](img/617262a339eed8504a813be6f1cd053e_185.png)

![](img/617262a339eed8504a813be6f1cd053e_186.png)

So it's a very simple algorithm it's from very long time ago and these is exactly what you're going to do these are exact details of that algorithm and one of the reasons I went through this paper is because of this so one step was to reduce the variance the other step is to help your method generate more diverse samples so explore more and this is going to give you the estimates of the gradients that you need now that you know the gradients you can do gradient S while updating the parameters w you're going to maximize L ofs and if you maximize L because your log likelihood should be bigger than L bigger than the lower bound your likelihood is going to go up as well so you're maximizing your likelihood and all of this trouble was because you needed to marginalize S out you couldn't compute the likelihood anymore because it is complicated there are some random variables going around in there。



![](img/617262a339eed8504a813be6f1cd053e_188.png)

![](img/617262a339eed8504a813be6f1cd053e_189.png)

![](img/617262a339eed8504a813be6f1cd053e_190.png)

![](img/617262a339eed8504a813be6f1cd053e_191.png)

![](img/617262a339eed8504a813be6f1cd053e_192.png)

![](img/617262a339eed8504a813be6f1cd053e_193.png)

![](img/617262a339eed8504a813be6f1cd053e_194.png)

![](img/617262a339eed8504a813be6f1cd053e_195.png)

![](img/617262a339eed8504a813be6f1cd053e_196.png)

![](img/617262a339eed8504a813be6f1cd053e_197.png)

![](img/617262a339eed8504a813be6f1cd053e_198.png)

![](img/617262a339eed8504a813be6f1cd053e_199.png)

How does it relate to deter deterministic soft attention Let's take the expected value of this random variable with respect to our distribution so the expected value of Z hat there is going to be a summation the expected value of the summation is the summation of the expected values expectation is a linear operation this is just a constant and it's going to be the expected value of S and the expected value of S the multi newly distribution is going to be these alpha the probabilities so that's the expected value so you are going to make an approximation here you're going to say forget about these being a random variable just set the hat of T to be alpha T AI and this guy you know this attention you know theyre going to add up to one you have a budget of one there is a softm here and then you're spreading that budget of one among your input so this is an approximation of what you do with hard attention don't worry about this beta term this is reducing the attention a little bit。



![](img/617262a339eed8504a813be6f1cd053e_201.png)

![](img/617262a339eed8504a813be6f1cd053e_202.png)

![](img/617262a339eed8504a813be6f1cd053e_203.png)

![](img/617262a339eed8504a813be6f1cd053e_204.png)

![](img/617262a339eed8504a813be6f1cd053e_205.png)

![](img/617262a339eed8504a813be6f1cd053e_206.png)

![](img/617262a339eed8504a813be6f1cd053e_207.png)

![](img/617262a339eed8504a813be6f1cd053e_208.png)

![](img/617262a339eed8504a813be6f1cd053e_209.png)

![](img/617262a339eed8504a813be6f1cd053e_210.png)

![](img/617262a339eed8504a813be6f1cd053e_211.png)

Because these are images and without is and method would converge， there is another trick。



![](img/617262a339eed8504a813be6f1cd053e_213.png)

That we know that if you do a summation over I， these are gonna be these are gonna add up to one。

 This is the budget that you had。 So this is bounded in terms of I。

 but then there is no bound if you do a summation over the sequence then if you do your summation over T there is no bound you can make that bounded by setting a hyperparameter here tau it's some number that you choose and then you penalize that in your last function。

 you say that with some penalty， I want this summation to be around tau So now you are penalizing that and this was needed because without this the method without un converge and the reason for that was because these are unbounded they could get unbounded the decoder So far we were talking about the encodeder。

 the decoder is when you are predicting the caption it's actually when you' are generating your caption the decoder is an LM input gate for get gate output gate cell memory cell。



![](img/617262a339eed8504a813be6f1cd053e_215.png)

![](img/617262a339eed8504a813be6f1cd053e_216.png)

![](img/617262a339eed8504a813be6f1cd053e_217.png)

![](img/617262a339eed8504a813be6f1cd053e_218.png)

![](img/617262a339eed8504a813be6f1cd053e_219.png)

![](img/617262a339eed8504a813be6f1cd053e_220.png)

![](img/617262a339eed8504a813be6f1cd053e_221.png)

![](img/617262a339eed8504a813be6f1cd053e_222.png)

![](img/617262a339eed8504a813be6f1cd053e_223.png)

![](img/617262a339eed8504a813be6f1cd053e_224.png)

![](img/617262a339eed8504a813be6f1cd053e_225.png)

tThen hidden state and then you're paying attention so Z hat T is exactly what you have it could come from the soft attention or it could come from the hard attention and we know that whenever you are predicting words you're going have a softm so you're dividing by some normalizing term here to turn these numbers into probabilities but this is going to be related to this exponential term and there's also some attention there going on is your're embedding matrix and then how do you initialize your decoder how do you initialize C0 and H0 you're going to initialize I'm using two neural networks and the average image that you're seeing so you're averaging across all of these for 14 by 14 numbers across 196 numbers vectors actually I know this was tough but let's look at some figures the soft attention while predicting。

A bird is going pay attention in a soft manner to the bird and the hard attention is gonna pay attention in a hard manner so it's gonna pay attention to one portion of your image and this is the soft attention if your sentence caption the output cap is a stop sign is on a road with a mountain in the background and if you focus on stop you're gonna to notice that your message is focusing on the stop sign and if you want your method to focus on the trees or if you want to check it whether it's focusing on the correct thing you can see that it's focusing on the correct thing so it's focusing on the trees okay any questions why would you want to use hard attention because it seems like if it expectation is just soft attention then instead of sampling I should just compute this expectation exactly in your soft attention instead so you're losing a lot of your statistics so the proper way of doing it is this hard attention but it turns out that they are going to give you the same performance why。

Go through this because I wanted you to see that the proper way of doing it is using hard attention the soft attention is an approximation to the hard attention it is nicer it looks nicer mathematically it's easier and the other reason I went through this is because I wanted you to see reinforce and I want you to see this trick with the derivative of the log of the probability so for multiple reasons I went through this paper and this is an amazing paper so does that answer your question yes thanks。

I guess I'm going to stop here for those of you want to leave it can leave and the ones who want to stay and ask questions i'll be around I had a question about the the energy for the Markov Brand field in the previous paper okay so do you see my screen yeah。

I guess intuitively I'm just thinking about here it says we're minimizing this energy and in this case it seems more intuitive to me that we want to maximize something which is you know our alignment scores are high and we have consecutive words assigned to the same image region so it feels more intuitive that there should be a maximization is there like a minus sign scene where like I guess where's my intuition wrong here I guess you're right so there should be a minus here so yes you want to maximize the assignment within these two Okay that's my only question So if there's so instead of just be min a and then there's a minus of this E yes。

 and you're right you want to find a maximumim assignment between these two go all right。

 thank you that was my question。we get YouTube let's get this started so last session we stopped here we show At until we learned about hard attention and its relationship to reinforcement learning and one particular algorithm reinforce which is an old algorithm but it's still very useful and then we learned that for instance in this case our policy could be choosing where to attend so that's our policy or how much attention actually where to attend is the correct way of doing it where in the input should we attend to that's our policy our reward is going to be this P of Y given SNA and the states are going to be where we attended so far the image that goes in or the features of the image these are the states and that's one way to think about this framework as well。

Hard attention is related to reinforcement learning so we are going to go through reinforcement learning later on。

 so don't worry about it it was just this trick that is really important to me that the derivative of the log it is related to one over the object that you're taking its derivative and the derivative of that object in the numer。


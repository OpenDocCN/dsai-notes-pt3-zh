# P163：L73.3- 期望转录损失 - ShowMeAI - BV1Dg411F71G

This paper is going be a little bit tough the next one。

 so I want you to be patient because I want to tell you about the beam search and another type of loss and we are going to go back to speech recognition we want to tran transcribe audio data be text that your input sequence in the form of a spectralgram a bidirectional SDM is going to give you an output sequence we are going to need to use connection connection is temporal classification loss because of the following observation so this observation is made it's a paradox made for handwriting recognition systems but handwriting recognition systems are very similar to speech the input is misaligned with the output and what is the observation what is the paradox it says that a cursively written word cannot be recognized without being segmented and it cannot be segmented without。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_1.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_2.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_3.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_4.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_5.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_6.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_7.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_8.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_9.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_10.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_11.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_12.png)

Being recognized so you first need to recognize it to be able to segment it and then to be able to segment it you need to be able to recognize it so there's a paradox going on there and for that reason you're going to use connection is temporal classification We know that your neuraln network whatever that you do these topics we covered this is just a quick recap one solution is that you' are not only you are going to emit the labels you are gonna to emit some blanks and then you are gonna get rid of those blanks and repetitions later on so in the end you are not going to get what you are going to need to train the model but you are gonna get a bunch of labels or label indices and a bunch of blanks out of your neuraln network and that's going to be your path So this is gonna be your path previously were calling it pi here we are calling it a but this is your path it's a path that neuron network to Q then we said that we are going。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_14.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_15.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_16.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_17.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_18.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_19.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_20.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_21.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_22.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_23.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_24.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_25.png)

Define an operator that it first remove the repeated labels and then it's gonna to remove the blanks。

 Let's see an example。 you first remove the repeated letters， there is no repetition here going on。

 So the next step is removing these blanks and that's going to give you ABc and this is what you are gonna to need in the end you don't care about those blanks。

 This is what you're gonna to need in the end。 and the same another path could give you the same label。

 there were no repetitions here， you are just removing the blanks， there could be repetitions。

 for instance， here you have a BBB， because for the same input signal。

 youre outputting the same letter。 your model is outputting the same letter because that your input signal is longer than your target So you're going keep repeating yourself。

 The model is going to keep repeating itself。 if youre remove the repetitions that's going to give you ABc。

 And if you remove these repetition and then remove the blanks that's going to give you ABc again。

 So there are multiple。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_27.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_28.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_29.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_30.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_31.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_32.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_33.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_34.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_35.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_36.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_37.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_38.png)

Fri path that correspond to the same label That's why you're gonna for that particular label。

 you are interested in the probability of that label given the speech you're going to consider all of the possible path that are going to take you to that particular label so B of a is in B inverse of Z So B of a is going be equal to z so you're looking at all of the A's all of the path that give you the same label to write down your likelihood and then you're going to have your target sentence that you can use to optimize the parameters of your neural network and that's going to give you a loss function you know the ground truth you know your input you know an efficient way of computing these probability using dynamic programming we went through it last session and then that's going to give you your CDC object and if you remember for the Google neural translation system we said that if you're max。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_40.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_41.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_42.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_43.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_44.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_45.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_46.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_47.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_48.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_49.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_50.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_51.png)

Your likelihood， it's not directly related to the blue score that you're going to use to evaluate your model later on。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_53.png)

And over there， we said that maybe making our objective function look more similar to the evaluation metric is going to help。

 and then we did that and that help the model。 So here we're going to do it a similar thing another observation is that if you use this loss function。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_55.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_56.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_57.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_58.png)

You're only going to learn from your mistakes and your good behavior。

 but then you're not going to learn from the discrepancy between your mistakes you might be giving it the model might be giving the correct answer approximately so not all of the wrongs are equally wrong some of the mistakes are not that bad and maybe you can learn from those as well that's why you're going to change your loss function slightly is what are youre going to do you have your word error rate or label error rate this is a non-differiable function you know the underlying label your model is going to take as input X and is going to give you another label and then you need to say how many insertions deletions and substitutions do I need to make to change the prediction of the model to be the correct one。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_60.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_61.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_62.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_63.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_64.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_65.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_66.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_67.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_68.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_69.png)

That your word error rate and as you can see this is not a differentiable function so you cannot pass your derivatives through this and you don't need to what you're doing is computing the expected value of all of these mistakes or error rate Now if you're making if your model is making tiny mistakes but it's not that bad you're still going to learn from them and this is just the expected value of that that's going to give you a loss function and this is called expected transcription loss Now the problem is taking the derivative of these loss and first evaluate take its derivative and then using those derivatives optimize the parameters of your neural language let's try to do that the first step is getting rid of these probability of Z given x using this formula up here probability of Z given x is all of the path that are going to give you the same label we're going to use that so theres going to be a summation here of A B inverse of C。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_71.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_72.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_73.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_74.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_75.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_76.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_77.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_78.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_79.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_80.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_81.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_82.png)

AI in B inverse of Z B of a is going to be equal to Z and this way you're going to get rid of the summation over Z and you're only going to do a summation over your A's。

 now you can actually compute your Z on the fly Z is B of A Okay so this is just using the definition of B so you can come give an A。

 you can compute Z that's why you can get rid of that summation。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_84.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_85.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_86.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_87.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_88.png)

Now this is your loss function and one might say okay go ahead and do an empirical evaluation of that loss function let's do it What you're going do is you're going to sample from your probability so you're sampling from your recurrent neural run network pushing it through your this is going to give you a path you're going to push it through your operator that's going to remove the blanks and labels and that's going to give you your empirical loss now you want to take derivative of that guy this is a step you're gonna to need as an intermediate step in the end what you want to do is take the derivative of this loss we respect to the parameters of your neural network but this is an intermediate step what do we have here the probability of a given x we know that it's the product of the probabilities of Y given x once you take a lot that's going give you the summation of those probabilities now you're taking the derivative of the summation。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_90.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_91.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_92.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_93.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_94.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_95.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_96.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_97.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_98.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_99.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_100.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_101.png)

A bunch of probabilities with respect to the probabilities whenever A for that particular time step is equal to k that's going to be a 1 otherwise that's going to be a zero the derivative is going to be zero and because of the log term here you're going to have one over PR okay that's just a derivative of the probability with respect to another probability perfect and if you remember we use this trick。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_103.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_104.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_105.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_106.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_107.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_108.png)

That the derivative of a function is equal to the function itself times the derivative of the log of the function。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_110.png)

Where did we use this we use this when we were doing hard attention we are going to use this trick again。

 you want the derivative of your loss with respect to these probabilities and we are going to use these formula down here there is the summation over a and you are taking the derivative of this loss with respect to those probabilities and that's just because of the summation andre taking derivatives being linear we can switch the role this is going to be the summation of the derivatives of these L these penalties and this is where we are going to use this trick now our F is going to be these probabilities so your F is going to be probability of a given x and your f here in this formula is going to be probability of k comma t given x and we are going to use that and this is where the log term is going to come in here you have a function it's going to give you the same function and then you're going to take the log the derivative of the log。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_112.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_113.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_114.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_115.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_116.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_117.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_118.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_119.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_120.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_121.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_122.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_123.png)

So we just expanded that term using this formula and here is where you're going to need that observation。

 the derivative of the log of the probability， given the probability of k and T this is where you're going to need it if A is equal to K that's going to be a one otherwise it's going to be a zero that's why your summation is going to collapse into all of the As that are equal to K and you're also conditioning on A being equal to K because that's the only place that you have a non-zero value and that one over the probability is canceling out with this other probability and that's what you're going get in the end okay that actually that probability is the one that is giving you the conditioning okay so far so good we were taking derivatives of this guy but now we are on a computer and we need to do Monte Carlo estimates whether we're going do were going to use this formula here and then because everything is now in terms of expectation there is an。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_125.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_126.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_127.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_128.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_129.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_130.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_131.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_132.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_133.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_134.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_135.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_136.png)

Going on there you can keep sampling from this probability and do just add those values but what are you sampling from first you are going to sample from the distribution of a's your path condition on X this is where your neural network is going to help you but then you are not interested in all of the A's if at a particular time this t is equal to that other T that should be k because of this conditioning for any other time you can just use the sample from above from your neural network so you're just modifying one entry at a particular time step of your samples you sample from that guy and you modify one of them and these are going to give you the samples that go inside your loss this is not your loss this is your word error rate and that's the way that you're going to get the derivatives the rest of it is chain and back propagation so these I'm going to leave as an exercise in。



![](img/52d4d5888bf7b17853ab1bd50fc8e34e_138.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_139.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_140.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_141.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_142.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_143.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_144.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_145.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_146.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_147.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_148.png)

You want to compute the derivative of your loss with respect to the parameters of the model but an intermediate step is that you're going to need the derivative of your loss with respect to the predictions of the model is YTK and then the rest of it is the derivative of YTK with respect to the parameters what you're going to do here you're going to use this summation use the chain rule and take the derivative of the softmax and taking derivative of the softmax is not that hard and that's the way that you're going to get this formula and if you look at it is Z is all of the terms that are appearing in the denominator and the other term is the ones that are appearing in the numerator of your softmax I think now you' are in good shape we know how to take derivatives of our loss and we can do training next step is decoding the predictions of the model think it's a good time to stop and for those of you who have questions I be around。

I'm confused by this notation I'm taking the derivative with respect to the probability of K C given x which part can you point me Yeah where are you point all of these pieces where taking the derivative with respect to the probability Yes。

 so these are parts of your chain rule and let's track the chain rule and see what happens in the end you want the derivative of your loss with respect to the parameters of your neuraln network and now you're gonna break this you want to go backward the first step is taking the derivative with respect to the predictions these probabilities and these you have the model here so you are not taking derivative with respect to YtK or YtK prime yet you are taking derivative with respect to this output okay and that's what it means so you could have labeled this maybe you would have been more comfortable if these notation。

P TK like something that you have here Y TK but it's just a variable it's an intermediate variable in between and then this probability of a given x we know that these are independent so you are making an independent assumption a is a sequence and each time for that sequence you are making an independence assumption so that's going give you a product of these guys so does that part also make sense because this guy you need it this is an intermediate step you needed it here and the rest of it is what is just then the next step is taking the derivative of PK with respect to Y TK and this is where the softm is going to come in and these you can actually compute them is not that hard this is boring the exciting part is using this formula and we are going to use that again in reinforcement learning we saw it for。

Attention， we cite for this loss。 And I guess we cite also in Google's neural machine translation system as well。

 So this trick is very useful。 Does that answer your question。 yeah， Thank you sure。


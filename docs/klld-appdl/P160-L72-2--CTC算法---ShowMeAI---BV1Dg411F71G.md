# P160：L72.2- CTC算法 - ShowMeAI - BV1Dg411F71G

This is gonna be a technical paper， but I want you to stick with me。 Okay， just don't give up。

 This is gonna be a little bit tough explaining this paper， but I think we can do it。

 Let's go through it。 What is speech recognition。 What do you want to do。

 Somebody gives you an audio signal。 And then you want to transcribe it in terms of words。

 sub wordss， letters， phonemes， etc。

![](img/f82f906f1a4affba647cce4cb17d818a_1.png)

![](img/f82f906f1a4affba647cce4cb17d818a_2.png)

![](img/f82f906f1a4affba647cce4cb17d818a_3.png)

![](img/f82f906f1a4affba647cce4cb17d818a_4.png)

![](img/f82f906f1a4affba647cce4cb17d818a_5.png)

![](img/f82f906f1a4affba647cce4cb17d818a_6.png)

So that is a speech recognition and audio signal like the one that we just saw goes in actually log me Spectrogram is going to go in and you want to turn it into words or subwords what do we have you have a noisy real valued input stream this is your raw audio this is your input data and they're going to be some annotations for it somebody wrote it in terms of letters or actually it's usually the other way around the data are constructed by somebody reading a text or multiple people reading the text but in any ways you have your data it's not only about the connection is temporal classification CTC it's gonna to give you your last function it is not only for speech you can use it for handwriting recognition you can use it for a speech you can use it for gesture recognition so what is temporal classification what is the definition what is temporal classification where is the name coming from it is the。



![](img/f82f906f1a4affba647cce4cb17d818a_8.png)

![](img/f82f906f1a4affba647cce4cb17d818a_9.png)

![](img/f82f906f1a4affba647cce4cb17d818a_10.png)

![](img/f82f906f1a4affba647cce4cb17d818a_11.png)

![](img/f82f906f1a4affba647cce4cb17d818a_12.png)

![](img/f82f906f1a4affba647cce4cb17d818a_13.png)

![](img/f82f906f1a4affba647cce4cb17d818a_14.png)

![](img/f82f906f1a4affba647cce4cb17d818a_15.png)

![](img/f82f906f1a4affba647cce4cb17d818a_16.png)

![](img/f82f906f1a4affba647cce4cb17d818a_17.png)

![](img/f82f906f1a4affba647cce4cb17d818a_18.png)

![](img/f82f906f1a4affba647cce4cb17d818a_19.png)

labeling unsegmented data sequences so the data that you have for speech they are not like text that are segmented it's not like there is words afterwards afterwards it's just a continuous signal so you have an unsegmented data sequence and your task is labeling that and that is called temporal classification so you're classificationifying across time and there is the connectionist word coming from so there was a time that deep learning was being called connectionist and it is coming from the fact that you're using RNNs or neural networks in general so connection is is because of neural networks and temporal classification is just the task and then you also have framewise classification which is you're going to classify each frame independently and framewise classification is a step towards connectionist temporal classification and you're gonna to see why so let's go ahead。



![](img/f82f906f1a4affba647cce4cb17d818a_21.png)

![](img/f82f906f1a4affba647cce4cb17d818a_22.png)

![](img/f82f906f1a4affba647cce4cb17d818a_23.png)

![](img/f82f906f1a4affba647cce4cb17d818a_24.png)

![](img/f82f906f1a4affba647cce4cb17d818a_25.png)

![](img/f82f906f1a4affba647cce4cb17d818a_26.png)

![](img/f82f906f1a4affba647cce4cb17d818a_27.png)

![](img/f82f906f1a4affba647cce4cb17d818a_28.png)

![](img/f82f906f1a4affba647cce4cb17d818a_29.png)

![](img/f82f906f1a4affba647cce4cb17d818a_30.png)

![](img/f82f906f1a4affba647cce4cb17d818a_31.png)

De with temporal classification you have a data set S this is your training data and you have pairs of input speech and output text So x is a sequence or is your input space it's the space of all sequences that are M dimensional and we are putting a star here because we don't know the length of our speech a priori okay so this could change so you have a sequence of m dimensionional realvalued vectors this is your data this is just what we saw with me spectrograms。

 a sequence of vectors the output is also a sequence of vectors。

 it's actually a sequence of labels sorry because your text it could be 1，2。

34 it's a bunch of integers the words in your text So you're gonna have a vocabulary of size L and that's going to give you a sequence of labels L any element of that。



![](img/f82f906f1a4affba647cce4cb17d818a_33.png)

![](img/f82f906f1a4affba647cce4cb17d818a_34.png)

![](img/f82f906f1a4affba647cce4cb17d818a_35.png)

![](img/f82f906f1a4affba647cce4cb17d818a_36.png)

![](img/f82f906f1a4affba647cce4cb17d818a_37.png)

![](img/f82f906f1a4affba647cce4cb17d818a_38.png)

![](img/f82f906f1a4affba647cce4cb17d818a_39.png)

![](img/f82f906f1a4affba647cce4cb17d818a_40.png)

![](img/f82f906f1a4affba647cce4cb17d818a_41.png)

![](img/f82f906f1a4affba647cce4cb17d818a_42.png)

![](img/f82f906f1a4affba647cce4cb17d818a_43.png)

![](img/f82f906f1a4affba647cce4cb17d818a_44.png)

A let star is a sequence is your labeling and you're gonna to have pairs of X and z in your data X is a speech Z is a label this is your input sequence this is your target sequence and I'm sure you notice something we talk a lot so we our speech is going to have a lot of observations in it the sequence length is going to be really long t is going to be long but we usually write a few number of words or characters so the sequence length for your input is usually much larger than your outputs and that's a problem that you want to solve with connection is temporal classification but let's say you have a system let's say you know how to train your neural network the question is let's say you know your loss function you know your model now the question is how we're going to measure the performance of a model so let's start with that you have。



![](img/f82f906f1a4affba647cce4cb17d818a_46.png)

![](img/f82f906f1a4affba647cce4cb17d818a_47.png)

![](img/f82f906f1a4affba647cce4cb17d818a_48.png)

![](img/f82f906f1a4affba647cce4cb17d818a_49.png)

![](img/f82f906f1a4affba647cce4cb17d818a_50.png)

![](img/f82f906f1a4affba647cce4cb17d818a_51.png)

![](img/f82f906f1a4affba647cce4cb17d818a_52.png)

![](img/f82f906f1a4affba647cce4cb17d818a_53.png)

![](img/f82f906f1a4affba647cce4cb17d818a_54.png)

![](img/f82f906f1a4affba647cce4cb17d818a_55.png)

![](img/f82f906f1a4affba647cce4cb17d818a_56.png)

![](img/f82f906f1a4affba647cce4cb17d818a_57.png)

Pral classifier it's going to take us input a sequence。

 it's going to output another sequence and let's say this is already trained or it's to be trained using your data and you want to evaluate it and a bunch of test data these are different from your training data What are you going to do What is the metric that we're going to use the metric is coming from edit distance what is that your model is going to predict H of x given a speech it's going to give you a bunch of words or subwords or characters or phomes and the underlying one you know you know the ground truth because this is your test data ED is the edit distance and it is the minimum number of insertions substitutions and deletions required to change the prediction of the model to the correct one So how many insertions substitutions deletions do you need to do to convert H of x to Z。



![](img/f82f906f1a4affba647cce4cb17d818a_59.png)

![](img/f82f906f1a4affba647cce4cb17d818a_60.png)

![](img/f82f906f1a4affba647cce4cb17d818a_61.png)

![](img/f82f906f1a4affba647cce4cb17d818a_62.png)

![](img/f82f906f1a4affba647cce4cb17d818a_63.png)

![](img/f82f906f1a4affba647cce4cb17d818a_64.png)

![](img/f82f906f1a4affba647cce4cb17d818a_65.png)

![](img/f82f906f1a4affba647cce4cb17d818a_66.png)

![](img/f82f906f1a4affba647cce4cb17d818a_67.png)

![](img/f82f906f1a4affba647cce4cb17d818a_68.png)

![](img/f82f906f1a4affba647cce4cb17d818a_69.png)

![](img/f82f906f1a4affba647cce4cb17d818a_70.png)

To make it correct but then you need to make that normalized by the sequence lens so you're going to divide it by z so that this is relative to the size of your target and then you're going to do an average over your data so this is the L label error rate which could be word error rate or it could be character error rate or it could be P formme error rate etc so we're going to see this error rate a lot now let's go back to this problem how are we going align x and z because they have different sizes one is t1 is U and this is where connection is temporal classification is going to help us usually your neuraln network is going to take as input as sequence and it's going to out with another sequence and we saw that for text a sequence of Mdisional vectors is going to go in a sequence of n dimensionsional vectors is going to come out。



![](img/f82f906f1a4affba647cce4cb17d818a_72.png)

![](img/f82f906f1a4affba647cce4cb17d818a_73.png)

![](img/f82f906f1a4affba647cce4cb17d818a_74.png)

![](img/f82f906f1a4affba647cce4cb17d818a_75.png)

![](img/f82f906f1a4affba647cce4cb17d818a_76.png)

![](img/f82f906f1a4affba647cce4cb17d818a_77.png)

![](img/f82f906f1a4affba647cce4cb17d818a_78.png)

![](img/f82f906f1a4affba647cce4cb17d818a_79.png)

![](img/f82f906f1a4affba647cce4cb17d818a_80.png)

![](img/f82f906f1a4affba647cce4cb17d818a_81.png)

![](img/f82f906f1a4affba647cce4cb17d818a_82.png)

![](img/f82f906f1a4affba647cce4cb17d818a_83.png)

They're gonna have the same size capital T， the same length。

 So x is a sequence Y is the output sequence giving you the probabilities。

 Basically this y Tk is gonna to give you the probability of observing label K which could be the probability of of observing word K or letter K at time T so y I want to think of I want you to think of them as probabilities so these are your probabilities coming out of your recurren run network so your re run network is giving you your probabilities perfect but you have too many of them you have capital T of them and we need to somehow get rid of them the trick is that in addition to all of your labels to your vocabulary you're going to add a blank so for some of your vectors in the input you're just outputwiing nothing because when I'm speaking I might have。



![](img/f82f906f1a4affba647cce4cb17d818a_85.png)

![](img/f82f906f1a4affba647cce4cb17d818a_86.png)

![](img/f82f906f1a4affba647cce4cb17d818a_87.png)

![](img/f82f906f1a4affba647cce4cb17d818a_88.png)

![](img/f82f906f1a4affba647cce4cb17d818a_89.png)

![](img/f82f906f1a4affba647cce4cb17d818a_90.png)

![](img/f82f906f1a4affba647cce4cb17d818a_91.png)

![](img/f82f906f1a4affba647cce4cb17d818a_92.png)

![](img/f82f906f1a4affba647cce4cb17d818a_93.png)

![](img/f82f906f1a4affba647cce4cb17d818a_94.png)

![](img/f82f906f1a4affba647cce4cb17d818a_95.png)

ies， long pauseies and then short pauseies talking faster， slower， repeating myself。

 etc and you might need to output nothing。 there is just nothing there there is no label and this is going to be a sequence that is that has a length of T of your alphabet I don't know ABCD or if you have words or sub wordss these are going to be your sub wordss and some blank and each member of that set which are which we are coming which we are calling lambmbda is your path and then you can just read off your probabilities from your recurrent neural run network X goes in and given that you know pi pi is any of these guys you can just read off the probability of that pi happening it's just so you're making some assumptions here the connection is temporal classification is making some independent assumption that given x your y's are going to be independent at least for writing your loss。



![](img/f82f906f1a4affba647cce4cb17d818a_97.png)

![](img/f82f906f1a4affba647cce4cb17d818a_98.png)

![](img/f82f906f1a4affba647cce4cb17d818a_99.png)

![](img/f82f906f1a4affba647cce4cb17d818a_100.png)

![](img/f82f906f1a4affba647cce4cb17d818a_101.png)

![](img/f82f906f1a4affba647cce4cb17d818a_102.png)

![](img/f82f906f1a4affba647cce4cb17d818a_103.png)

![](img/f82f906f1a4affba647cce4cb17d818a_104.png)

![](img/f82f906f1a4affba647cce4cb17d818a_105.png)

![](img/f82f906f1a4affba647cce4cb17d818a_106.png)

![](img/f82f906f1a4affba647cce4cb17d818a_107.png)

So far so good and what you're just doing is just defining a distribution over this lambda t but what is the problem you don't have labeled data for pi your label data are for Z so you need to somehow convert your labels to the space of pi and then you're gonna be able to use your recurrent run network so we are doing a lot of work for writing or loss function for each pi you need to get rid of the repetitions and you need to get rid of the pauses when you're talking so you're going to define many to one map for instance if I talk I'm going to be talking differently from one of you guys we are going to pause in different locations so there is gonna be many to one mapping in the end you're interested in AAB and this could be your sub words this could be your words this could be your letters this could be your phos we are interested in this this is one of you guys talking what you're going to do is remove the。



![](img/f82f906f1a4affba647cce4cb17d818a_109.png)

Because they are repeated and make them one this is gonna be AB。

 then this is repeated also you're gonna make this a and then you're going to get rid of these pauses and that's going to give you aA for me speaking it's going be a pause A B pause this is what the model predicted now we need to map it into the actual text and we are just going to get rid of the blankks what did we just do we reduce the length of our sequence we went from capital D to something that is less than t so far so good now I'm starting to see that okay if this is my label there could be multiple outputs from the network that correspond to the same label perfect this is my label and this is exactly what you want to optimize x goes in you know the corresponding label and you want to maximize the likelihood of that perfect and I said for each L there might be。

Multiple pis so you're just going to add up those probabilities for each label there could be multiple pis you just add up those probabilities and then you're gonna optimize this and that's going to give you a last function perfect now you know your last function You know that you're going to use and run network you know how to evaluate it using label error rate but how you're going to decode you're going use this objective here actually you're going to use this objective here X goes in your model is going give you pi or the probability of pi and then you're going to do the maximum probability pi star is going to maximize that probability So it's the art max of that probability but then you need to convert it into speech into text and you're going to use this many to one mapping and this is called best path decoding this is not the best way of decoding but this is actually not that bad perfect so far everything was mathematical how on earth are you're going to implement this。

On your computer there is a label and you need to span all of those possibilities。

 you need to sum over all of the pies that could happen and this is a very complex problem to solve okay if you don't use dynamic programming so I'm going to go through the dynamic programming or I don't expect you to understand everything I'm going to give you an example。

 and I'm going to leave it as an exercise for you to figure out the details of the example let's see how we are gonna to break apart these probability and compute it for dynamic programming you need to express some variable in terms of the previous time steps So you' are breaking your problem apart into tiny steps from one step to the next one you don't solve the entire thing at once you just solve it one step at a time for that you're going to need to define a good variable let's say you're sitting at time T and you want to know the total probability of this label。

So far so you' are cutting your label， you are not looking at the entire capital T。

 you are looking at an intermediate time small T and then you're looking at intermediate label from one up until S and you're going to write down the total probability for that This is the product of the model outputs from time1 up until the current time and then this formula here is exactly what you have up there we are interested in all of the pis such that from pi from one up until the current time if you do them many to one mapping it's going to give you your label so there could be multiple pi is corresponding to this label this partial label now you have two variables that you can work with you have s and you can T and for dynamic programming you are going to write alpha Ts in terms of alpha t minus1 evaluated at S S minus1 and S minus。

And this is how you are breaking apart your problem I'm going to go through the details a little bit more but then i'm going to come back how do you start this the first guy is going be the probability of a blank and the second guy is going be the probability of the first letter and anything that has S bigger than two is going to be zero because we know that the labels are usually smaller or of a smaller size than t so at this point in time t is1 so if s is bigger than two you just set them to be zero。

And then in the end， the probability that you needed up there we can express it in terms of alphas at the final time and you might wonder what is L prime here。

 L prime is the same as L but you're adding blanks between each subward or each funny for instance here is an example CA is your label。

 it's your L you're inserting blanks， it's going to give you L prime so this is L prime and then you're going to keep computing alphas。

 this is going to give you alpha 1 this is alpha 11 alpha 12。

 then you're going compute alpha21 alpha 2 two alpha 2。

3 alpha24 and then using this recurion relationship you're going to compute your probability and in the end you're going to have the entire probability which is the addition of these two numbers。

So what I want you guys to do is to use this formula here and apply it on this example and see what happens and when you are doing that keep track of these these are going to be your probabilities and then you're going to be able to demystify this algorithm this is already implemented intensorflow it's just going to be one line it's already implemented in por so you usually say I want to use CTC loss and it's just going to do this for you on the fly but it's a good idea to know what is behind the scenes and how you're computing your probability of L given X the probability of your label given your speech is everything clear any questions so this was a complex topic and if you understand it that's great I mean we are not afraid of going through tough topics okay and the problem is your neural network is going to take as input a sequence that has length T。

And it's going to output another sequence of the same length and with the speech you don't know what is the correct alignment between your input speech and your target label。

 you don't know that alignment so the first idea is that if you don't know the alignment just keep outputting blanks or keep repeating the same letter so your your neuraln network is going to do that it's going to keep outputting blanks and it's going to keep outputting repeated letters but then you need to get rid of that repetition and those blanks how do you get rid of them you're going to use them many to one mapping。

 which is a very simple mapping， it's going to remove all the blanks and it's going remove repeated labels so it's actually first gonna remove repeated labels and then all the blanks but then your neuraln network is outputting too many stuff you just need to add those probabilities mathematically this is beautiful but computation。

speakingking this is a hard problem Comp this loss because there are many pis that could correspond to the same label and there is no way for you to expand the entire space and whenever you have those sorts of problems a good answer is dynamic programming so you're going to break your problem apart into smaller pieces you're going to introduce two variables T ands and then you're going to do a recursion on T andS S is going to be the length of your labels and T is going to be your current the length of your current speech I guess I'm going stop here and for those of you have questions I'll be around it seems like the the inverse map from any wayable is an infinitely large set and so what part of this is the dynamic programming that accounts for like truncating that infinite set pi yes so that's a good question first of all we are introducing two new variables S and。

And we are going to do recursion and them and your recursion is going be t minus1 S S minus1 and S minus2 so far so good but then things could get messed up What are those if you have blanks like this blank here and the other blank here this blank that blank the other blank so one part of your recursion is taking care of those blanks So if that's a blank do something else and the other part is taking care of the repeated words remember your for instance here you have repeated letters you could have B and then you're inserting artificial blanks as well you're gonna have B blank B and this is gonna take care of that repeated stuff if S minus2 is equal to S do something else Otherwise use the three recursions before and then this addition that you're obtaining here is because of the addition that you have here。

Okay， you're adding some probabilities together and these Ytl prime ses are just your probabilities coming out of your neural network and that's how you're getting your probabilities and there is going to be some multiplication for instance alpha t minus S is being multiplied by some probability and that multiplication corresponds to this independence assumption so there is a product there is a summation there is a summation here there is a product and you're just inserting additional blanks for this recurient to work this is really smart okay so S in the dynamic on the right S is the index going down Yes S is here and T is going across and this is t when in the end you're going to add alpha T L prime because this is the length of your L prime and the previous one。

So what I want you to do is just do this recursion on this example as an exercise so you just have to be careful for the math to work。

 but then you're going to be fine and then you're going understand this fully hopefully and there is also a backward pass this is the forward pass for the backward pass you need to take gradients of your loss is going to be very similar there is going to be a recursion for that and that's also going to be dynamic programming Yeah I've seen seen dynamic programming mentioned before but I haven't any of the details yeah if you go and apply to companies like Google Amazon some people get angry when they are asked brain teasers like this what is the minimum number of insertions substitutions and deletions to convert a string to another string this could be an interview question or there are a bunch of other interview questions about dynamic。

They give you a problem like this and then you need to break it apart into pieces and usually you can solve it with dynamic programming that's good know yeah so these are not brain teasers these are actually usefulB stuff cool that's that's all I had Thank you Jack perfect。


# P113：L54.1- 基于注意力的神经机器翻译 - ShowMeAI - BV1Dg411F71G

I think we have enough time to at least start the next topic about different types of attention so now that we learned about sequences and reccar neuralron networks and how to model sequences Let's go back to attention and see what type of attention mechanisms we can have and try to study that these we learned about you have encoder decoder architecture and input sentence goes in and output sentence comes out all we want to do is model this P of y given x y is ABCD sorry x is ABCD and y is X Y Z that your source sentence that your target sentence they have different length。



![](img/460f12699e9f2a3933b325f0878c5894_1.png)

![](img/460f12699e9f2a3933b325f0878c5894_2.png)

![](img/460f12699e9f2a3933b325f0878c5894_3.png)

![](img/460f12699e9f2a3933b325f0878c5894_4.png)

![](img/460f12699e9f2a3933b325f0878c5894_5.png)

![](img/460f12699e9f2a3933b325f0878c5894_6.png)

![](img/460f12699e9f2a3933b325f0878c5894_7.png)

![](img/460f12699e9f2a3933b325f0878c5894_8.png)

N on M。You can model the log of your probability。

![](img/460f12699e9f2a3933b325f0878c5894_10.png)

Because you are taking a log， there is a product， the log of a product is the summation of the logs。

 so that's what's happening here， given the previous words before the J word so let's say you are interested in predicting the J word you are going to condition on all of the previous words from one up until J and S S is going to encode the source sentence so S is source sentence or it's the source sentence representation but then we know that you're going to end up with HJ in the end you're going to take HJ you're going to correct its size。

 this is exactly that capital G matrix that we just saw so you can adjust it adjust the output to have the size of your vocabulary and then you do a softmax is going to give you the probability of the next word so that's how you model and you model H by a recurrent run network。



![](img/460f12699e9f2a3933b325f0878c5894_12.png)

![](img/460f12699e9f2a3933b325f0878c5894_13.png)

![](img/460f12699e9f2a3933b325f0878c5894_14.png)

![](img/460f12699e9f2a3933b325f0878c5894_15.png)

![](img/460f12699e9f2a3933b325f0878c5894_16.png)

![](img/460f12699e9f2a3933b325f0878c5894_17.png)

![](img/460f12699e9f2a3933b325f0878c5894_18.png)

![](img/460f12699e9f2a3933b325f0878c5894_19.png)

![](img/460f12699e9f2a3933b325f0878c5894_20.png)

![](img/460f12699e9f2a3933b325f0878c5894_21.png)

![](img/460f12699e9f2a3933b325f0878c5894_22.png)

And your recurren neural network could be a simple RNN， a GRU or an LSDM。

 and then in the end you have your corpus of input output data， input output translations。

 and then you are going to maximize the likelihood or equivalently minimize the leave of the log of the likelihood I'm going to stop here because we are out of time it's130 already and then we are going to continue next time from the attention models。



![](img/460f12699e9f2a3933b325f0878c5894_24.png)

![](img/460f12699e9f2a3933b325f0878c5894_25.png)

![](img/460f12699e9f2a3933b325f0878c5894_26.png)

![](img/460f12699e9f2a3933b325f0878c5894_27.png)

![](img/460f12699e9f2a3933b325f0878c5894_28.png)

For those of you who want to leave it can leave and for those of you who have questions and want to stay I'll be around I was curious about this diagram in the left top left the the input sequence ABCD then end of sentence X Y Z。

 is that just showing that as we translate we're really streaming like a paragraph and we translated on the fly by doing sentence by sentence or is is that showing like Y and then in a concatenation at the end of the sentence and then the other sentence X as inputs？



![](img/460f12699e9f2a3933b325f0878c5894_30.png)

![](img/460f12699e9f2a3933b325f0878c5894_31.png)

![](img/460f12699e9f2a3933b325f0878c5894_32.png)

![](img/460f12699e9f2a3933b325f0878c5894_33.png)

![](img/460f12699e9f2a3933b325f0878c5894_34.png)

![](img/460f12699e9f2a3933b325f0878c5894_35.png)

![](img/460f12699e9f2a3933b325f0878c5894_36.png)

So I guess your question is about this unit that unit the I guess the unlabeled blue ones in the top right and why Xyz is an input and an output Okay that's a good question and there are two things that you're going try to do okay there is a training and there is the inference and let's say that you already know the parameters of this model so you're trained it somehow I don't care how you did it you are giving me some good parameters now it's time to translate an English sentence pose in ABCD and the end of the sentence that your English sentence and then it's going to go through this encode coder RN and it's a stacked RN okay this is layer one that's layer2 it's both deep in time and space and then you're going end up with two h there is one h here one hidden state and there is another hidden state here now you want to output the first word of your translation so you want to。



![](img/460f12699e9f2a3933b325f0878c5894_38.png)

![](img/460f12699e9f2a3933b325f0878c5894_39.png)

![](img/460f12699e9f2a3933b325f0878c5894_40.png)

![](img/460f12699e9f2a3933b325f0878c5894_41.png)

![](img/460f12699e9f2a3933b325f0878c5894_42.png)

![](img/460f12699e9f2a3933b325f0878c5894_43.png)

![](img/460f12699e9f2a3933b325f0878c5894_44.png)

![](img/460f12699e9f2a3933b325f0878c5894_45.png)

![](img/460f12699e9f2a3933b325f0878c5894_46.png)

![](img/460f12699e9f2a3933b325f0878c5894_47.png)

![](img/460f12699e9f2a3933b325f0878c5894_48.png)

Put X what do you know at this point in time， you know ABC D， you know end of sentence。

 these are the information that you have so you can output the first word that's okay， okay， yeah。

 or you can output 10 options this is beam search actually you can output 10 words the highest probability ones but then you take those and then you push it through your neural network again because at this point in time。

 you know ABC D end of sentence and X so you're going to use that information to output the next word and you know X Y and the input sentence。

 you're going use that information to output the next word until you see the end of sentence and then you're gonna stop the next sentence because you don't want to continue this forever in all of these all of these。



![](img/460f12699e9f2a3933b325f0878c5894_50.png)

![](img/460f12699e9f2a3933b325f0878c5894_51.png)

![](img/460f12699e9f2a3933b325f0878c5894_52.png)

![](img/460f12699e9f2a3933b325f0878c5894_53.png)

![](img/460f12699e9f2a3933b325f0878c5894_54.png)

![](img/460f12699e9f2a3933b325f0878c5894_55.png)

![](img/460f12699e9f2a3933b325f0878c5894_56.png)

![](img/460f12699e9f2a3933b325f0878c5894_57.png)

![](img/460f12699e9f2a3933b325f0878c5894_58.png)

R andNs or GR users the previous hidden state and then the current word and so you're using the output of the translation as the new current word Yes that makes perfect sense and there is actually some language modeling also going on there for your translation so some of it is yes the input sentence and some of it is actually your outputted sentence making sense in that language have the correct semantics syntctic etc but for training that was for inference you do beam search for training you know ABCD end of sentence and you know Xz end of sentence you know everything and you can just use that to give you the probability so you know the probabilities of your input output sentences and then you can put it here on train it meaning you know the input output you pass it through your model you see what the model's probability assigns to it or you see what the model signs the probability of that pair and then you。



![](img/460f12699e9f2a3933b325f0878c5894_60.png)

![](img/460f12699e9f2a3933b325f0878c5894_61.png)

![](img/460f12699e9f2a3933b325f0878c5894_62.png)

![](img/460f12699e9f2a3933b325f0878c5894_63.png)

![](img/460f12699e9f2a3933b325f0878c5894_64.png)

![](img/460f12699e9f2a3933b325f0878c5894_65.png)

![](img/460f12699e9f2a3933b325f0878c5894_66.png)

![](img/460f12699e9f2a3933b325f0878c5894_67.png)

![](img/460f12699e9f2a3933b325f0878c5894_68.png)

![](img/460f12699e9f2a3933b325f0878c5894_69.png)

![](img/460f12699e9f2a3933b325f0878c5894_70.png)

![](img/460f12699e9f2a3933b325f0878c5894_71.png)

Exactly so basically you are reading of your likelihood you're saying that how likely is this pair of sentence of input and output sentences Yeah and then a a good modelll say that they're 100% likely to go together and you want to steer it towards that exactly so you want to increase the likelihood of that happening and that's the role of training so you train you come up with these good parameters and then you do inference you do translation this makes perfect you Any other question let's get us started I'm going go quickly through what we have done so far so we started with this paper neural machine translation which had everything in it it was defining the problem for us when it comes to inference then we had we introduced recurrent neural networks in particular gated recurrent neural networks and we were using them and then we introduced attention as well this was for modeling。



![](img/460f12699e9f2a3933b325f0878c5894_73.png)

![](img/460f12699e9f2a3933b325f0878c5894_74.png)

![](img/460f12699e9f2a3933b325f0878c5894_75.png)

![](img/460f12699e9f2a3933b325f0878c5894_76.png)

![](img/460f12699e9f2a3933b325f0878c5894_77.png)

![](img/460f12699e9f2a3933b325f0878c5894_78.png)

Proability once you know the probability you can write down your likelihood and once you write down your likelihood you can maximize it so the training data is in the form of source sentences target sentences you train your algorithm now it's time to evaluate it and we introduce the blue score it's not a perfect score but it's their score that you usually use in practice but then we said let's forget about attention for a while and just focus these sequence models focus on the required neural network。

 they encode their decoder approach and try to to use them so we try to use them for sequence to sequence learning in particular translation machine translation and we said it's not going do a good job on its own but if you use that if you use your neuraln network to re score the recommendations or the translations that。

coming out of your baseline system your statistical machine learning framework then you're going to get some improvements but on its own it's not enough to beat the state of the art then we said there is another way of doing it we can add these scores that come out of a neural network and add them as additional features to whatever hand engineer features that you had already for your statistical machine translation and yes these are independent and because they are independent they are going to add more information and therefore you managed to increase the performance of your statistical machine translation this way but again neural networks on their own were not able to give you good translation now this paper came along not only it introduced a new architecture so there is nothing special about this architecture is telling us that the encoder you can replace it with CNNs so that's cool but it made two observations that's going to help。

A lot it says that maybe the sentence length matters and the other observation is that the vocabulary size matters so the sentence length matters and this is proof if you increase the sentence length。

 the quality of your translation goes down if you believe that the blue score is a good score and no matter the architecture whether you're using RNN encoder or this gated recursive CNN encoder and in terms of vocabulary size if there are more unknowns or unknown words in your sentences。

 then the quality of the translation goes down so these two observation matter。

 then we go to the next paper and it's going to try to address the sentence length and the paper after that that we're going to cover is going to try to address the vocabulary size so we stopped here last session so we had this LSTM stacks of LSTM it was encoder decoder architecture。



![](img/460f12699e9f2a3933b325f0878c5894_80.png)

![](img/460f12699e9f2a3933b325f0878c5894_81.png)

![](img/460f12699e9f2a3933b325f0878c5894_82.png)

All we need to model is this probability of the output sentence given the input sentence Y is the entire output sentence X is the entire input sentence this is our sentence we have done it multiple times by now this is the target sentence they have different length then you write down the log of your probability and if you manage to do that the rest of it is optimizing this objective function maximizing this or minimizing the negative of this and there is nothing wrong with this objective function so given the source sentence and the previous words that you already translated predict the next word so that's our source sentence representation we usually write a model for G here because the dimension of the hidden states from these hidden states that are coming out of LSTN is usually different from your vocabulary size so you have to adjust a size you do some projection matrix vector multiplication and。



![](img/460f12699e9f2a3933b325f0878c5894_84.png)

![](img/460f12699e9f2a3933b325f0878c5894_85.png)

![](img/460f12699e9f2a3933b325f0878c5894_86.png)

![](img/460f12699e9f2a3933b325f0878c5894_87.png)

![](img/460f12699e9f2a3933b325f0878c5894_88.png)

![](img/460f12699e9f2a3933b325f0878c5894_89.png)

![](img/460f12699e9f2a3933b325f0878c5894_90.png)

![](img/460f12699e9f2a3933b325f0878c5894_91.png)

![](img/460f12699e9f2a3933b325f0878c5894_92.png)

![](img/460f12699e9f2a3933b325f0878c5894_93.png)

![](img/460f12699e9f2a3933b325f0878c5894_94.png)

![](img/460f12699e9f2a3933b325f0878c5894_95.png)

the softmax to turn them into probabilities we can have recurrent neural networks of various forms are enhanced GRs LSDMs。

 but once you do that you can write down your objective function you have pairs of input output sentences in your training corpus and then you try to minimize this once the objective function is minimized you have good parameters but the focus of this paper is trying to address the sentence length and they said maybe attention we need to bring back attention maybe that's going to help us address the issue with the sentence length and there are different versions of attention that this paper is going to introduce and we are going try to study all of them first of all what is this G function this G function is coming out of a matrix vector multiplication I need to tell you what is htilda htilda is a。



![](img/460f12699e9f2a3933b325f0878c5894_97.png)

![](img/460f12699e9f2a3933b325f0878c5894_98.png)

![](img/460f12699e9f2a3933b325f0878c5894_99.png)

![](img/460f12699e9f2a3933b325f0878c5894_100.png)

![](img/460f12699e9f2a3933b325f0878c5894_101.png)

![](img/460f12699e9f2a3933b325f0878c5894_102.png)

![](img/460f12699e9f2a3933b325f0878c5894_103.png)

![](img/460f12699e9f2a3933b325f0878c5894_104.png)

![](img/460f12699e9f2a3933b325f0878c5894_105.png)

![](img/460f12699e9f2a3933b325f0878c5894_106.png)

![](img/460f12699e9f2a3933b325f0878c5894_107.png)

H applied on a vector parameter matrix multiplied by two vectors H is the target hidden state so there is a target hidden state here and then there is going to be a source side context vector and this source side context vector is going to be dependent on the word that you are translating so this is very similar to the attention framework that we introduced before in the first slide rather than it being a single vector it's a vector that is time dependent and we know that C is going to be a linear combination of the hidden states of the source sentence and we have an attention budget of one and we are spreading it among all of these hidden state and that's going to give you CT okay but the focus here is trying to come up with different types of attention mechanisms for attention you're going have a budget of one therefore you're going to use a selfmax you can call it a line you can。



![](img/460f12699e9f2a3933b325f0878c5894_109.png)

![](img/460f12699e9f2a3933b325f0878c5894_110.png)

![](img/460f12699e9f2a3933b325f0878c5894_111.png)

![](img/460f12699e9f2a3933b325f0878c5894_112.png)

![](img/460f12699e9f2a3933b325f0878c5894_113.png)

![](img/460f12699e9f2a3933b325f0878c5894_114.png)

![](img/460f12699e9f2a3933b325f0878c5894_115.png)

![](img/460f12699e9f2a3933b325f0878c5894_116.png)

![](img/460f12699e9f2a3933b325f0878c5894_117.png)

![](img/460f12699e9f2a3933b325f0878c5894_118.png)

![](img/460f12699e9f2a3933b325f0878c5894_119.png)

![](img/460f12699e9f2a3933b325f0878c5894_120.png)

Attention， whatever that you call it is's gonna be a budget of one that you're spreading among your source sentences So the question is what is H bar S now H bar S is the source hidden state so you have a target hidden state and you have a source hidden state and these two are paying attention to each other how much attention should this at this point in time while predicting this word should we pay to the rest of the input sentence or the hidden state of the input sentence but until that point we knew about it it's all about this score how are you going to score if I give you a pair of target hidden state and a source hidden state how are you going to come up with this attention and there are multiple versions this version we saw so you first concatenate H and H bar you multiply them by a matrix this is equivalent。



![](img/460f12699e9f2a3933b325f0878c5894_122.png)

![](img/460f12699e9f2a3933b325f0878c5894_123.png)

![](img/460f12699e9f2a3933b325f0878c5894_124.png)

![](img/460f12699e9f2a3933b325f0878c5894_125.png)

![](img/460f12699e9f2a3933b325f0878c5894_126.png)

![](img/460f12699e9f2a3933b325f0878c5894_127.png)

![](img/460f12699e9f2a3933b325f0878c5894_128.png)

![](img/460f12699e9f2a3933b325f0878c5894_129.png)

![](img/460f12699e9f2a3933b325f0878c5894_130.png)

![](img/460f12699e9f2a3933b325f0878c5894_131.png)

![](img/460f12699e9f2a3933b325f0878c5894_132.png)

![](img/460f12699e9f2a3933b325f0878c5894_133.png)

Lned to having two matrices and multiplying them separately by Ht and h bar。

 but then you can concatenate and then write them in one shot you push it through an H and then you introduce some new parameters because this is a vector you want to turn it into a score it has to be a scalar So you do a dot product and this we saw before there is another alternative you know Ht you know Hrs just form the dot product of the two and this is the cosine similarity between the target and the source hidden states and there is a general formulation so it's generalizing the dot product you first multiply by a matrix in the middle and then you do your dot product This is the one that is going to survive and we are going to use that later on when we do transformer models so this is the one thats going to survive but different types of attention mechanisms where around and we are seeing different versions。



![](img/460f12699e9f2a3933b325f0878c5894_135.png)

![](img/460f12699e9f2a3933b325f0878c5894_136.png)

![](img/460f12699e9f2a3933b325f0878c5894_137.png)

![](img/460f12699e9f2a3933b325f0878c5894_138.png)

![](img/460f12699e9f2a3933b325f0878c5894_139.png)

![](img/460f12699e9f2a3933b325f0878c5894_140.png)

![](img/460f12699e9f2a3933b325f0878c5894_141.png)

![](img/460f12699e9f2a3933b325f0878c5894_142.png)

![](img/460f12699e9f2a3933b325f0878c5894_143.png)

![](img/460f12699e9f2a3933b325f0878c5894_144.png)

Today。There is another version and this version says don't pay any attention to the source sentence。

 just take whatever the outcome of the hidden state at this time is multiplied by matrix to a softm to turn it into numbers from zero to1 they add up to one and then that's going to give you at so this at is not paying any attention to any of these source sentences。

 so that's another version visually speaking this is what is happening for the global attention model you have Ht tilde which is here and this is the one that's going to give you the probability of your word that is being outputted so your word could be any of these in your sentence that is Ht tilde Ht tilde is going to depend on CT and H so it's going to depend on CT and Ht pairs of Ht and H bar。



![](img/460f12699e9f2a3933b325f0878c5894_146.png)

![](img/460f12699e9f2a3933b325f0878c5894_147.png)

![](img/460f12699e9f2a3933b325f0878c5894_148.png)

![](img/460f12699e9f2a3933b325f0878c5894_149.png)

![](img/460f12699e9f2a3933b325f0878c5894_150.png)

![](img/460f12699e9f2a3933b325f0878c5894_151.png)

![](img/460f12699e9f2a3933b325f0878c5894_152.png)

![](img/460f12699e9f2a3933b325f0878c5894_153.png)

![](img/460f12699e9f2a3933b325f0878c5894_154.png)

![](img/460f12699e9f2a3933b325f0878c5894_155.png)

![](img/460f12699e9f2a3933b325f0878c5894_156.png)

![](img/460f12699e9f2a3933b325f0878c5894_157.png)

arere going to give you are going to give you your scores and once you know your scores they are going to give you your attention vector so it's going to give you a global attention and this is going to add up to one it's going to be a vector that is going to add up to one it's elements and then to form CT you're going to take an input from here multiplied by these vector another input another element multiplied by this vector at them up all and that's going to give you CT so we know how to form C we know how to form80 we know what is H they are coming out of these red boxes and then in the end you're going to do your prediction so is everything clear with global attention I said one question about the index T is it it's like H1 and then H2 H3 and so on and those would be the four blue boxes the target or no target hidden state would be other way around the red the red hidden boxes but in the index by like12。



![](img/460f12699e9f2a3933b325f0878c5894_159.png)

![](img/460f12699e9f2a3933b325f0878c5894_160.png)

![](img/460f12699e9f2a3933b325f0878c5894_161.png)

![](img/460f12699e9f2a3933b325f0878c5894_162.png)

![](img/460f12699e9f2a3933b325f0878c5894_163.png)

![](img/460f12699e9f2a3933b325f0878c5894_164.png)

![](img/460f12699e9f2a3933b325f0878c5894_165.png)

![](img/460f12699e9f2a3933b325f0878c5894_166.png)

![](img/460f12699e9f2a3933b325f0878c5894_167.png)

![](img/460f12699e9f2a3933b325f0878c5894_168.png)

![](img/460f12699e9f2a3933b325f0878c5894_169.png)

![](img/460f12699e9f2a3933b325f0878c5894_170.png)

3，4 T is a a time index Yes， so it's going go one2。

34 and that's when you're predicting the first word in the sentence。

 the second word in the translation， the third word in the translation so T is counting that and then ask similarly it would be like source one23。

4 for the blue ones Yes exactly okay and then the question is at this point in time when you're outputting this word to each words in the input sentence are you going pay attention to and how much attention are you going to pay to each one of these hidden states Any other questions the other question I had is if the attention is a distribution over words or distribution over previous hidden states it's over the hidden states that are coming out Yeah that makes more sense Yeah perfect Thank you okay for this model it's for the hidden states we're going expand on that。



![](img/460f12699e9f2a3933b325f0878c5894_172.png)

![](img/460f12699e9f2a3933b325f0878c5894_173.png)

![](img/460f12699e9f2a3933b325f0878c5894_174.png)

![](img/460f12699e9f2a3933b325f0878c5894_175.png)

![](img/460f12699e9f2a3933b325f0878c5894_176.png)

![](img/460f12699e9f2a3933b325f0878c5894_177.png)

![](img/460f12699e9f2a3933b325f0878c5894_178.png)

![](img/460f12699e9f2a3933b325f0878c5894_179.png)

![](img/460f12699e9f2a3933b325f0878c5894_180.png)

![](img/460f12699e9f2a3933b325f0878c5894_181.png)

![](img/460f12699e9f2a3933b325f0878c5894_182.png)

But the point of this paper and why am I going through it is that you're gonna have you can have different models for your score people started with this concateated version。

 but then you can have the dot product and the general or no attention at all or local attention you pay attention to yourself you can expand upon that local attention why are we doing this because if you want to pay attention to everybody else in the input sentence it's going to end up being costly to reduce the cost maybe you're going to say I'm going only pay attention to a particular portion of the input sentence This is gonna to be a little bit tricky to explain but if you are a little bit patient things are going to become clear so you're now sitting at this point in time you can think of it as time you can think of it as index or you're sitting at this point and you want to predict this word maybe you're here and you want to predict why and you want to know where should I pay attention to。



![](img/460f12699e9f2a3933b325f0878c5894_184.png)

![](img/460f12699e9f2a3933b325f0878c5894_185.png)

![](img/460f12699e9f2a3933b325f0878c5894_186.png)

![](img/460f12699e9f2a3933b325f0878c5894_187.png)

![](img/460f12699e9f2a3933b325f0878c5894_188.png)

![](img/460f12699e9f2a3933b325f0878c5894_189.png)

![](img/460f12699e9f2a3933b325f0878c5894_190.png)

![](img/460f12699e9f2a3933b325f0878c5894_191.png)

![](img/460f12699e9f2a3933b325f0878c5894_192.png)

![](img/460f12699e9f2a3933b325f0878c5894_193.png)

![](img/460f12699e9f2a3933b325f0878c5894_194.png)

of all and you want to do it locally， first of all。

 you're going to say I'm going to have a P of T that is going to tell me where in the sentence I'm going to look at。

 so maybe you're going to look at here maybe that's your PT， that's the value of your PT。



![](img/460f12699e9f2a3933b325f0878c5894_196.png)

![](img/460f12699e9f2a3933b325f0878c5894_197.png)

![](img/460f12699e9f2a3933b325f0878c5894_198.png)

And then around that you're going to create an interval of maybe one word to the right。

 one word to the left or two words to the right two words to the left and pay attention only to those five words or three words and then your attention is going be zero everywhere else so the question is how we're going model this PT and it is exactly what I just mentioned as soon as you know PT you know your interval and once you know your interval you can pay attention to that interval locally and then the rest of the sentence you don't pay attention to so the question is how we're going model PT still your attention is going to be the same as before but now it's local okay rather than at having the size of the entire input sentence A is going have a size of 2D plus one and then the rest of it is zeros so you don't need to do extra computations。



![](img/460f12699e9f2a3933b325f0878c5894_200.png)

![](img/460f12699e9f2a3933b325f0878c5894_201.png)

![](img/460f12699e9f2a3933b325f0878c5894_202.png)

![](img/460f12699e9f2a3933b325f0878c5894_203.png)

![](img/460f12699e9f2a3933b325f0878c5894_204.png)

![](img/460f12699e9f2a3933b325f0878c5894_205.png)

![](img/460f12699e9f2a3933b325f0878c5894_206.png)

![](img/460f12699e9f2a3933b325f0878c5894_207.png)

![](img/460f12699e9f2a3933b325f0878c5894_208.png)

![](img/460f12699e9f2a3933b325f0878c5894_209.png)

![](img/460f12699e9f2a3933b325f0878c5894_210.png)

One model is that PT is equal to T just set it to be T if you're translating the fourth word in your target sentence。

 just go in your source sentence look at the fourth word and then create an interval around it that's one model this is called local n another model is that you can have this p to be a learnable function。

 maybe there is another one to one correspondence between words in the target sentence and the source sentence maybe it's better to do a predictive alignment okay let's say you have capital S and that's the size of your entire source sentence that's the length of it and that's capital S what you can do is you can parameterize if you multiply s by a number that is from zero to1 and then you quantize it because in the end you're going to need integers these are integers1。

234，5 etc if you multiply that by a number that's from zero to。



![](img/460f12699e9f2a3933b325f0878c5894_212.png)

![](img/460f12699e9f2a3933b325f0878c5894_213.png)

![](img/460f12699e9f2a3933b325f0878c5894_214.png)

![](img/460f12699e9f2a3933b325f0878c5894_215.png)

![](img/460f12699e9f2a3933b325f0878c5894_216.png)

![](img/460f12699e9f2a3933b325f0878c5894_217.png)

![](img/460f12699e9f2a3933b325f0878c5894_218.png)

![](img/460f12699e9f2a3933b325f0878c5894_219.png)

![](img/460f12699e9f2a3933b325f0878c5894_220.png)

![](img/460f12699e9f2a3933b325f0878c5894_221.png)

![](img/460f12699e9f2a3933b325f0878c5894_222.png)

It's going to tell you where you need to pay attention to maybe the length of your sentence is 12345 if you multiply 5 by let's say 0。

5 that's going to give you two and a half and then you're round it and maybe you're round it down and then you're paying attention your PT is going to be two but then the cool thing is that you can make this depend on your hidden state on the word that you're translating so you can say H you're going to multiply it by a weight。

 you're going multiply it by a10h and then because in the end you need a scalar you're going multiply it by a vector it's going to be a adult product it's going to give you a scalar from negative infinity to positive infinity。

 youre squash it through a sigmoid it's going to make this a number from0 to1 and now this is a learnable aligned position so you can learn it and once you know PT regardless of how you do it。



![](img/460f12699e9f2a3933b325f0878c5894_224.png)

![](img/460f12699e9f2a3933b325f0878c5894_225.png)

![](img/460f12699e9f2a3933b325f0878c5894_226.png)

![](img/460f12699e9f2a3933b325f0878c5894_227.png)

![](img/460f12699e9f2a3933b325f0878c5894_228.png)

![](img/460f12699e9f2a3933b325f0878c5894_229.png)

![](img/460f12699e9f2a3933b325f0878c5894_230.png)

![](img/460f12699e9f2a3933b325f0878c5894_231.png)

![](img/460f12699e9f2a3933b325f0878c5894_232.png)

![](img/460f12699e9f2a3933b325f0878c5894_233.png)

![](img/460f12699e9f2a3933b325f0878c5894_234.png)

![](img/460f12699e9f2a3933b325f0878c5894_235.png)

The rest of it mathematically is gonna to look like this， but on your computer。

 you don't need to pay attention to everything in your source sentence。 But what are we doing now。

 we still have this alignment of Ht and H bar S。 and that's exactly what you have up there。

 but then your alignment is gonna go exponentially fast to zero So this is an exponential function。

 It goes it's like a Gaussian distribution。 It's0 and then suddenly becomes nonze and then becomes0 again really fast。

 and then you can set the standard deviation of these to be d over 2。

 and this is basically paying attention to the words that are close to your aligned position Can I ask real quick it seems like the global attention is just a more general form because it's possible that you could。



![](img/460f12699e9f2a3933b325f0878c5894_237.png)

![](img/460f12699e9f2a3933b325f0878c5894_238.png)

![](img/460f12699e9f2a3933b325f0878c5894_239.png)

![](img/460f12699e9f2a3933b325f0878c5894_240.png)

![](img/460f12699e9f2a3933b325f0878c5894_241.png)

![](img/460f12699e9f2a3933b325f0878c5894_242.png)

![](img/460f12699e9f2a3933b325f0878c5894_243.png)

![](img/460f12699e9f2a3933b325f0878c5894_244.png)

![](img/460f12699e9f2a3933b325f0878c5894_245.png)

![](img/460f12699e9f2a3933b325f0878c5894_246.png)

In the global attention like framework， you could end up just paying attention to say one position Yes。

 so you're absolutely right the global attention model is a better model compared to the local one but it's always a tradeoff it's a better model but in the end it's more costly there's more learning time Yes。

 so it's a more costly because you have to pay attention to everybody in the source sentence and these source sentences could be really long Okay so you're trying to reduce the cost from the size of your source sentence S which could be large to something that is deterministic it's two d plus one it's always that number we are gonna talk about the cost of attention model so they are theyre good but they are not perfect Okay they have their own drawbacks you're costly last question on this like the main difference is the low local and so that would just change like WP with output something that's2 d plus one。



![](img/460f12699e9f2a3933b325f0878c5894_248.png)

![](img/460f12699e9f2a3933b325f0878c5894_249.png)

![](img/460f12699e9f2a3933b325f0878c5894_250.png)

![](img/460f12699e9f2a3933b325f0878c5894_251.png)

![](img/460f12699e9f2a3933b325f0878c5894_252.png)

![](img/460f12699e9f2a3933b325f0878c5894_253.png)

![](img/460f12699e9f2a3933b325f0878c5894_254.png)

![](img/460f12699e9f2a3933b325f0878c5894_255.png)

![](img/460f12699e9f2a3933b325f0878c5894_256.png)

![](img/460f12699e9f2a3933b325f0878c5894_257.png)

![](img/460f12699e9f2a3933b325f0878c5894_258.png)

BigV the W A matrix above would give you something that's as big as your sentence input sentence So you still have this W A's right still present because you have this alignment Okay you still have W you have more parameters here but then you you have your attention but you manually force it to be0 exponentially fast it's only non zero around that local point that you're interested in Okay any other questions so you can have different types of attention mechanisms and locally this is exactly what is happening have you still have h T tilde it's going to depend on C and H the question is how are you' gonna now compute C So and how you're going compute A first of all。

 you're going take H you're gonna multiply by a matrix you're gonna multiply it by another vector push it through sigoid multiply by。



![](img/460f12699e9f2a3933b325f0878c5894_260.png)

![](img/460f12699e9f2a3933b325f0878c5894_261.png)

![](img/460f12699e9f2a3933b325f0878c5894_262.png)

![](img/460f12699e9f2a3933b325f0878c5894_263.png)

![](img/460f12699e9f2a3933b325f0878c5894_264.png)

![](img/460f12699e9f2a3933b325f0878c5894_265.png)

![](img/460f12699e9f2a3933b325f0878c5894_266.png)

![](img/460f12699e9f2a3933b325f0878c5894_267.png)

That's going to give you PT So now you know PT P is going to tell you this location here。 Okay。

 perfect， so now that you know PT， you can go one word to the right one word to the left this is one word to the right one word to the left and then from that you can compute your attention So now you have an attention span of one and you're spreading it among three words rather than the entire input sentence okay once that's done you have A now C is gonna be at multiplied by these vectors So you have an attention span of one that you're spreading among these vectors that's going to give you C So do you see that difference here C is going to depend on everybody else in the source sentence。

 this is going to depend on the words in a local fashion So it's local There is another trick that I want you to learn and that's input feeding this happens a lot and this is going to improve the performance of your question translation So whatever hidden state that you end up。



![](img/460f12699e9f2a3933b325f0878c5894_269.png)

![](img/460f12699e9f2a3933b325f0878c5894_270.png)

![](img/460f12699e9f2a3933b325f0878c5894_271.png)

![](img/460f12699e9f2a3933b325f0878c5894_272.png)

![](img/460f12699e9f2a3933b325f0878c5894_273.png)

![](img/460f12699e9f2a3933b325f0878c5894_274.png)

Right before doing your translation， this is Hilda you take that and push it as input to your LsN the next LstM unit not only you input the word but only but also your inputting the hidden state that's called input feeding that's going to increase the performance so what happens after all of these which model are we going to use or we're going to use global attention or local attention and which one is the best first of all you can look at the perplexity so we are going to talk about perplexity when we do language modeling so you can have a perplexity for your translated sentences and for perplexity the lower is the better so it turns out that this local P general is doing the best so general is this general attention type here and local P is this predictive alignment model and it's giving you the best blue score for blue score the bigger is the better。

And don't worry about unknown because there are some ways to deal with unknown words in your sentences maybe a simple solution is that if you encounter an unknown word in your test data just copy it from your source sentence to a target sentence maybe the output here is an unknown but then you just copy it from B so you copy B and put it here that's one way to deal with the unknown words okay that was the story but if you remember we started this slide with a question and the question was this we want to address the problem of the sentence length and we had this observation that the blue score is going to go up and then it's going to drop and get lower as you increase the sentence length so this is the observation from the previous paper it turns out that attention。

 all of these other models have attention in them， it turns out that adding the attention is going fix that it's going to address that okay any question。

Before I move to the next topic and you had a quick question the local attention model has it looks like it has more parameters overall but it just has to consider fewer source hidden states Yes so you have more parameters because of computing this PT and there are two versions of it one of them adds no more parameters and the other version is adding some parameters Okay yeah I see that but the computational cost is lower much lower so is it the case that you only do this like this this Gaussian weighting on the alignment score for the locations as that fall within the alignment position window this is actually a mathematical way of doing it and this is exactly the question that we had from what happens if you are rounding PT to its nearest integer how do you differentiate through it for learning。

This is what you do for you to be able to differentiate through your attention mechanism okay you can keep PT to be 2。

5 and then you do your training this way， but once you do your inference you do that quantization so this is just a mathematical formula for you to be able to differentiate and then write it in a nice way but once the training is done you don't need to compute to pay attention to the things that are outside of this exponential okay so everything that's well I guess my question then is like outside the exponential exponentials are never exactly zero So is it that we're paying infinitely small amount of attention to all the words or do we mathematically speaking yes。

 but in practice you just set them to be zero you just trunccate it when it's outside the window Yes because you don't want to do extra computation so you take like you take like a Gaussian and then just chop it off on the left in the right tail when it gets outside of that plus or minus D window exactly。

Yes， that makes sense thank you Okay perfect and Matthew does that answer your question and how do you differentiate Okay。

 perfect， but the observation is that attention is important and it's important because of dealing with this sentence lens。


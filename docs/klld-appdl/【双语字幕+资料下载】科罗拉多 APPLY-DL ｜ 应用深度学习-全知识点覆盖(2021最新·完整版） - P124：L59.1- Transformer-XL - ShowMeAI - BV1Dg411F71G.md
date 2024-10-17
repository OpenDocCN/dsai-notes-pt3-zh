# P124：L59.1- Transformer-XL - ShowMeAI - BV1Dg411F71G

So in that case， let's start the next topic a little bit and then we are gonna continue it next session there is Transformer XL and let's see what the task is let's review transformer so now we are trying to improve transformers and we know that transformers they have a fixed context and we want to increase the context to be bigger that's your corpus of tokens that's your data and for language modeling given the previous words you're predicting the next word and these words you're gonna to encode them in a fixed size context if visually speaking this is what is happening for a transformer you have your sentence each word is gonna this is the decoder part of your transformer so there is some masking going on and these word is attending to these two this word is attending to these two etc This is for the training phase and you can have two segments。



![](img/310d4b6aae011608c0ce022e5ed37f42_1.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_2.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_3.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_4.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_5.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_6.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_7.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_8.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_9.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_10.png)

But then when you do your evaluation， this word here is going to always have this context for words as it context as you go to the next prediction this context here is going to get forgotten when you go to the next one this context here is going to get forgotten so you always have a limited context so next session we are going to increase the context to be more I mean how much that you need however much that you need Okay I think I'm going to stop here and for those of you who have questions I'll be around and for those of you want to leave somebody gives you a corpus it's a large corpus。



![](img/310d4b6aae011608c0ce022e5ed37f42_12.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_13.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_14.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_15.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_16.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_17.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_18.png)

And this corpus is going have some words in it， the task of language modeling is that given the past information you want to predict an X and basically you are trying to model the probability of your corpus or your sentences what you do regardless of the model that you choose。

 let it be an LSDM， let it be a reren neural network， let it be a GRU。

 let it be the decoder part of a transformer you are always trying to take this pass the context and encode it in terms of a fixed size hidden state okay let's take a look at transformer。

 the decoder part of a transformer and let's say you want to process your text in segments during the training phase you give it forward x1 x2 x3 x4 and here you are predicting x2 x3 x4 and x5 and during training you know this input。

 you know the output， you can write down your likelihood coming out of this probability。



![](img/310d4b6aae011608c0ce022e5ed37f42_20.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_21.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_22.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_23.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_24.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_25.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_26.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_27.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_28.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_29.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_30.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_31.png)

And you can do your maximization so you can maximize the parameters and this is a decoder part of your transformer why because this point here is paying attention to x1。

 this point here depends on x2 and x1 this point here depends on x1 x2 x3 so you're always depending on the past So it's one sided this is the decoder part of the transformer not the encoder now you go to the next segment。

 somebody gives you a new portion of your text， you take it you push it through your network。

 you do your predictions and you do do your training when you go to evaluation and testing the task is you want to predict x5 the next word。

 given the previous word this is okay for the first iteration for the first sentence you are paying attention to x1 x2 x3 and x4 while predicting x5 as you go to the next step which is predicting x6 x6 is gonna to depend on x2 x3 x4 and x5 so you're。



![](img/310d4b6aae011608c0ce022e5ed37f42_33.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_34.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_35.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_36.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_37.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_38.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_39.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_40.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_41.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_42.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_43.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_44.png)

Forget x1 as you go toward predicting x7， youre depending on x3 x4。

 x5 and x6 and you're forgetting the information coming from X1 and x2 so you always have a limited context for transformers the idea of this paper is that you want to extend the context and that's why you have Xl So it's going to be extra long context so how are we going to do it let's try it mathematically let's try to do that let's set tau to be1 so you're going S1 and S2 it's going to be segment1 segment 2 segment 1 is going to have x1 x2 up until x4 so a is4 segment2 is going to have x1 x2 up until xl or Xl so you're going to have two segments we divided our text into two segments segment 1 segment2 and these are conseative segments they have length L。



![](img/310d4b6aae011608c0ce022e5ed37f42_46.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_47.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_48.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_49.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_50.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_51.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_52.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_53.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_54.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_55.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_56.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_57.png)

These H they are what you see here so now we are here we want to go to the next layer for H1 this is going to have length L and each one is going to be a vector that is d dimensional that's going to give you H1 then you go to the next layer that's going to give you H2 up until the last layer so n is counting the layer and tau is counting the segment so you have H11 H12 H13 for segment 1 and you have H21 H22 and H23 for segment 2 forget about this Sg for now forget about the stop gradient whatever we're going to do we want these guys to pay attention to these entries as well so what you're going do is you're going to kind catnate along the sentence length so you're going to make your sentence2 times larger so it's going to be 2L。



![](img/310d4b6aae011608c0ce022e5ed37f42_59.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_60.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_61.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_62.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_63.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_64.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_65.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_66.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_67.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_68.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_69.png)

What you' are going do next is for these guys to pay attention not only to themselves。

 but also to the previous segments you take these guys H n minus1 tab plus1 so you're in segment2 and let's say n is2 so this is H21 so we are here you're going to multiply that by a query matrix so these are your weight matrices otherwise there is nothing to learn so you need to introduce weights and this we already did for the transformer model we are going to do the same thing but this is using H not H tilde but then for your key and value we are going to take h tilde so this is going to have length2 L Q is going have length L and now you're going do your attention you multiply query by key you do a self max and then you multiply by V so it's exactly your transformer layer and then you are going to do your masking because this is the decoder part of the transform。



![](img/310d4b6aae011608c0ce022e5ed37f42_71.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_72.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_73.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_74.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_75.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_76.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_77.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_78.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_79.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_80.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_81.png)

So you're going to do transformer layer， the decoder part， you do proper masking， query， key value。



![](img/310d4b6aae011608c0ce022e5ed37f42_83.png)

So query is coming from the sentence， the segment that you're interested in key and value are going to include the history but this is going to do your training there is a catch here the forward pass is fine it's going to be super fast but if you want to do the back pass you have to go through these derivatives and then you're going have a very huge sequence of derivative operations and that's going to be too costly so you're going to do an upper approximation you stop your gradients here so in tensorflow this is going to be Tf do stop gradient in p towards you're going to do dot detached so you're going to detach it so that the derivatives are not going to go past through the previous segment and there is nothing special about the previous segment you can actually have a history you can have a memory it doesn't have to have a size of L it could have a bigger size so it could have a size of M you could have a history that is as big as size。



![](img/310d4b6aae011608c0ce022e5ed37f42_85.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_86.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_87.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_88.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_89.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_90.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_91.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_92.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_93.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_94.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_95.png)

![](img/310d4b6aae011608c0ce022e5ed37f42_96.png)

M rather than size L， okay， so you can have a memory。



![](img/310d4b6aae011608c0ce022e5ed37f42_98.png)

Visually speaking what did we just do This is our new segment we are paying attention to itself and then this new segment is also paying attention to the previous segment so these new connections they are learnable the green ones the gray the darker gray are also learnable these connections here because after the stop gradient they are not learnable in this round they are learnable in the previous round okay but for this set of data they are not learnable because you are fixing the gradient this is this。

Set up these pair of sentences， pair of segments Now you go to the next pair of segments What you're going see is the same pattern as before。

 but now during the forward pass， these light gray connections means that there is some history going on So you're not forgetting you're not totally forgetting the past while computing these guys there is some information propagating forward maybe not backward。

 but forward there is some information propagating okay that's during training for evaluation。

 now you extended your context， it's not a fixed context of it's not a limited context anymore you extended it why because these guys are paying attention to here and then these guys is paying attention to here here and here and then you can expand it these guy is paying attention to here here and here so you can go up until X3 from x3 up until x。

So you extended it the context so is everything clear so far the big picture the idea any questions when do we wipe the context do we read until the end of the paragraph or the end of a document。

So you're going to need you're going to read during evaluation as much as you need so why predicting X 13 you are going to read from x3 until X12 and it's much better than a context of four okay and this depends the amount of context that you have depends on the choice of M that you have here yeah okay the bigger is m the more context you're gonna to have and then of course it's going to become more costly we know that attention is not costless computing this is going to become more costly okay there is always a tradeoff any other questions is also an added memory cost rate you have to keep the the H tilda which have the the hidden states from the previous window Yes absolutely so you're right but there is a catch you are this first author and a couple of other authors now you're really happy you manage to extend your context。

You're happy， you go sit behind your computer you code it up and your algorithm is not going to work and you're going to have that experience a lot while doing deep learning an idea looks very promising on a piece of paper but once you take it to computer things are not going to work so why is this not going to work the problem goes back to the details of positional encoding if you have absolute positional encoding by absolute I mean for each of these x1 for one2 three and4 you have their dedicated vectors so and they are going to have L max L Maxax is whatever position that you had here。

Okay if you have absolute positional encoding， what's going to happen。

 how are you going to distinguish between x tau and 10 and x tau plus1 and 10 both of them are going to have the same vector they're going to have the same positional encoding so you miss the position so you miss your order and that's why their framework was not working okay when they took it to computer it wasn't working so what is the fix the fix is you cannot store the absolute position for all of your corpus because then it's going to explode the corpus size is huge so you cannot have a matrix that huge the idea is perhaps all you need is the difference between the indices so maybe the relative position while paying attention while paying attention while x7 is paying attention to x3 maybe just the difference。

beten the indices is what you need So the relative distance between the two positions is going to be your positional encoding now you can have an L max and this is not going to explode okay but let's go a little bit into more details at least in the first layer you have positional encoding in addition to the wording embedding So you have position embedding and word embedding for instance let's say word Xj is paying attention to word X at location I what would you do you would write the embedding of X plus the embedding of the position Ui you multiply it by a weight matrix and then you do the inner product of that with another one this is word X I this is word Xj or word Xj word X it doesn't matter once you expand that term out this is what you're gonna get。

 you're gonna get E of X transpose Wq。transranpose w K E of Xj So these are your word embeddings for X word X and word Xj。

 then you're gonna to have the word embedding for X and the position embedding for Uj so these are the absolute positions you are gonna have the position embedding for I position I and the word embedding for word at position J and then you're gonna to have another one which is about position Here is a catch when you are doing relative positional link coding you're not going to have these terms you are not going to have Uj it doesn't make any sense anymore and you're not going to have Ui so we are going need to get rid of them let's try to do that This first thing is fine This is about word embeddings and we are fine this is not about position So term A is fine term B this term is fine this is also okay this term here we are going make it a dedicated matrix for R and then。

Rather than having UJ you're gonna to have the relative position between word I and word J and this is you're gonna to just read it out from the corresponding row of the relative positional encoding let's go to the next one Efxj is fine you're going have a dedicated matrix for WK and you're going call it WKE and then you don't have UI anymore it doesn't make sense you can merge UI and Wq into a vector which is learnable and then you go to the next one UI doesn't exist the same way that you merge UI Wq you're gonna merge Ui Wq here and call it V transpose it's another vector it's learnable and then you're gonna have a dedicated matrix here it's the same matrix as above and then UJ you're replacing it by your relative positional encoding and now you train your method and then it's gonna work okay are there any questions so this was a very important。

Minor detail that we needed to go through， okay。
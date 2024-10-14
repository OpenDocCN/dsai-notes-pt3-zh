# 【双语字幕+资料下载】官方教程来啦！5位 Hugging Face 工程师带你了解 Transformers 原理细节及NLP任务应用！＜官方教程系列＞ - P5：L1.5- Transformer：编码器 - ShowMeAI - BV1Jm4y1X7UL

In this video， we'll study the encoder architecture。

An example of a popular anchor only architecture is Bt， which is the most popular model of its kind。

Let's first start by understanding how it works。We'll use a small example using three words。

 We use these as inputs and pass them through the encoder。

We retrieve a numerical representation of each word。Here， for example。

 the encode converts those three words welcome to NYC in these three sequences of numbers。

The encoder outputs exactly one sequence of numbers per input word。

This numerical representation can also be called a feature vector or a feature tensor。

Let's dive in this representation。 It contains one vector per word that was passed through the encoder。

Each of these vector is a numerical representation of the word in question。

The dimension of that vector is defined by the architecture of the model for the base bird model。

 it is 768。These representations contain the value of a word， but contextualized。For example。

 the vector attributed to the word2 isn't the representation of only the two word。

It also takes into account the words around it， which we call the context。

As in it looks to the left context， the words on the left of the one we studying。

 hear the word welcome， and the context on the right， here the wordnyC。

 and it outputs a value for the word given its context。It is therefore a contextualized value。😊。

One could say that the vector of 768 values holds the meaning of the word within the text。

It does this thanks to the self attention mechanism。

The self attention mechanism relates to different positions or different words in a single sequence in order to compute a representation of that sequence。

As we've seen before， this means that the resulting representation of a word has been affected by other words in the sequence。

😊，We won't dive into these specifics here， but we' offer some further readings if you want to get a better understanding at what happens under the hood。

So when should one use an encode？Encodeders can be used as tenderalone models in a wide variety of tasks。

😊，For example， Bert， arguably the most famous transformer model， is a standalone anchor model。

 and at the time of release it be the state of the art in many sequence classification tasks。

 question answering tasks， and masked language modelling to only cite a few。😊。

The idea is that encoders are very powerful at extracting vectors that carry meaningful information about a sequence。

This vector can then be handled down the road by additional neurons to make sense of them。

Let's take a look at some examples where encodes really shine。First of all。

 mask language modeling or MLM。It's the task of predicting a hidden word and a sequence of word。Here。

 for example， we have hidden the word between my and is。

This is one of the objectives with which Bert was trained。

 It was trained to predict hidden words in a sequence。Encodes shine in this scenario in particular。

 as bidirectional information is crucial here。If we didn't have the words on the right is Silva and the dot。

 then there is very little chance that Bt would have been able to identify name as the correct word。

The encoder needs to have a good understanding of the sequence in order to predict a masked word。

 as even if the text is grammatically correct。It does not necessarily make sense in the context of the sequence。

As mentioned earlier， encodes are good at doing sequence classification。😊。

Sentiment analysis is an example of sequence classification。

The model's aim is to identify the sentiment of a sequence。

It can range from giving a sequence a rating from one to five stars if doing review analysis to giving a positive or negative rating to a sequence。

 which is what is shown here。For example， here， given the two sequences。

 we use the model to compute a prediction and to classify the sequences among these two classes。

 positive and negative。While the two sequences are very similar containing the same words。

 the meaning is entirely different， and the encoder model is able to grasp that difference。



![](img/9effa565b433264b98944ee23b41a7f0_1.png)

。

![](img/9effa565b433264b98944ee23b41a7f0_3.png)
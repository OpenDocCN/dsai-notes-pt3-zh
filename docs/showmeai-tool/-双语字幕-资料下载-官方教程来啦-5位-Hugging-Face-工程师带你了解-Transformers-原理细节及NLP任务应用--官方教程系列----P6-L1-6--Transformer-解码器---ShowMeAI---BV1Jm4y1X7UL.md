# 【双语字幕+资料下载】官方教程来啦！5位 Hugging Face 工程师带你了解 Transformers 原理细节及NLP任务应用！＜官方教程系列＞ - P6：L1.6- Transformer：解码器 - ShowMeAI - BV1Jm4y1X7UL

In this video， we'll study the decoder architecture。

An example of a popular decoder only architecture is GPT2。In order to understand how decoders work。

 we recommend taking a look at the video regarding encoders， they're extremely similar to decoders。

One can use a decoder for most of the same tasks as an encoder。

 albeit with generally a little loss of performance。

Let's take the same approach we have taken with the encoder to try and understand the architectural differences between an encoder and ID decor。

We'll use a small example using three words。 We pass them through their decoder。

We retrieve a numerical representation for each world。Here， for example。

 the decoder converts the three words welcomee to NYC and these are three sequences of numbers。

The decoder outputs exactly one sequence of numbers per input word。

This numerical representation can also be called a feature vector or a feature tensor。

Let's dive in this representation。It contains one vector per word that was passed through the decoder。

Each of these vectors is a numerical representation of the word in question。😊。

The dimension of that vector is defined by the architecture of the model。

Whether a decoder differs from the encoder is principally with its self attention mechanism。

 it's using what is called masked self attention。Here， for example， if we focus on the word 2。

 we'll see that this vector is absolutely unmodified by the NYC word。

That's because all the words on the right， also known as the right context of the word is masked。

Rather than benefiting from all the words on the left and right， so the bidirectional context。

 decoders only have access to a single context。Which can be the left context or the right context。

The mask self attention mechanism differs from the self attention mechanism by using an additional mask to hide the context on either side of the word。

The words numerical representation will not be affected by the words in the hidden context。

So when should one use a decoder decoders like encoders can be used as standalone models。

 as they generate a numerical representation， they can also be used in a wide variety of tasks。

 However， the strength of a decoder lies in the way a word can only have access to its left context。

Having only access to their left contacts， they are inherently good at tax generation。

 the ability to generate a word or a sequence of words， given a known sequence of words。😊。

This is known as causal language modeling or natural language generation。

Here's an example of how causal language modeling works。 We start with an initial word， which is my。

We use this as input for the decoder。😊，The model outputs a vector of numbers。

 and this vector contains information about the sequence， which is here a single word。

We apply a small transformation to that vector so that it maps to all the words known by the model。

 which is a mapping that will seeator called a language modeling head。

We identify that the model believes that the most probable following word is name。

We then take that new word and add it to the initial sequence。From my， we are now at my name。

This is where the autoregressive aspect comes in。😊。

Outtoregressive models reuse their past outputs as inputs and the following steps。Once again。

 we do the exact same operation。We cast that sequence through the decoder and retrieve the most probable following word。

In this case， it is the word is。We repeat the operation until we're satisfied。

Starting from a single word， we've now generated a false sentence。 We decided to stop there。

 but we could continue for a while。 GP T2， for example， has a maximum context size of 1024。

 We could eventually generate up to 1024 words， and the decoder would still have some memory of the first words and as sequence。

😊。

![](img/dfd8577ffd03c9ab167585435c2c2709_1.png)

嗯。

![](img/dfd8577ffd03c9ab167585435c2c2709_3.png)
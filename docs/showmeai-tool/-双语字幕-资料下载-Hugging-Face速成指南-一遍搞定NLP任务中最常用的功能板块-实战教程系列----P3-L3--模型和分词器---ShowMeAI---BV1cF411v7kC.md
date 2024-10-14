# 【双语字幕+资料下载】Hugging Face速成指南！一遍搞定NLP任务中最常用的功能板块＜实战教程系列＞ - P3：L3- 模型和分词器 - ShowMeAI - BV1cF411v7kC

Let's see how we can use this model and tokenizer directly and do some of the steps manually。 this will give you a little bit more flexibility。 So down here。 let's first use the tokenizer and see what this does。 So first。 let's call the tokenizer dot tokenize function。 So we say。

 let's call the tokens and then equals tokenizer dot tokenize and then the string or the sentence we want to tokenize。 So let's copy and paste this in here。 And then once we get the tokens。 we can use them and get the token Is out of it。 So we can say token Is equals。 And then we again use the tokenizer and the function convert tokenizer to。😊。



![](img/4e0ddcb38791825272bb7f961349fc05_1.png)

![](img/4e0ddcb38791825272bb7f961349fc05_2.png)

![](img/4e0ddcb38791825272bb7f961349fc05_3.png)

![](img/4e0ddcb38791825272bb7f961349fc05_4.png)

![](img/4e0ddcb38791825272bb7f961349fc05_5.png)

![](img/4e0ddcb38791825272bb7f961349fc05_6.png)

![](img/4e0ddcb38791825272bb7f961349fc05_7.png)

![](img/4e0ddcb38791825272bb7f961349fc05_8.png)

Called Is。 And then it meet the tokens。 So this is one way how to do this。 Or we can do this directly by saying token I equals。 And then we call this tokenizer like a function。 And then again， we give it the same string here。 So now let's print all these three variables to see where is the difference。

 So first we print the tokens， then we print the token Is。 And then here let's actually give this a different name。 So let's call this input I。 So now let's run this and see how this looks like。 Alright， so here is the result。 So as you can see when we call tokenizer dot tokenize， then we get a list of strings。



![](img/4e0ddcb38791825272bb7f961349fc05_10.png)

![](img/4e0ddcb38791825272bb7f961349fc05_11.png)

![](img/4e0ddcb38791825272bb7f961349fc05_12.png)

![](img/4e0ddcb38791825272bb7f961349fc05_13.png)

![](img/4e0ddcb38791825272bb7f961349fc05_14.png)

![](img/4e0ddcb38791825272bb7f961349fc05_15.png)

![](img/4e0ddcb38791825272bb7f961349fc05_16.png)

![](img/4e0ddcb38791825272bb7f961349fc05_17.png)

The list of the words backs so now each word is a sorry each word is a separate token and for example。 this one is our smiley face or our emoji So yeah this is what the tokenized function does and then once we call this convert tokens to IDs we get this one back so now it converted each token to an ID so each word has a very unique ID and this is basically the mathematical representation or the numerical representation that our model then can understand So this is what we get after this function and if we call this tokenr directly then we get a dictionary back and here we have the key input Is and we also have the attention mask so。



![](img/4e0ddcb38791825272bb7f961349fc05_19.png)

For now you don't really have to worry about this but let's have a look at the input IDs so if we compare the token IDs with the input IDs then we see we have the exact same sequence of token IDs but we also have this 101 and 102 token and this is just the beginning of string and the end of string token but basically it's the same so yeah this is the difference between these three functions and then these input IDs this is what we can pass to our model later to do the predictions manually so now like before we can also use multiple sentences of course for our tokenr so for example usually in your code you have your training data so let's say xtrain and in this example let's just。



![](img/4e0ddcb38791825272bb7f961349fc05_21.png)

![](img/4e0ddcb38791825272bb7f961349fc05_22.png)

![](img/4e0ddcb38791825272bb7f961349fc05_23.png)

![](img/4e0ddcb38791825272bb7f961349fc05_24.png)

Use these two sentences。 So this is our X train and then we and then we can pass this to our tokenizer and let's call this batch。 So this is our batch that we put into our model later。 So we say batch equals tokenizer and then we call this tokenizer directly with our training data。 and then I also want to show you some useful argument。 So we say padding equals true。

 and we also say truncation equals true。 and then we say max length equals 412。 and we say return tenss equals and then as a string P for pi torch。 So this will ensure that all of our samples in our batch have the same length。 So it will apply padding and truncation。

![](img/4e0ddcb38791825272bb7f961349fc05_26.png)

![](img/4e0ddcb38791825272bb7f961349fc05_27.png)

![](img/4e0ddcb38791825272bb7f961349fc05_28.png)

![](img/4e0ddcb38791825272bb7f961349fc05_29.png)

![](img/4e0ddcb38791825272bb7f961349fc05_30.png)

![](img/4e0ddcb38791825272bb7f961349fc05_31.png)

Necessary and this is also important。 So in this case。 we want to have a pytorch tenor returned directly。 So I will show you later what's the difference if you don't use this。 But for now let's just use this and then first of all。 let's print this batch and see how this looks like。 And then we see we get a dictionary and again it has the key input Is and the key attention mask and then here it has two tenzos。 So the first one for the first sentence and the second one for the second sentence and the same for the attention mask So two tens。 So yeah as I said， these input id are these unique Is that our model can understand。

 So yeah now we have this batch and now we can pass this to our model。![](img/4e0ddcb38791825272bb7f961349fc05_33.png)

![](img/4e0ddcb38791825272bb7f961349fc05_34.png)

![](img/4e0ddcb38791825272bb7f961349fc05_35.png)

![](img/4e0ddcb38791825272bb7f961349fc05_36.png)

And。
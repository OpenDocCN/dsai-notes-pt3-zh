# P127：L60.2- GPT-3 - ShowMeAI - BV1Dg411F71G

This is G3， so I'm going stop with G3， the language modeling part of the course or the NLP part of the course。

 I'm going to stop with GPT3。 but there are other improvements upon GP3。

 There is a paper by Google recently etc。 but you get the idea of how things are working。

 I think you have a solid background now that you can start reading the papers on your own So we have this we have this traditional fine tuning。

 which is bird type models you do fine tuning。 you do pretraining fine tuning pretraining fine tuning on the target task for the fine tuning part。

 You see an example let's say you want to translate that your downstream task and you already pretrained your language model。

 now you want to find tu。 This is not what you're going do for G3 by the way， an example comes in。

 you do some gradient updates。

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_1.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_2.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_3.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_4.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_5.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_6.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_7.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_8.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_9.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_10.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_11.png)

You do your stochastic gradient decentcent another example is gonna come in stochastic gradient decentcent and then you update your gradients until in the end you can do your prediction somebody gives you T cheese and then your model can translate this is fine tuning and you can think of it as if you are doing a soft conditioning on your data a data comes in。

 you update your gradients this could be soft conditioning okay the idea of GPT2 was that you can actually do hard conditioning what do I mean you can actually write down what you want from the model you want to translate English to French so you write it down。

 you describe your task you give it an example or a prompt and then your condition on this。

 your condition on translate English to French and cheese and then so your condition on your task description and your prompt and then you predict a couple of next words until you see the stuff。



![](img/1be330b1fcfcb6b59dcb50714f3dddd8_13.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_14.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_15.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_16.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_17.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_18.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_19.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_20.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_21.png)

Or the end of the sentence this is zero shot learning you can show it a couple of examples like here you are showing it C utter and the corresponding translation。

 you can show it an example in addition to task description and prompt and do a hard conditioning on this so your condition and you predict the next words you can have multiple other examples。



![](img/1be330b1fcfcb6b59dcb50714f3dddd8_23.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_24.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_25.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_26.png)

Rather than having one you can have multiple other examples and they can predict the next words so to me this is stronger in terms of conditioning that's why I'm calling it hard conditioning your conditioning on what you want to do you're coming up with your posterior distribution and you keep updating your prior as data comes in as examples comes in here it is soft conditioning a data comes in and you update your parameters another data comes in you update your parameters you are not conditioning on your data in a hard manner so that's the difference and the similarity between these two frameworks you still have that outer loop which is pre-training and that one you're going to do a stochastic gradient distant for the inner loop you are not going to do fine tuning you' are going to do in context learning you show it a couple of examples the task description the prompt and it has to do。

 for instance here it is the task is five plus a。

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_28.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_29.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_30.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_31.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_32.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_33.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_34.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_35.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_36.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_37.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_38.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_39.png)

is137 plus2 is9 you're describing your task that way and then you are going to show it I know10 I don't know5 plus2 is what equals and then the algorithm needs to tell you the answer this could be fixing the dictation or you can translate thanks Mer etc the idea of this paper is that you can actually scale this if you have 1。

3 billion parameters this was GPT2 and we saw that this wasn't beating the state of the art it was impressive that it was actually doing something but it wasn't beating the state of the art the idea of this paper is that what if you scale things you give it a lot of data and you throw at it a lot of compute and a lot of parameters what's going to happen or you going start seeing close to the state of the art results so this one is not a scaling that well but then as you go to 13 billion。



![](img/1be330b1fcfcb6b59dcb50714f3dddd8_41.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_42.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_43.png)

![](img/1be330b1fcfcb6b59dcb50714f3dddd8_44.png)

and you keep showing it more examples Okay this axis is the number of examples and if you go to 175 billion parameters and here you're going from zero shot framework to one shot framework or you keep showing it more examples a few shot and then you're gonna see much better accuracy and then your model starts to scale What is the data that they use it's a common crawl data set and they're gonna filter it there is the webtex data set there are two internet based books corpoa and there is the English language Wikipedia So for pretraining。

 they have a very large corpus basically the entire internet for fine tuning there is no fine tuning it's just gonna be in context learning so you can be shown it's hard conditioning you can use this model to solve different tasks and you can see the applications the applications are a lot one of the applications is generating text。

So you give it a paragraph and then it's going to keep imagining imaginary people and then coming up with a story of its own and sometimes this story is really hard for human to understand is it real or is it fake so you have to think a little bit more to understand whether it's a fake or it's a real text it's not that obvious that it's coming from a machine but one of you mentioned why are you going to 107 billion parameters or you were asking about GT2 two sessions ago why do you need to have a model that is that big can't you solve those problems？

With less parameters， the answer is yes， you can solve those problems with less parameters。

 but why are we going that route because we are now moving towards general AI Okay so far we were trying to solve the。

Sentiment analysis task， but now we want to have something that is capable of solving multiple different tasks。

 not only a classification task， not only a translation task。

 but all of them you give it a description and you want to solve that task you show it a couple of examples and you wanted to to solve that problem without changing your model so I was explaining about that story that this language model GPT3 is able to create but then sometimes you're going to see some discrepancies in the story and the reason for that。

 some people in the literature are claiming is that this model has only seen language it hasn't seen when let's say it is talking about an airplane it has never seen an airplane let's say it's talking about a chair it has never seen a chair or an image of a chair and maybe that is causing this problem。

 this inconsistes in this。And that's why today we are going to start with multimod learning not only you learn from languages。

 but you also learn from images at the same time you learn about speech let's say you want to design a robot and you want to talk to your robot you're gonna say take this up and put it on that table here what is this unless that robot is seeing that you're pointing at something then it's gonna know what this refers to so language alone is not enough it needs to be able to combine its vision and speech and text and language and human language to be able to do the type of tasks that you want to do Okay any questions about GT so in this inner loop here for these columns This is that few shots scenario Yes exactly Okay and so is there a fixed number of shots or is it like a random a random number of。

Actually， there is a diminishing return to the number of shots that you're showing it you can see it in this figure after a while。

 this is the number of shots that you're doing one shot to shot three shot for shots etc Okay I see 10 examples etc and then after you do that you update the gradient after each column No there is no gradient at all there is no gradient update within the column but after after you go through one few shot no there is no there is no fine tuning at all there is no fine tuning at all the outer loop is you pretrain you fix your parameters forever you don't update them anymore and then you keep conditioning on new examples there is no fine tuning it is saying here not use for G3 no fine tuning and so this no gradient update in this original pretraining is just some of the standard like what we saw in GT2 or bird or something Yeah so this is a very simple。

Model it's a decoder part of a transformer Pre an next word Okay predict the next subword So they just only relies for your downstream task it only relies on having just multiple shots improving the context actually it's going to do very good on some of these tasks for zero shot and one shot we saw it we saw GP2 was doing zero shot and one shot but the thing to know is that the question that you're asking is very fundamental there is no gradient update when you do in context learning you are just conditioning on the context so this is your context given the context predict an next word and then what you're going to do here is going to say five plus one and it's going to give you the answer so this is really impressive There is no fine tuning There is no gradient update it is one model that is solving multiple different problems and if you think about it you are getting closer to how human solve a problem you give them the context。

If I show you these examples， you're going to know how to solve the next task。

 if I show you these examples， you're going to understand the task and then solve it here youre learning from very few examples okay。

Yeah that that makes sense thanks yeah I had a question actually yes so know the data set that they are turning on is it's quite massive so in regard to the zero shot at one shot how do they actually know that it's zero shot and they haven't seen those turning？

I guess words or whatever they're turning on in the data spec because it's so large Yes so you're right there could be some data contamination maybe the model has seen these sorts of arithmetic before or the type of downstream task because your corpus is very large and if you read this paper it's a 75 page paper okay and they try to control for the contamination and study I would say if you read the paper the most frequently used in that paper is contamination yes you're right there could be data contamination Does it answer your question definitely and and here is where the data matters for instance the model that comes out of G3 could be sexist it could be racist it could have all sorts of biases because the text on the internet is crazy there is no filter on it okay any other questions in like a use case if。

I was going use GPT to say like solve a math problem like on the left here would I need to have on hand my set of few shot examples in addition to my like target Yes so you need to describe the task for it so this part is the small data that you have at hand and then the rest of it is just conditioning okay this is going be the input to G3 and then the output is going to be the answer to your problem no training so the other argument against these types of models the massive size models is that do you really need it to be that big and an answer to that is that this is just a small fraction of a human brain so this is a tiny fraction it's orders of magnitude smaller okay。

So what do you mean the brain has 86 billion neurons it's actually double the amount of neurons that a human brain does has the number of neurons is different from the number of connections okay。

 this is the number of connections these are the parameters okay and that could if you count the number of neurons and then you want to have pairs of connections between them these is a combinatorially huge size in terms of your parameters okay so this is in terms of parameters connections does that answer your question。

Yeah makes sense because human nuance at 86 by the connection is like tullions andions Yeah okay。

 so I said there are some drawbacks to these big language models and the drawback at least to me is that these models have not seen what they' are talking about is not grounded in terms of they have never seen a chair before they have never seen a table before they have heard about it in human language but they have never seen it so that's why we want to go to multimodal now。


# P126：L60.1- 跨语种语言模型 - ShowMeAI - BV1Dg411F71G

So far what we have been doing was about a single language。

 only English when we were doing language modeling today we are going to try to extend that to multiple languages or crosslingual language modeling。

And again we want to stick to the pretraining and then fine tuning paradigm it's similar to BRT now we want to extend it to multiple languages you're going have multiple languages and you're going to have crosslingual pretraining so far what we were doing was only single languages or single you have a single corpus for English for instance now we want to do cross-lingual pretraining and then we have some downstream tasks for each language specifically XLM is going to stand for crosslingual language models we are going to have monolingual data or parallel data for monolingual data you have N monolingual corpora so these are different for instance CI could be the corpus for English or the corpus for French Spanish etc and you have N monolingual corpes。



![](img/b7d1f8d51654c8bf6b23bb501eabac03_1.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_2.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_3.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_4.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_5.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_6.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_7.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_8.png)

That's going to be an unsupervised task， you can make your life a little easier by having parallel data so you have pairs of English and French data that's going to become supervised so it could be either unsupervised or supervised we have n monolingual corporal and then let's say an I is the number of sentences in each of those corpusees in C it sizes NI。



![](img/b7d1f8d51654c8bf6b23bb501eabac03_10.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_11.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_12.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_13.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_14.png)

You could have unsupervised which is that you don't have pairs of translations from English to French from English to Spanish etc。

 or you could have parallel data the first one is unsupervised the second one is going to be supervised first thing first you're going to need to say what is your vocabulary and how do you want to come up with we know about by pair encoding and now we are going to apply it on pairs of languages or on all of these corpes so we are going have a single vocabulary for the entire data so we are going to have a shared vocabulary we are going to use bi pair encoding and how do you come up with your data sentences to train this and how do you learn your bi pair encoded split。

 you' are going to concatenate sentences so you're going to sample a sentence from English you're going to sample a random sentence from French。



![](img/b7d1f8d51654c8bf6b23bb501eabac03_16.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_17.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_18.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_19.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_20.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_21.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_22.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_23.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_24.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_25.png)

them together and then that's going to give you your sentences that you're going to use to train the sub words in your by pair encoding So these are your by pair encoded sub words Now the question is how you're going to sample and with what probability are you going to sample from the first corpus with but what probability are you going to sample from the second corpus etc So you're going to sample according to a multinoial distribution with probability Qi So with probability Q1 you're going to sample a sentence from C1 with probability Q2。

 you're going sample a sentence from C2 corpus2 etc okay and one idea for Qi is that you' are going to look at this size of your corpus let's say alpha is one for now you're going to look at the size of corpus I you're going to divide it by the entire number of the entire size of your corpes So it's going to be the total number of。



![](img/b7d1f8d51654c8bf6b23bb501eabac03_27.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_28.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_29.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_30.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_31.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_32.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_33.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_34.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_35.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_36.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_37.png)

ents regardless of the corpus and that's going to give you piI so P1 P2 P3 P4 and these are going to add to1 you could sample according to that but then if a language has more data in it if a corpus for a particular language like English has more data there is bias towards that language to remove the bias you're going to take the square root of these pis but once you take a square root they're not going add up to one anymore So you're going to force them to add up to one this is a square root of pi the summation of over J of a square root of pjs now Qs are going to add up to one and this way you' are removing the bias towards high resource languages such as English or French etc okay so far so good and then you're going to apply by pair encoding and this kind ofcateninated sentences and that's going to give you your sub wordss so it's going to be。



![](img/b7d1f8d51654c8bf6b23bb501eabac03_39.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_40.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_41.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_42.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_43.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_44.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_45.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_46.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_47.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_48.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_49.png)

Shared vocabulary for the entire language， human language， whatever that is they it be English。

 French， whatever now now that you know your vocabulary whatever you're going to do you're going to apply a language model to it you can have causal language modeling and these was pretty the next word so these were AR models auto regressive models and these are the decoder part of your transformer you could apply a mask language modeling framework like BRT now the only catch here is first of all you have your total and embeddings these are coming out of your by pair encoded you're going to then need to know what position you're at and then you're going to need to know what language。



![](img/b7d1f8d51654c8bf6b23bb501eabac03_51.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_52.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_53.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_54.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_55.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_56.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_57.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_58.png)

This data is coming from what language so you're going to have a language embedding so if you are processing a sentence in English you're going to have a vector corresponding to English here。

 if you are processing the sentence in French you're going to have French here and then it's going to be masked wherever you have a mask you're going to predict it and then you're going to train that over the entire corpus all of your corpoa。



![](img/b7d1f8d51654c8bf6b23bb501eabac03_60.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_61.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_62.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_63.png)

This is good， This is when you have monolingual data。

 this is unsupervised the supervised here means that you have pairs of translations If you have that that's a luxury and you can use that and that's going to be called TLM so we have CLM MLlM and TlM This is translation language modeling here you have pairs of sentences in English and French and then you can feed the entire thing inside your transformer and then predict some words in English and some words in French and then you can train it。



![](img/b7d1f8d51654c8bf6b23bb501eabac03_65.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_66.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_67.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_68.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_69.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_70.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_71.png)

What is a downstream task you could have a natural language in in 15 different languages so that's a data set that I want you to explore it is X andI for instance your task could be in French pair there is a pair of sentences in French and the question is are they logically following each other are they contradiction or they are neutral what your sentences are in French what can you do you have a bunch of data now this is remember this is now the fine tuning this is the downstream task you have pairs of sentences in French and let's say you have a training data for that what you can do is you can translate your training data into English now your training data is now in English you train your you fine tune your natural your cross-lingual language model or your language model for that task。



![](img/b7d1f8d51654c8bf6b23bb501eabac03_73.png)

askIn English and then you can use that so the first obvious benchmark is that you're going to translate your sentences to English。

 solve your problem in English and then come back the other one is that you already have a good natural language inference framework trained on English data so you can now somebody gives you a test data what you can do is you can translate your test to English solve your problem in English and then report your results so one of them is operating on the training data one of them is operating on the test data these are gonna give you some baseline to work with or you can solve the task in its own language because now you're doing a transfer learning you're doing some transfer from English。

 some transfer from French and then you're transferring some information to Spanish okay。

So now all of these languages are talking to each other through this pretraining and then it turns out that if you have the luxury of having pairs of data or parallel data it being supervised then you're going to get the best results in terms of accuracy and the second best are if you don't have TLM that is for natural language inference you can solve some translation for translation machine translation for some of these languages you don't have pairs of data or that much pairs of data can you go to the extreme and have no translation at all and this is going to be called unsupervised machine translation so yes you can do unsupervised machine translation by unsupervised I mean it's just you use your language model and just apply it for the task of translation and you can have different types of embeddings actually doing transfer。

You can do your transfer learning on the encoder side。

 you can do your transfer learning on the decoder side if you start with wording beddings that's going to give you depth performance in terms of blue if you start random initially everything is random。

 that's your performance so it's very bad。If you do CLM on the decoder part your performance starts to improve if you do MLM on the decoder part you're going to improve if you do CLM on the encoder you're going to have a little bit of drop in performance and remember if this is blank it means that those inbeddings you're not doing any transfer learning so everything is going to start randomly and then you're going to train and then you can do some transfer learning CLM CLM CLM MLlM and the best one is MLlM MLlM it's performing the best for translation so these are our down astream task so you're down astream task could be supervised machine translation but now this is a low resource language Romania。

And you can have another low resource language and now you can improve the perplexity of Nepali and by training Nepali English and handy。

 the big ideas are these shared subward vocabulary the way that you're going to sample to remove the bias towards high resource languages。

 but the rest of it and the other one is these embeddings language embeddings the rest of it is the same paradigm of pre-training find unit so basically are extending BRT or GPT type models。

 GPT1 not GPT2 to multiple languages crosslingual models Any questions？Okay in that case。

 let's move to the next。
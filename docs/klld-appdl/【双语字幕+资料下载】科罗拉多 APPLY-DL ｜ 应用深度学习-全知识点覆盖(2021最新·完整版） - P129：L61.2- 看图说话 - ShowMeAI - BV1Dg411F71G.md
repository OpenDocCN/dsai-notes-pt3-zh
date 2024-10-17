# P129：L61.2- 看图说话 - ShowMeAI - BV1Dg411F71G

So now let's focus more on the task of somebody gives us an image and then we want to come up with a caption for it so we want the machine to describe it for us so we are going to show it and then the algorithm needs to tell what is happening in that image why is it helpful and immediate application that comes to mind is helping visually impaired people so it's going to explain what is happening on this image on the web for them that's an immediate impact but it's going to have a lot of other applications。



![](img/60f4b0239bb62bab456ee4485f2f8495_1.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_2.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_3.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_4.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_5.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_6.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_7.png)

It's actually going to help you understand what the neural network is thinking， where is it looking。

 etc， what it's seeing， because once it describes it。

 then you're going to know if it is making mistakes or no a couple of data sets that I want you to explore。

 the Pascal data set， Liquor 30K data， SBU and Coco， okay。



![](img/60f4b0239bb62bab456ee4485f2f8495_9.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_10.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_11.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_12.png)

What is a task you have an input image I previously were denoting it by X now let's denotote it by I okay that's just notation that's your input image the sentence is the target sequence of words so that's the type of data that you're going have input image the corresponding target the sentence caption and we want to model this likelihood the same way that you are modeling likelihood for languages you're going to model the likelihood for a pair of image and sentence S we know that these are coming from your dictionary it's an index or idea of a word in your dictionary and then the framework is going to be called neural image caption so if you hear Nick that that's this paper neural image caption and let's say you found a way to parameterize this likelihood using neural networks once you parameterize it it's going to have some parameters and then you do maximum likelihood or maximum of the log of the likelihood so。



![](img/60f4b0239bb62bab456ee4485f2f8495_14.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_15.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_16.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_17.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_18.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_19.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_20.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_21.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_22.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_23.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_24.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_25.png)

Smation is coming out of log of a product is the summation of logs。 Okay。

 and I and S are spanning your dataset。 It's the entire dataset set。

 These are elements of your dataset。

![](img/60f4b0239bb62bab456ee4485f2f8495_27.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_28.png)

And this is the role of training once you train it you're done we can use it in production now the question is how we're going model this log of this probability and we did this before we know that because it has a sequential nature not only we need to condition on the image we need to condition on the sentence that we have output it so far so this part P of S given I and theta we are going to use the product rule and expand in terms of so it's going to be a product of T from zero to n of P ofS given the rest of them now that you have a log the product is going to turn into summation。



![](img/60f4b0239bb62bab456ee4485f2f8495_30.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_31.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_32.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_33.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_34.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_35.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_36.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_37.png)

So now you need to model this and that we are gonna model with an R or with a fancy R I don't know an LSTM or a GRU the question is now what is this X what are your inputs the inputs are gonna be the previous words as well as the image now this is where the neural networks are going come in so you start from your loss and then you break apart your problem until you see your neural network and neural network is going be an LSTM input for output gate now here is the Google net architecture so don't worry about it that we cover in part one again think of it as a feature extractor an image goes in some magic happens here and then a vector is going to come out an image goes in a vector is going to come out you take that vector and that's the first input to your LSTM then your LSTM is going out with a hidden state the next input are gonna be your sentences so that's your first word you embed it that's going to be the input to your LSDM and then。



![](img/60f4b0239bb62bab456ee4485f2f8495_39.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_40.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_41.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_42.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_43.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_44.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_45.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_46.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_47.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_48.png)

You can continue This is how the hidden states are going to get handed over from one LSTM unit to the next LSTM unit and the output are probabilities probability of the next word so this is the log of the probability of the next word that are getting output it and this is exactly what you need it the log of the probability of the next word a little bit more mathematically you have a CNN it's going to take an image it's going to output the vector that's the first input that's x minus one and the rest of it is word embedding and then LSTMs that are outputting the probabilities of the next word now you have your likelihood you have your model it is parameterized this CNN you can either fine tune or you can just freeze the parameters here if you have enough data you can fine tune this if you don't have enough data just freeze this's your features extractor for your image you're going have a spatial token for the start of a。



![](img/60f4b0239bb62bab456ee4485f2f8495_50.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_51.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_52.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_53.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_54.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_55.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_56.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_57.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_58.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_59.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_60.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_61.png)

You're going to have a special token for the end of sentences is these are one0 vectors like what we were doing for languages W is our word embedding and now you have your likelihoodli or your last function because now you are multiplying it by a negative sign so that's going to give you a last function that is for training for prediction once the network is trained you're going to use beam search and we learned about beam search so let's say at time T you have k good sentences now you want to go to time T plus1 that's going to give you a bunch of words that you can concatenate to these sentences you do that then you look at the probability of each sentence and keep the top K and then you keep repeating the same thing and K could be a 20 or some number that you choose okay how is the model performing that's an image it goes in and it's going to tell you a person writing a model。



![](img/60f4b0239bb62bab456ee4485f2f8495_63.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_64.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_65.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_66.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_67.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_68.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_69.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_70.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_71.png)

![](img/60f4b0239bb62bab456ee4485f2f8495_72.png)

Ccle on a dirt road and these are good examples these are being described by the network accurately so without any errors a group of young people playing a game of frisbee a herd of elephants walking across a dry grass field these are being described whenever you write a good paper you shouldn't have only good results you should also report failure cases because then there is more room for improvement so somebody else is gonna to come out take over your method and improvement it these are some examples with minor errors for instance this is a close up of a cat laying on a couch。

 but this is not a couch this is probably a bed these are two hockey players are fighting over a pack it is right but there is no puck and they're not fighting over it they're in the same team perhaps two dogs playing in the grass maybe there are three of them and。

These are being somewhat related to the image， a red motorcycle parked on the side of their road。

 It is not on the side of their road and these are the failure cases。

 for instance this is interesting a refrigerator field with lots of food and drinks so this is what the network is thinking now you're getting into the network and it's thought process once it is able to describe something for you you're gonna to know what the network is thinking about perhaps it makes sense。

 perhaps it doesn't， but in terms of a data sets Pacal VOC has only 101000 test data flicker8K and 30k I mean they have ADK and 30K data span across training validation and testing Microsoft Coco and an SPPU is the largest you can have a human describing your images and then report the blue score of a human so these are the blue scores of a human。

These are the blue scores of Nick neural image caption， the method of this paper， so not bad okay。

And then you might wonder now that you showed your network not only images。

 not only words but also images did it actually learn something useful that you can transfer to other problems and the first question that you can start with is asking about these word embeddings how good are they so what are some neighbors of car and it's gonna to tell you van cap SUV vehicle jep boy it's a toddler gentle man daughter son etc so these are the neighbors of these words and you might say is this framework memorizing the data or is it capable of giving me new sentences。

 not include in the training data and these are examples of new data new predictions so a man holding a frisbee and his had a man standing in the grass with a frisbee etc so these are variations of that sentence that you could find in the training data so yes it can come up with sentences。

And it all， okay， is everything clear， any questions， any questions？Sure。

 so when we were doing LTM3 just NLP economic sense when we had the forget gate。

 but how does it work with an image with a different gates like an image factor because I have to all point of CNN is to really extract the main features so then we pass it through some forget gate so how does it actually work like what is the so the forget gate it's not only about the image it could be these words that you're forgetting and remember this forget gate is adaptive so a new data set is gonna go in a new data point and it's gonna to decide whether to forget it or no so it's not the case that you're always forgetting so this F is not always one so depending on the data that goes in it could change and actually the aim of these input gate forget gate output gate are for you to extend the memory of your LSTM G it's actually there to help you。

This forget gate is there to help you not to forget the image it is helping you it is helping your network deal with the vanishing gradient problem it is actually a good thing doesn't answer your question yeah okay perfect but yes you're right you might say that because you're inputting the image at the first entry of your LSDM you might forget it and you're absolutely right but you' are not bound to put it here you can take that image or the vector that is coming out of your CNN and push it everywhere so that you never forget and that we are going do later on in other papers Yeah that was that was my question was how to how to enforce that everything about the word prediction is given the same amount of context with the image Yes that you're going to do and that's a good question okay any other ones we are gonna keep improving this task it's one of the tasks that you're gonna end up working on a lot or seeing a lot of paper。

Is working on it， image description or caption generation。


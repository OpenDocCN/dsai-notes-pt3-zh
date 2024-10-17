# P165：L74.2- Deep Speech - ShowMeAI - BV1Dg411F71G

Now we learned a lot， we learned about our loss function， We learned how to decode given a speech。

 how do you output transcription， we learned about new loss， we learned about our data。

 So now we are in a comfortable position to move forward with another architecture for speech recognition for speech there is a me Spectroogram this we covered in the first slide and then given the me Spectrogram。

 you want to output some text So X is your speech Y is the corresponding label just to set the stage in terms of notnotation。

 and then your data set are pairs of speech and label speech label speech label that's your training dataset。



![](img/faf34092641a92d64ad5d017ffde67cb_1.png)

![](img/faf34092641a92d64ad5d017ffde67cb_2.png)

![](img/faf34092641a92d64ad5d017ffde67cb_3.png)

![](img/faf34092641a92d64ad5d017ffde67cb_4.png)

![](img/faf34092641a92d64ad5d017ffde67cb_5.png)

![](img/faf34092641a92d64ad5d017ffde67cb_6.png)

XI this X here is a time series is actually this speech spectrogram and they're gonna to have different length to T so for each X you have the corresponding ti and let's take a look at one element of that sequence so let's take a look at one of these guys let's say this guy that's gonna be a vector of audio features and what do they mean if it's a vector if you look at this element here the P element that's the power of the P frequency these axis here is time the other axis is frequency and these colors are the power or the energy in that particular bin and then you're gonna output your model is going to output the probability of C these are the outputs of your model there's a hat on it and then CT could be characters A B up until Z it could be a space it could be apost trophy or it could be a blank so。



![](img/faf34092641a92d64ad5d017ffde67cb_8.png)

![](img/faf34092641a92d64ad5d017ffde67cb_9.png)

![](img/faf34092641a92d64ad5d017ffde67cb_10.png)

![](img/faf34092641a92d64ad5d017ffde67cb_11.png)

![](img/faf34092641a92d64ad5d017ffde67cb_12.png)

![](img/faf34092641a92d64ad5d017ffde67cb_13.png)

![](img/faf34092641a92d64ad5d017ffde67cb_14.png)

![](img/faf34092641a92d64ad5d017ffde67cb_15.png)

![](img/faf34092641a92d64ad5d017ffde67cb_16.png)

![](img/faf34092641a92d64ad5d017ffde67cb_17.png)

![](img/faf34092641a92d64ad5d017ffde67cb_18.png)

The space is a different thing from the blank blank is just you outputting nothing that's for your speech for instance for this guy there is nothing that you're outputting or you could output the space because these are your words space is part of your characters H are your hidden hidden layer one hidden layer two up until the last hidden layer and then your80 is your input what is the first layer doing for deep speech it's based on a convolution and a convolution you take Xt and a context around it for instance maybe two timeless steps before and two timeless steps after that's your context one way to implement convolutions is just to turn this context so the entire window here into a long vector and multiplied by matrix so it's then going to be a fully connected neural network or a fully connected layer so you can think of everything here as fully connected the first。



![](img/faf34092641a92d64ad5d017ffde67cb_20.png)

![](img/faf34092641a92d64ad5d017ffde67cb_21.png)

![](img/faf34092641a92d64ad5d017ffde67cb_22.png)

![](img/faf34092641a92d64ad5d017ffde67cb_23.png)

![](img/faf34092641a92d64ad5d017ffde67cb_24.png)

![](img/faf34092641a92d64ad5d017ffde67cb_25.png)

![](img/faf34092641a92d64ad5d017ffde67cb_26.png)

![](img/faf34092641a92d64ad5d017ffde67cb_27.png)

![](img/faf34092641a92d64ad5d017ffde67cb_28.png)

![](img/faf34092641a92d64ad5d017ffde67cb_29.png)

![](img/faf34092641a92d64ad5d017ffde67cb_30.png)

![](img/faf34092641a92d64ad5d017ffde67cb_31.png)

is taking into account the neighborhood The next one you can think of them as one by one convolutions or fully connected ones。

 so it's just a linear combination of your previous hidden state plus a bias pushing it through value but this is modified value up until least point this is value but then you're capping your value at maybe 20 so that number is doesn't really matter so you're capping it at some point so that you can control the values of your age they don't get too big so these are not recurrent up until this point there is no recurrence there is a bunch of convolutions and then fully connected or actually one by one convolutions the next guy here is going to be recurret so you have a forward recurrence you have a backward recurrence and then you're going to add the two and then the last guy is again one by one convolution so ifs a combination of convolutions and recurrence。



![](img/faf34092641a92d64ad5d017ffde67cb_33.png)

![](img/faf34092641a92d64ad5d017ffde67cb_34.png)

![](img/faf34092641a92d64ad5d017ffde67cb_35.png)

![](img/faf34092641a92d64ad5d017ffde67cb_36.png)

![](img/faf34092641a92d64ad5d017ffde67cb_37.png)

![](img/faf34092641a92d64ad5d017ffde67cb_38.png)

![](img/faf34092641a92d64ad5d017ffde67cb_39.png)

![](img/faf34092641a92d64ad5d017ffde67cb_40.png)

![](img/faf34092641a92d64ad5d017ffde67cb_41.png)

![](img/faf34092641a92d64ad5d017ffde67cb_42.png)

![](img/faf34092641a92d64ad5d017ffde67cb_43.png)

![](img/faf34092641a92d64ad5d017ffde67cb_44.png)

archrchitecture and in the end you're going to output the probability of the next symbol being K and K could be any of these letters or the blank and then we know that we need to write down a loss。

 you can use the CTC loss you can train it and then you can decode it with beam search you just covered it the only thing that you change is the architecture and if you want to expand your beam search the one that I just explained before you are multiplying the probability of your language model by the probability is coming out of your CTC if you take the log that multiplication is just gonna turn into summation so it's the log of the CTC plus the log of the language model and there is also another catch here you can penalize the length of the outputted sequence in terms of word count so that they don't get too big terms of data set you can have Wall read journal which is somebody is reading from text you can have switchboard which is conversation。



![](img/faf34092641a92d64ad5d017ffde67cb_46.png)

![](img/faf34092641a92d64ad5d017ffde67cb_47.png)

![](img/faf34092641a92d64ad5d017ffde67cb_48.png)

![](img/faf34092641a92d64ad5d017ffde67cb_49.png)

![](img/faf34092641a92d64ad5d017ffde67cb_50.png)

![](img/faf34092641a92d64ad5d017ffde67cb_51.png)

![](img/faf34092641a92d64ad5d017ffde67cb_52.png)

![](img/faf34092641a92d64ad5d017ffde67cb_53.png)

![](img/faf34092641a92d64ad5d017ffde67cb_54.png)

![](img/faf34092641a92d64ad5d017ffde67cb_55.png)

![](img/faf34092641a92d64ad5d017ffde67cb_56.png)

![](img/faf34092641a92d64ad5d017ffde67cb_57.png)

You can have feature these dataset sets I want you to explore and it can have byu I don't think this dataset is available but these are so the size of the data is getting bigger and bigger this is 5000 hours of speech and these many speakers without the language model for the decoding whether you're gonna to get you're going say what is the weather like in Bostonin right now Prime minister Narenner Modi Arthur and ticket for the game but then as you add the language model the busin here is going to get fixed to be Boston Prime minister Narenra Modi that one is going to get fixed because probably Narenra is a word in your vocabulary and this is going to get fixed as well are there any tickets for the game so that's the effect of your language model in terms of numbers that was qualitatively quantitatively speaking you can compare。



![](img/faf34092641a92d64ad5d017ffde67cb_59.png)

![](img/faf34092641a92d64ad5d017ffde67cb_60.png)

![](img/faf34092641a92d64ad5d017ffde67cb_61.png)

![](img/faf34092641a92d64ad5d017ffde67cb_62.png)

some classical methods like Gaussian mixture models and hidden Markov models and some CNNs CNNs in addition to hidden Markov models and they can have deep speech trained on switchboard trained on this data and trained jointly on Swboard and fissure and then you're reporting the results in terms of word error rate so the lower is better and these for on these data sets C is a complex data it has noise in it so this framework is doing the best when your speech is noisy for instance there is noise in the background somebody is talking there are traineds going around there is noise but without noise this model apparently is doing the best but in total if you put these two together deep speech is the best okay and we are going cover another paper deep Sp2 which is going to improve upon this we're going to see that later on so there are these systems。

For a speech recognition you can actually go online and play around with them like Apple dictation。

 being speech， Google API， we AI on the clean and noisy on the clean you are getting some improvement out of deep speech so this is just testing those systems against each other on some clean dataset set and on some noisy data set and a noisy dataset you are getting a huge improvement okay any questions most of the hard part we covered in the previous topics so the easy ones was working with different architecture。

 any questions perfect。
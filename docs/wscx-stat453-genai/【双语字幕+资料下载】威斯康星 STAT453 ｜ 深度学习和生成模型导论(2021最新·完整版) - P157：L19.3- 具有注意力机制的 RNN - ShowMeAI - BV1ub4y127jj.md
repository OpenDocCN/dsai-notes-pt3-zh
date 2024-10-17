# P157：L19.3- 具有注意力机制的 RNN - ShowMeAI - BV1ub4y127jj

Alright so for this video I have a fun idea so some people complained that RNNs and LSTMs are not complicated enough。

 so in this video we are going to make them a little bit more complicated。

 so in particular we are going to talk about recurrent neural networks with a socalled attention mechanism that helps at dealing better with long sequences when we have tasks such as language translation。



![](img/4afda3b49113df2fe91c660d308afc56_1.png)

So just to yeah recap how language translation looks like。

 So this is a many too many architecture for language translation。

 So we have an input sentence and this input sentence gets parsed gets parsed into one hidden state so。

This whole part is， essentially。Encoding the input sentence。

 which is why it's also sometimes called as the encoder。Part of the RnN。

 similar to how you call the first layers of an auto encoder。

 the encoder because it's compressing the input into one， let's say hidden state。And then。We have。

This。Deder part of the R N， which takes in the hidden state， and then produces。

The translated sentence。If you are interested in playing around with an example。

 I haven't made one for this class， but theres an excellent tutorial here on the PitWatch website that you can check out。



![](img/4afda3b49113df2fe91c660d308afc56_3.png)

But before I show you how the attention mechanism works。

 let me give you an example of a language translation task。

 So here I'm translating one input sentence to an output sentence。

 So the input sentence is the English sentence today is a great day， and I'm translating it to。

Hotaist and Goar attack。 So I'm not sure if you can guess which language it is。

 maybe a fun question for Piazza。 In any case， one thing。

In this particular sentence is that it actually translates word by word。

 so if you would take a dictionary。You could technically just translate it， whoops。Word for word。

 So if you have a sentence like that， you could almost use the many to many R N that we learned about in the previous lecture。

 the。One where we have the inputs。Then。The hidden states。Then， the outputs。And we technically。

Could just have the setup like this， like a。Many too many set up where。

We are translating word by word。But this doesn't work for all sentences。

This is why we have this delete set up， where we usually。Don't have these parts。

And this one goes into。The decoder。And the decota then produces the outputs just based on the last state。

 because for some sentences， theres not this one to one correlation between input and output work。

 So for instance， heres another example sentence its if you have ever studied a foreign language。

 you have probably encountered a false friend at some point and here。



![](img/4afda3b49113df2fe91c660d308afc56_5.png)

This is the translation。 So one thing that happens is， for instance， this one， these two words。

Become one word。 It's called fpair， and。Another thing I can spot here is that the you you have and here also。

 it translates one time to this word。So actually， the combination of these two。

 which are farther apart。And then。For this Monday is no corresponding word really。And。😔。

This one corresponds to this one。 So in this way， here， it's not so obvious。

 Like we don't have this one to one mapping。 So things might be shifted a little bit around in that sentence。

 depending on the grammar。 So it's not。

![](img/4afda3b49113df2fe91c660d308afc56_7.png)

Super straightforward to use an architecture， like。



![](img/4afda3b49113df2fe91c660d308afc56_9.png)

The original one that I had before here because we can't just map input to output。

Which is why we have this set up this many too many set up where we have。

The input sentence that gets passed into this hidden representation。

 And then we have something that creates the output so the。Encodeder。And the decoder network。However。

 then one challenge is really that the network has to compress all the information into this one hidden state right。

 So essentially it's like reading the whole sentence here。

 it's reading the complete sentence and after reading the sentence。

 it's starting to translate So how do we make sure that the network even remembers right。

 So if it reaches this point， it has to contain all the information of the whole sentence and this can be actually quite challenging。

 I mean， even for instance， for you if you think about a sentence like。



![](img/4afda3b49113df2fe91c660d308afc56_11.png)

![](img/4afda3b49113df2fe91c660d308afc56_12.png)

Like this it's maybe easy because it's just four words so you can memorize them and then translate them。

 but let's say you have a longer sentence like that and I read this out loud and then I tell you in one minute you have to translate it but you're not allowed to look at the whole sentence anymore So in that way I think also you would have a challenge memorizing all the words in that sentence because it's a lot of words。



![](img/4afda3b49113df2fe91c660d308afc56_14.png)

![](img/4afda3b49113df2fe91c660d308afc56_15.png)

So the same for the R and N， it will probably be challenged to have all the necessary information in the hidden state。

 the longer the sentence becomes。

![](img/4afda3b49113df2fe91c660d308afc56_17.png)

So this is why researchers worked on this so called attention mechanism to address this issue of having poor performance on long sentences。

So。Here， this is going back to the paper by Baranau and cos and。As far as I know。

 this is the first paper that really proposed this attention mechanism。

 but I may be wrong there may have been other papers， but this is at least the one。

 the first one I am aware of。And。The key idea here is essentially that it's a mechanism that allows the model to automatically soft search for parts of a source sentence。

That are。Relevant for predicting a target word， so。



![](img/4afda3b49113df2fe91c660d308afc56_19.png)

If I go back one more time to my sentence here， So let's say it's currently at that point translating this sentence。

 oops， it's allowed to look。

![](img/4afda3b49113df2fe91c660d308afc56_21.png)

![](img/4afda3b49113df2fe91c660d308afc56_22.png)

Like in the original sentence， which words are most。

Most important it it has access to the whole sentence at each time step。Essential， that's the idea。

 And some words are more important than others。 So， for instance。

 this might have a very low attention， like 0 and。This one is kind of relevant。

 It has maybe attention close to one。 if we have an attention value between 0 and 1。

 So we have high and low attention for different words。 So that at each time step the the model。

We be allowed to take a look at different parts of the sentence。 that's like the new idea here。



![](img/4afda3b49113df2fe91c660d308afc56_24.png)

And。At the bottom here is an illustration of how they evaluated the performance。

 So there is something called the thing it's called blue score， and this is a score for computing。

 how good the quality of the translation is。So we won't go into too much detail of how that works for here for this lecture。

Just assume a higher blue score is better。Better if it's high。And。

What you can see here is the sentence length。 So they did experiments with different sentence lengths。

 And you can see that for。These two networks， these are。Abbreviated R N， ink，30 and 50。 So these are。

These are。Essentially， encoder networks like regular。 they are actually traditional R and N networks。

 So it's just like a shortcut for these networks。 and the 30 and 50 is how much access they have。

To the input， I think。And you can see that the performance yet drops。

Ds dramatically for sentence lengths， larger than 30。

So you can see it gets good performance in this region， but if you get longer sentences。Ler than 50。

Words， then the performance declines。 But when they use this。Tension mechanism here。 they。

 they get good performance， even for longer sentences。 So here the takeaway is that。

They find that the performance for longer sentences is better if they use this so called attention mechanism。

 So how does the attention mechanism work， That is what I will show you in the next couple of slides。



![](img/4afda3b49113df2fe91c660d308afc56_26.png)

Yeah， so as I mentioned before， for each word， there will be a certain context provided。

 so the network will be allowed to look at the input sentence and。

See which words are important for translating a given word so。Summarise。

 it would be assigning an attention weight to each word。

So that we know how much attention the model should pay to each word。

 so for each word the networks learns a certain context。

 so what is for this particular word what is the context of words that is relevant for translating this？



![](img/4afda3b49113df2fe91c660d308afc56_28.png)

So here's a figure from the paper。Outlining the whole mechanism in one slide。

 So one thing to notice is that there are。2 R ends。 So this is all my annotation。

 But this is what I got out of this figure。 So there are two R Ns。 First of all。

 they have a bidirectional R N。 We haven't talked about bidirectional R ends。

 but it's a very simple concept。 It's just running the。Recurrent neural network forward and backward。

 or you can also think of it running the recurrent neural network twice one time in the regular order and one time by having the sentence。

Put in in the reverse order。So。If we have the sequences or the input sentence。X1 to X T。

 This is our input sentence。 So one。R and N runs this forward like a regular R n from x1， x 2。

 x 3 and to x T。 So it produces these hidden states corresponding to it。

 And then you can also have a。The same concept running backwards。 So you just reverse the order， so。

This is shown at the bottom。 So you start with X T when you go to x 3， T，2 and 1。

 So you are just going backwards essentially。So yeah， this is a bidirectional RN。

It produces these hidden states。 And from the hidden states。

 there will be these attention weights that will be computed。 I will。

Show you how that works in the next couple of slides。 But here's just the overview。

 So we have a bi direction R N。Then we compute these attention weights。And these go into our。

R and N that does the translation now。 So I call this the regular R and N because it's not bidirectional。

 It's， it's more like a regular R and N works like we talked about before。

 except now that it also receives。These attention weights as input。

 So not only the attention weights， the attention weights weighted。 So here， in this case。

 the attention weight weighted with this。With this stuff here， so with this hidden state。

 I will show you how this gets computed in the next couple of slides。And then yeah。

 it also receives the hidden state from the previous slide。

 So here this is maybe a little bit confusing， but it's the S。

 the S is just a letter that they used to denote the hidden state of this other of the second R N because here we already used the word the letter H and they didn't want to use the same letter。

 I guess for here and here because then it would be a little bit also confusing So here S。It's also。

 the hidden。Hidden state， but no the hidden state of the second are in。

And then these are the translated words。

![](img/4afda3b49113df2fe91c660d308afc56_30.png)

So here in this illustration I'm trying to simplify or at least try to explain what's going on in the previous figure in a little different way。

 So I haven't mentioned before what we do now with the hidden states of the bidirectional R andN。

 so when we have the bidirectional RN I mentioned we are running it forward and backward to obtain these hidden representations。

 but now we have two sets of hidden activations， one from the forward pass， it's called that F1。

And at this point。 and then we also have the backward  one。 let's call it B1。

 So how do we combine the two。 So in practice， it's very simple。 we just concatenate those。

 So we have just a hidden state that is twice the size of a regular hidden state from just the forward pass。

 because yeah， we are just concatenating those。 So the concatenator。 Then let's call that H1。

 This is our hidden activation。And yeah here I'm trying to illustrate how the attention mechanism works。

 It combines multiple things。 It combines these hidden states。From the bidirectional R N。

And the activation， I sorry， the attention weights。 So these are。The attention。Wait。

 send these are the hidden。Activations。Of the bidirectional R N。 And this is the hidden。Actation。

SoLet's call this decoder。Oops。Decoder。R N， okay。そう。For a regular RnN。

 what happens is that we provide the original word as input if you think back of our word RnN at the very beginning of this lecture。

 we would provide a word X1 here as input and then we let's say predict the next word for the many too many one for language translation。

 we wouldn't have any input here， we would just use the hidden state from the previous time step when we are in the decoding part。

So here， what's new is compared to a regular word R and N where we get this x1， the word is input。

 we now take in。A context vector。 So this context vector provides information about the whole sequence。

 not just x1， the whole sequence， the whole input sequence in a regular Rn N。

 This would be encoded in the previous hidden state。So if we at time step1， this would be of course。

0， but now imagine we are， let's say at the fifth time step。

 so the fifth time step would combine in the hidden state or the previous four time steps。

But it's like a very compressed version and information might get lost。

And for each word also in the sequence。Different other words might be important。

 So it's kind of hard for a given time step to really ensure that right now it captures the important information for this current word。

 But then for the next one， it captures other important information。

 So it's easy to to forget what information was important from a previous time step and so forth。

 So to solve this problem， we have this context vector that allows us to take a look at the whole input sequence。

 So to illustrate this again。Remove this。Annotation， we have this C1 here and this C1。Is computed by。

Taking all the attentions multiplied by each hidden state， or。This multiplied， plus。This multiplied。

Plus these multiplied。 So it might happen that a word is not very important。 So in this case。

 if the word is not important， what would happen is that the attention weight would be。

 let's say close to 0， then it would not， let's say use this word。

 Other words might be more important， so the attention weight is larger。

And here's how the context vector is computed。 It's， yeah， summing over。

The tension weights alpha multiplied by these hidden activations。 That's how。

How we compute this context vector。 Now， how do we compute this attention weight itself， I mean。

 we talked about the hidden activation， right， So the hidden activation is。

Just the concatenation of the forward and backward hidden activation。 Now， how do we compute this。



![](img/4afda3b49113df2fe91c660d308afc56_32.png)

Attention weight。So the attention weight is computed by using another neural network， for instance。

Mtilayer perceptron。So。Let's maybe before we get to that， take a look at this current time step S1。

 So what does the current time step。Get as information。 So it gets as information。

 essentially this information from the hidden state hidden activations from the previous time step。

 And then we also have this。Hid an activation from the current time step， right， x1， so this is。

Previous hidden。Actation of。Previous。Time。Step。And this is the hidden。Actation of the current。

Time step and。This network here gets takes both as input。

 the information from the current time step and the information from the previous time step and then outputs a score E。

 This is a while。Unormalized。Attention weight。And this unmalized attention rate is put through。Oh。

 softftm。Function to normalize it so that the attention weights。嗯。Some up to one， right。

 So after softm， as you are familiar with。We would have。It should be。😔，Should be over with T。

 I guess。So， they should sum up。To one。And yeah， so this is how we compute these attention weights。

And yeah， there might be larger and smaller attention weights， given how important each word is。

 So it's， it's a form the attention weight depends on both。The current time input and。

The previous hidden state。 So the attention ratess might be different if we look at a different word。

 if we have maybe attention rates that say that this is。t8，1 and 。1 for the current word。

For for this context vector here。It might be different if we compute C2。

 it might happen that this word here， the first one is not that important。

 the second word is more important and so forth， so at each time step might be different words that are important。

So but yeah， the bottom line is that this attention mechanism allows the network to kind of get information from the whole input sequence at each time step in addition to just this compressed information from this hidden state。



![](img/4afda3b49113df2fe91c660d308afc56_34.png)

Alright， so to finish it up， here's another figure from the paper where they visualize the attention weights since the attention weights are values between。

0 and 1， my guess， is the white ones here correspond to a high attention rate of one and the black ones here correspond to a low attention rate of 0。

So I guess this is。1， and this is a0 here。So， here you have。Actually， not， I think。

They translated from English to French。Might be wrong。 I might be misremembering。

 So let's say this is our input。And this is。Output。

And then you can see for each word how much attention the network pays。When translating， so。

When translating， let's say the L here， it pays most attention to the， but also something to s。

And so forth。 And you can see for some。Likeake。The number here 1992， 1992。

 it really only pays attention。 You can see that。It only pays attention。To this number。

 which makes sense， right。So in this way， what you can see is the strong value。

Attention value in the diagonal， which means that it's kind of like a one to one translation in that way。

 but not always there are some cases where it pays attention to words that are also far apart in that sentence right so this is the attention mechanism and in the next video we will build on this idea。

By taking away the R and N part， because it turns out we just went from a very complicated model。

 The R and N added attention， but actually we don't need the R N at all。

 We can maybe also get good results with just attention。 And that is the topic of the next video。



![](img/4afda3b49113df2fe91c660d308afc56_36.png)
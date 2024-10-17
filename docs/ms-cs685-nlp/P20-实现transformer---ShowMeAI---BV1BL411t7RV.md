# P20：实现transformer - ShowMeAI - BV1BL411t7RV

是。Okay， hey everybody。 So I know last week there were a bunch of issues with the connection I have。

Changed the stream settings to be low latency， which I suppose means the video quality has been reduced。

 So before we start， if for those of you who are watching right now， if the。

If you can read the text on the screen， that's fine。

 but if you're having issues like maybe it's pixelated or something do let me know。

 I think I can go back and change the settings， but yeah I wanted to make sure it would be smooth this time so yeah let me know what you think。

And okay， so I will get started then today。 We're going to do something different based on one of the suggestions from Piazza。

 We will be implementing a transformer or okay I shouldn't say that We'll be implementing a very simple version of the transformer and really like what is the important thing that we need to teach here。

 It's mainly how we parallelize the computations of the self attention。

 The rest of it is just you know stacking up many layers。

 adding things like dropout and layer norm and so on。 That's all like not very I mean。

 those are just modules that you add in and pytorch and you can it's of course。

 important to understand how they work but the main advantage of the transformer is its parallelization during training time So that's what we'll focus on here。

😊，So there are two different collab notebooks that I linked on Piazza on the website for those of you who are watching or for those of you who are going to watch later I think these kinds of classes will go better if you open up the notebook and try to follow along and get the code to work So let's start with this first notebook CS685 attention exercise the goal of this this notebook is to create a self-atten network that's going to perform a simple classification task so here we're doing spam classification So we're using our transformer as an encoder here rather than as a text generation model or something like a language model we'll switch over to that in the next exercise。

 but I just wanted to illustrate kind of the basics of how you efficiently compute attention。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_1.png)

And this is a very simple task that's good for this purpose。



![](img/1bffdc57c2785e5647c824db2af3396b_3.png)

Okay， so I've provided you a bunch of scaffolding code here just because we went over a lot of this stuff when we did the implementation of the neural language model。

 how do you you know go from strings to sequences of indices and then format those into the proper way to get them into Pytorrch embedding objects and so on。

 but let's just quickly review so here we're importing torch and then we have these four sentences of data this is a task of spam detection so we get three instances of spam you want a billion dollars click here for midterm answers。

 send me your bank account info and then one instance of not spam read important CS685 news。



![](img/1bffdc57c2785e5647c824db2af3396b_5.png)

![](img/1bffdc57c2785e5647c824db2af3396b_6.png)

![](img/1bffdc57c2785e5647c824db2af3396b_7.png)

So the goal is of course to predict that these three are spam and this one isn't and for all of these exercises we're not going to be doing any sort of test time prediction。

 we're just going to be looking at the training loss。

 but I'd highly encourage you especially for the second exercise to spend some time implementing a sort of decoding process you can experiment with greedy。

 beam search， sampling， etc that'll be kind of informative for learning how these things work at test time。



![](img/1bffdc57c2785e5647c824db2af3396b_9.png)

![](img/1bffdc57c2785e5647c824db2af3396b_10.png)

But anyway， so we have these sentences， we have these labels。

 this chunk of code essentially splits up these sentences into tokens and then puts them into this vocab along with an index associated with each unique word type。

 and then this input's object at the end is going to contain the list of indices that corresponds to each of these sentences。



![](img/1bffdc57c2785e5647c824db2af3396b_12.png)

![](img/1bffdc57c2785e5647c824db2af3396b_13.png)

![](img/1bffdc57c2785e5647c824db2af3396b_14.png)

![](img/1bffdc57c2785e5647c824db2af3396b_15.png)

And again， feel free to ask if anything is unclear in the chat box I think this kind of lecture is maybe a little difficult to do in this live stream setting but I'll try and take any questions that come up so anyway this is what our input looks like after running the cell we have these four different lists one corresponding to each sentence and you can see that some of the words here are reused word 12 for example is CS 685 it occurs in two different sentences and so on。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_17.png)

![](img/1bffdc57c2785e5647c824db2af3396b_18.png)

![](img/1bffdc57c2785e5647c824db2af3396b_19.png)

Okay， so now there's some scaffolding code for our neural network as well this we're calling a selfattention NN and remember its goal is to be a classifier so we have this in function which we looked at in the previous implementation class this is where we initialize all of the parameters of our network so we're going to have an embedding layer of course this is going to be for the word embeddings we're going to have in our very simple network。

 a projection matrix for queries， keys and values so we're just going to be looking at a single layer selfatten network here。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_21.png)

![](img/1bffdc57c2785e5647c824db2af3396b_22.png)

![](img/1bffdc57c2785e5647c824db2af3396b_23.png)

![](img/1bffdc57c2785e5647c824db2af3396b_24.png)

So and once we get our values， we're going to then feed this to an output feed forward layer to compute the predictions。

 this is just a binary classification problem， is the input spam or is it not spam。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_26.png)

Okay so these are all the parameters that we have and we have some different types of attention。

 the only one we're going to be implementing today is this dot product attention。

 there are other functions here that in your free time you might want to play around with an implement yourself but we'll just go with the simple dot product note that the transformer in practice uses the scaled dot product。



![](img/1bffdc57c2785e5647c824db2af3396b_28.png)

![](img/1bffdc57c2785e5647c824db2af3396b_29.png)

![](img/1bffdc57c2785e5647c824db2af3396b_30.png)

![](img/1bffdc57c2785e5647c824db2af3396b_31.png)

![](img/1bffdc57c2785e5647c824db2af3396b_32.png)

Alright， and we've also given you some code to get started in the forward function here。

 So the forward function takes a single input， and that's like one of these sentences。

 So let's just go ahead and print this out to。😊。

![](img/1bffdc57c2785e5647c824db2af3396b_34.png)

![](img/1bffdc57c2785e5647c824db2af3396b_35.png)

![](img/1bffdc57c2785e5647c824db2af3396b_36.png)

![](img/1bffdc57c2785e5647c824db2af3396b_37.png)

See what it looks like。嗯。So it gets as input the first sentence here in our batch of our data set of four sentences。



![](img/1bffdc57c2785e5647c824db2af3396b_39.png)

![](img/1bffdc57c2785e5647c824db2af3396b_40.png)

And this is again a pytorrch tensor object now， so it has a size and yeah we're going to get the number of tokens in this input and store it in this n variable。

 so this is going to be the length of the input sequence Now we're going to embed these and get a matrix of size n。

 the sequence length by the embedding dimensionality。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_42.png)

![](img/1bffdc57c2785e5647c824db2af3396b_43.png)

![](img/1bffdc57c2785e5647c824db2af3396b_44.png)

![](img/1bffdc57c2785e5647c824db2af3396b_45.png)

![](img/1bffdc57c2785e5647c824db2af3396b_46.png)

Okay， so now our basic architecture of this network is going to be we're going to project these word embeddings to query key and value。

 then we're going to do the selfattention computation for each embedding。

 then we're going to somehow compose together all of the resulting output embeddings for each token into a single vector and pass it to this output feed forward layer which is going to give us our prediction。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_48.png)

![](img/1bffdc57c2785e5647c824db2af3396b_49.png)

![](img/1bffdc57c2785e5647c824db2af3396b_50.png)

And down here we have a training loop， this is similar to what we looked at in the previous implementation lecture。

 we've specified the number of epochs as 10， we're using the cross entropy loss。

 we initialize our network with what is this argument here， and embedding dimensionality of 20。

 and we have two possible outputs， spam or not spam and this is the length of our vocabulary。

 the number of word types that we have。😊。

![](img/1bffdc57c2785e5647c824db2af3396b_52.png)

![](img/1bffdc57c2785e5647c824db2af3396b_53.png)

![](img/1bffdc57c2785e5647c824db2af3396b_54.png)

![](img/1bffdc57c2785e5647c824db2af3396b_55.png)

We're going to train this using stochastic gradient descent with a learning rate of 0。

01 and then this is just a standard training loop it's doing back prop on the cross entropy loss and updating the parameters zeroing the gradient and printing out the loss of this classifier at each epoch so our expected output for this exercise is to see this loss go down to somewhere close to zero。

 which indicates that the network has at least overfit this tiny four sentence long training set。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_57.png)

![](img/1bffdc57c2785e5647c824db2af3396b_58.png)

![](img/1bffdc57c2785e5647c824db2af3396b_59.png)

![](img/1bffdc57c2785e5647c824db2af3396b_60.png)

![](img/1bffdc57c2785e5647c824db2af3396b_61.png)

All right， so that is a kind of quick overview of the code that's given now let's get started with some implementation。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_63.png)

![](img/1bffdc57c2785e5647c824db2af3396b_64.png)

So we've initialized this attention reps matrix， which is the same size as the embeddings matrix and this is going to be where we store our final attention kind of weighted average of each token in the sequence so I have n number of tokens and for each of these n positions I'm going to get a weighted average of the value vectors which I'm going to store in the corresponding row。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_66.png)

Okay， so let's get started with probably the simplest and dumbest but easiest to understand way of implementing this kind of self attention computation。



![](img/1bffdc57c2785e5647c824db2af3396b_68.png)

So the first thing that we want to do is pretty easy。

 we're going to just project these embeddings into the query key and value spaces。

 and we're going to do that by using our matrices that we've created up here， these linear layers。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_70.png)

![](img/1bffdc57c2785e5647c824db2af3396b_71.png)

So I can do this by just passing in Ms here， so this is going to give me another object of this size I can do the same thing with the keys。

This is the same dimensionality， I'll just write that。And the values。Okay。

 so I've got these three different projections and now I want to start computing the self attention。

And so the way I'm going to do this is of course， for each query embedding。

 I want to compute the dot product between that query and all of the keys。

 and then I want to apply the softftmax， I want to then take the weighted average of the value vectors and I want to store that in this attention reps function here。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_73.png)

So let's take a look at how to do this with a very simple and slow solution， so simple。

 slow solution for。Self attention， computation。And of course。

 because it's slow it's going to start with a loop。

 So I'm going to loop over every single position in the sequence。

 So we know that n is the length of the the input sequence here and at each position I'm going to take the current embedding as the the current query embedding and use that to compute this dot product against all of the keys。

 So。😊，At each iteration， at each position， I take query Q subi and product that。

The product with all keys。

![](img/1bffdc57c2785e5647c824db2af3396b_75.png)

Not good English， but you get the point。So we can do this pretty easily by using the matrix vector product function in pitorrch so my unweighted I guess I'll call this my norm scores is just going to be torch。

mv note that this function is a matrix vector product so the first argument here should be the matrix which is my keys again this is and by DMM size matrix and my query at this particular position isque'ries I this is going to be my vector。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_77.png)

![](img/1bffdc57c2785e5647c824db2af3396b_78.png)

![](img/1bffdc57c2785e5647c824db2af3396b_79.png)

![](img/1bffdc57c2785e5647c824db2af3396b_80.png)

So we would expect this to return a single score for every key。

 so this vector should be of dimensionality N and oops Python 2 syntax creeping in。

 let's see what happens here。

![](img/1bffdc57c2785e5647c824db2af3396b_82.png)

![](img/1bffdc57c2785e5647c824db2af3396b_83.png)

So yes， it does print out a single score for each of the different keys for this particular query。

 And now， again， these are unormalized， right， This is not a probability distribution so I can convert it to one by。



![](img/1bffdc57c2785e5647c824db2af3396b_85.png)

![](img/1bffdc57c2785e5647c824db2af3396b_86.png)

🎼Calling toch。 nn functional softm。 and I can apply it to my。



![](img/1bffdc57c2785e5647c824db2af3396b_88.png)

![](img/1bffdc57c2785e5647c824db2af3396b_89.png)

です。Unor scores and along the first dimension。

![](img/1bffdc57c2785e5647c824db2af3396b_91.png)

Sorry， these help boxes are covering up the code that I'm writing so now if I print out these probabilities。



![](img/1bffdc57c2785e5647c824db2af3396b_93.png)

![](img/1bffdc57c2785e5647c824db2af3396b_94.png)

I get an actual well formed probability distribution。

 so I've successfully computed the attention scores for the very first time step right when I is0 Now if I loop through this till I equals n。

 I'm going to get these probabilities for each position in the sequence。

 the only thing that's changing here is what query embedding I'm using。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_96.png)

![](img/1bffdc57c2785e5647c824db2af3396b_97.png)

![](img/1bffdc57c2785e5647c824db2af3396b_98.png)

Okay， so hopefully this makes sense so far and now the next step is of course。

 to take our attention weighted average of the value vectors。

So there are many ways in which you can do this probably the most straightforward is I mean this essentially can be done with another matrix vector product so if we want add values we can do torch。

mv and here。

![](img/1bffdc57c2785e5647c824db2af3396b_100.png)

Or we can do this， which will give us an attention weighted average of the value vectors。

 There's an alternate solution， which is probably more straightforward to understand where。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_102.png)

Actually， I。Should take that back。 It's not as straightforward to understand， but it。

 it introduces an important concept， which you should certainly understand。 So values here got these。



![](img/1bffdc57c2785e5647c824db2af3396b_104.png)

Help boxes are annoying values times。

![](img/1bffdc57c2785e5647c824db2af3396b_106.png)

Probabilities so this asterisk means we're doing an elementwise product。

 So every single element of the values matrix is being multiplied by this probabilities this pros vector。

 So of course， this doesn't make sense because values is a matrix and pros is a vector so they don't have the same number of elements I can't just do an elementwise multiplication。

 but that's where this very important concept of broadcasting comes in。

 So I want to essentially multiply each element of a row in the values matrix by the same probability right and then I can sum over all of these elementwise product over the rows to get my attention weighted average。

 So to make to kind of duplicate。😊。

![](img/1bffdc57c2785e5647c824db2af3396b_108.png)

![](img/1bffdc57c2785e5647c824db2af3396b_109.png)

this probs vector across this first dimension I can do broadcasting where I say that essentially I'm putting in this non argument and the second axis。

 so this is normally how we index Pytorch tensors， but none here indicates that I want to broadcast the same value in this first dimension across this second dimension here。

 So this is going to allow me to do an elementwise product between this matrix and this vector because this vector has been broadcast into the second dimension。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_111.png)

![](img/1bffdc57c2785e5647c824db2af3396b_112.png)

So once I do this element wise product I'm going to sum over the first dimension which is going to give me my weighted average of the value vectors so these two things are equivalent I won't belabor the point you can try them out afterwards and make sure you understand what's happening here but both of these are just ways of getting the weighted average of the value vectors using the probabilities that we computed as the weights。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_114.png)

Okay， so we'll go with this one for now and we're just going to store this thing into our attention reps。



![](img/1bffdc57c2785e5647c824db2af3396b_116.png)

Matrix at the corresponding dimension。

![](img/1bffdc57c2785e5647c824db2af3396b_118.png)

Okay。So we did this and now we're going to first there there is， of course。

 a more efficient implementation of the attention， which we'll get to a little later。

 but for now we're going to just connect this attention reps into our our classifier and make sure that the loss is actually going down So making sure that we've done this properly So the last thing that I need to do is now I have attention reps。

 which is end by DM。😊。

![](img/1bffdc57c2785e5647c824db2af3396b_120.png)

![](img/1bffdc57c2785e5647c824db2af3396b_121.png)

![](img/1bffdc57c2785e5647c824db2af3396b_122.png)

![](img/1bffdc57c2785e5647c824db2af3396b_123.png)

![](img/1bffdc57c2785e5647c824db2af3396b_124.png)

嗯。Matrix， and I want to get it down into a single vector that represents the entire sequence before I feed it to this output。



![](img/1bffdc57c2785e5647c824db2af3396b_126.png)

So compose。🎼Attention reps into a single vector。 So there are many ways you can think about doing this。

 but this is a very simple example。 So we'll just simply average。



![](img/1bffdc57c2785e5647c824db2af3396b_128.png)

So we can do torch。 mean。

![](img/1bffdc57c2785e5647c824db2af3396b_130.png)

Attention。Reps zero equals0， so we're going to average across the sequence length dimension and get a single vector that's of the size of the embedding dimensionality。

So if I print this， for example。

![](img/1bffdc57c2785e5647c824db2af3396b_132.png)

![](img/1bffdc57c2785e5647c824db2af3396b_133.png)

嗯。

![](img/1bffdc57c2785e5647c824db2af3396b_135.png)

I get just a 20 dimensional vector， which is the size of my embedding dimensionality。 So I mean。

 we've talked about many other ways of composing multiple representations into a single one in Bt。

 we wouldn't even have to do this right because we would just index the CS representation and feed that into the classifier but we're not using Bt here。

 So we have to train our own thing。 and now we can just use the existing code here。

 which feeds in this composed vector into the output classifier。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_137.png)

![](img/1bffdc57c2785e5647c824db2af3396b_138.png)

![](img/1bffdc57c2785e5647c824db2af3396b_139.png)

Okay， so if we train this function， all right the loss is going down but not too much。

 maybe we can try increasing our learning rate all right so that helped so we can see that our loss function went from somewhere close to 3 to down to 0。

12 of course if we train with more epochs， we will likely get to something very close to 0。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_141.png)

![](img/1bffdc57c2785e5647c824db2af3396b_142.png)

![](img/1bffdc57c2785e5647c824db2af3396b_143.png)

![](img/1bffdc57c2785e5647c824db2af3396b_144.png)

Okay， so I've just shown you this incredibly slow and solution for self-atten that you shouldn't use in practice and that no implementation of the transformer like the Pytorch default。

 for example， doesn't use this either。 but now let's get into a more efficient implementation。

 I guess before that is there a way for us to keep track of tensor size besides putting them in comments I usually just put them in comments I guess if you're playing around with it。

 you can come up with some other way， but yeah I'll try and be better about putting them in comments can you explain how non workss in broadcasting here So right none when you're doing broadcasting essentially means you want to make a new dimension and copy this thing over So let's maybe I think to explain this I'll show a simple example。

 just do it in this loop because why not So let's say that I have。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_146.png)

![](img/1bffdc57c2785e5647c824db2af3396b_147.png)

![](img/1bffdc57c2785e5647c824db2af3396b_148.png)

![](img/1bffdc57c2785e5647c824db2af3396b_149.png)

嗯。A matrix。Of ones， so it's going to be all ones。And let's say it's going to be five by five。So。

Does this work， first of all？

![](img/1bffdc57c2785e5647c824db2af3396b_151.png)

Okay， so we have this matrix。 and now let's say we have this vector。



![](img/1bffdc57c2785e5647c824db2af3396b_153.png)

呃。Let's say， it's going to be a。呃。I think this is all I need to provide。



![](img/1bffdc57c2785e5647c824db2af3396b_155.png)

Okay， so I have these two vectors， and I want to multiply them together。 Oh。

 I think I should make this a。

![](img/1bffdc57c2785e5647c824db2af3396b_157.png)

![](img/1bffdc57c2785e5647c824db2af3396b_158.png)

Float tensor， and maybe I can do that。Like this。

![](img/1bffdc57c2785e5647c824db2af3396b_160.png)

Yeah， okay， so， so basically， if I want to multiply or take the dot product between this so like。嗯。



![](img/1bffdc57c2785e5647c824db2af3396b_162.png)

So let's just look at where the broadcasting is used in our example。

 We're using it to do this element wise product。 And then we're summing after that。

 So let's let's take a look at what happens if I apply the same computation So I basically want to multiply every row here with this vector。

 That's that's my goal。 But of course， I can't just do an element wise product because these are different dimensions。

 right？ So。😊。

![](img/1bffdc57c2785e5647c824db2af3396b_164.png)

![](img/1bffdc57c2785e5647c824db2af3396b_165.png)

![](img/1bffdc57c2785e5647c824db2af3396b_166.png)

![](img/1bffdc57c2785e5647c824db2af3396b_167.png)

Broadcasting explanation。 So let's just， first of all。



![](img/1bffdc57c2785e5647c824db2af3396b_169.png)

Make that clear。Oh， so this actually did the broadcasting automatically so this is what we want to happen。

 I didn't realize that it would automatically do that。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_171.png)

But。Usually in something like nuy you'll get an error when this happens because this vector is not the same dimensionality as the matrix and so what you do with none is it essentially just duplicates this vector rowize into a matrix such that you can actually do this multiplication so this gives you the。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_173.png)

![](img/1bffdc57c2785e5647c824db2af3396b_174.png)

Oh interesting so yeah it depends on what dimension you broadcast into so I think this would be the equivalent of the Pytorch case。

 so actually this is a good demonstration right of what's actually happening so。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_176.png)

![](img/1bffdc57c2785e5647c824db2af3396b_177.png)

![](img/1bffdc57c2785e5647c824db2af3396b_178.png)

![](img/1bffdc57c2785e5647c824db2af3396b_179.png)

![](img/1bffdc57c2785e5647c824db2af3396b_180.png)

Okay， so。Maybe I should。

![](img/1bffdc57c2785e5647c824db2af3396b_182.png)

Print mat。

![](img/1bffdc57c2785e5647c824db2af3396b_184.png)

So here if I apply the none to the first dimension of this vector object。

 then it basically takes this and multiplies it with each row of the matrix right so it's expanding in the row direction which means the broadcasting operation essentially just copied this into five different rows of the0。

1，2，3，4。

![](img/1bffdc57c2785e5647c824db2af3396b_186.png)

And that's why you see the output product is just01，2， three，4，01，2，3，4， and so on。



![](img/1bffdc57c2785e5647c824db2af3396b_188.png)

However， if we use this operation， it's going to do this multiplication column wise。

 so here we've instead made a matrix where each column in the first so each element in the first column is 0。

 each element in the second column is1，2，3，4 and so on。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_190.png)

So this is what is happening and the nonen is essentially telling you which dimension you want to copy over。

 you can think about it that way， although in practice nothing is really being copied in memory。

 this is an efficient way of duplicating your data in the matrix without incurring memory penalties。



![](img/1bffdc57c2785e5647c824db2af3396b_192.png)

Okay， if you use a matrix size that isn't a square matrix your code， okay maybe yeah。

 maybe you're right， but yeah we won't go into that here。

 we are essentially converting a 1D row vector into 2D column matrix and broadcasting， yes。

 that's the intuition， although under the hood that's not actually， so there's nothing being copied。

 but yeah that is implicitly what's happening here。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_194.png)

Okay， so I'll comment all of this out you can feel free to play around with it but you'll see in other implementations which are more complicated actually have a batch size of more than one there's going to be a lot more broadcasting going on it quickly becomes hard to even keep track of what your like dimensions mean and which dimensions you have to broadcast over so yeah it is something that requires a lot of good with。

And this is why every time you write a new line of code or a new computation。

 you should have some sanity checks to make sure that it's doing what you think it's doing because as you can see here。

 like even broadcasting across the wrong dimension is going to alter your results。

 so you need to be careful and make sure you got everything right。



![](img/1bffdc57c2785e5647c824db2af3396b_196.png)

All right， wow so I've already used 27 minutes， this is proceeding inefficiently as usual。

 but hopefully broadcasting is now clear， so now let's get to a more efficient implementation of attention that is not using this for loop。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_198.png)

![](img/1bffdc57c2785e5647c824db2af3396b_199.png)

![](img/1bffdc57c2785e5647c824db2af3396b_200.png)

![](img/1bffdc57c2785e5647c824db2af3396b_201.png)

Okay， maybe I'll move this out of the loop just to。



![](img/1bffdc57c2785e5647c824db2af3396b_203.png)

I'll put it like down here。Okay。

![](img/1bffdc57c2785e5647c824db2af3396b_205.png)

So now let's go ahead and comment out this part Oh there was a question that I missed。

 can you explain the composed step Yeah， so remember that this is just a simple sentence classification problem so when we do our weighted value vector average we get a different value vector for every position in the sequence so now we have n different vectors and one for each word but we want a single representation of the sentence to pass into our classifier so the compose step is essentially any function that will take a sequence of vectors and produce a single vector so we just use the elementwise mean here。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_207.png)

![](img/1bffdc57c2785e5647c824db2af3396b_208.png)

![](img/1bffdc57c2785e5647c824db2af3396b_209.png)

Okay， so we did our slow version now let's do a efficient。ian computation。

 So I guess I probably will spend less time explaining this， but。

we're going to do our implementation in the dot product attention function which is up here。

 so this function is going to take all of the queries。

 the keys and the values as arguments and were going to compute this attention reps object without any four loops so that's our goal if we can avoid using for loops。

 we take better advantage of the GPU， we try and back possible and avoid loops wherever possible as it just takes better advantage of the GPU's case。



![](img/1bffdc57c2785e5647c824db2af3396b_211.png)

![](img/1bffdc57c2785e5647c824db2af3396b_212.png)

![](img/1bffdc57c2785e5647c824db2af3396b_213.png)

![](img/1bffdc57c2785e5647c824db2af3396b_214.png)

![](img/1bffdc57c2785e5647c824db2af3396b_215.png)

So here， note that all three arguments。Our end by DM matrices。

So we don't have ourqueries as a vector here， and we were looping over our query matrix before。

 but now we're not going to do that。 So the very simple change that we're going to make is。



![](img/1bffdc57c2785e5647c824db2af3396b_217.png)

Back down here， we took a matrix vector product， but here we can just do a simple matrix multiply。



![](img/1bffdc57c2785e5647c824db2af3396b_219.png)

To key matrix and this。

![](img/1bffdc57c2785e5647c824db2af3396b_221.png)

Gets old。Said it was disconnected， hopefully it's reconnected now anyway， so here。

 the high level intuition is essentially we replace these matrix vector products with a single matrix matrix multiply。

 which allowed us to efficiently get all of these dot products at once。

 So this is the important line in this in this code。😊，Okay， hopefully the connection improves。

 and now if we okay， looks like it's back。

![](img/1bffdc57c2785e5647c824db2af3396b_223.png)

![](img/1bffdc57c2785e5647c824db2af3396b_224.png)

If we run this， we see that our loss is still improving and we should make sure that these two things are giving us the same result right so let's take a look at that result right so let's take a look at that just to confirm so I'm going to uncomment the slow solution。

 let's say I'm going to call this attention reps2 and let's just see if。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_226.png)

![](img/1bffdc57c2785e5647c824db2af3396b_227.png)

![](img/1bffdc57c2785e5647c824db2af3396b_228.png)

![](img/1bffdc57c2785e5647c824db2af3396b_229.png)

![](img/1bffdc57c2785e5647c824db2af3396b_230.png)

![](img/1bffdc57c2785e5647c824db2af3396b_231.png)

Print attention reps， oh， these are probably pretty large vectors。

 let's just look at the first element of each。

![](img/1bffdc57c2785e5647c824db2af3396b_233.png)

![](img/1bffdc57c2785e5647c824db2af3396b_234.png)

嗯嗯。Okay， slow attention。

![](img/1bffdc57c2785e5647c824db2af3396b_236.png)

And then。Fast attention。Wops， and this should be attention reps  too。



![](img/1bffdc57c2785e5647c824db2af3396b_238.png)

Zero okay， so hopefully we'll see that these two are this。



![](img/1bffdc57c2785e5647c824db2af3396b_240.png)

It was dumb。嗯。是。Iide doing here， okay？All right， so hopefully we see that these are the same。



![](img/1bffdc57c2785e5647c824db2af3396b_242.png)

![](img/1bffdc57c2785e5647c824db2af3396b_243.png)

And they are the same so this is just showing that these two methods of computing the attention are equivalent and so if you're still a little unsure about these computations。

 you can go back to this code and make sure that you understand what's happening。

 but I do want to switch over now to the text generation example as I think that will show you how to actually efficiently implement the masked self-atten。

 which is something we haven't talked about as of yet。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_245.png)

![](img/1bffdc57c2785e5647c824db2af3396b_246.png)

Okay， so at this point， if you could switch over to the second notebook here。

 the transformer exercise。

![](img/1bffdc57c2785e5647c824db2af3396b_248.png)

![](img/1bffdc57c2785e5647c824db2af3396b_249.png)

Let me make sure it's switched over here。So this in this example we're going to look at a slightly more complicated task so as you can see up above we're going to be giving a network a sequence of characters like A ABB CC DD and we're going ask it to generate the same sequence in reverse order so of course with a very simple vocabulary of like four letters。

 this is going to be a very simple task， but this is actually not a trivial task if you have huge。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_251.png)

![](img/1bffdc57c2785e5647c824db2af3396b_252.png)

Okay， so the goal of this exercise is mainly just to explain the masked self attention and how you can compute it efficiently。



![](img/1bffdc57c2785e5647c824db2af3396b_254.png)

So let's take a look at there's again some scaffolding code here first we are creating a small data set here at least bigger than before 500 examples it would encourage you to actually try this of training on sequences of length 10 and then testing on sequences of length 15 but in this lecture we're just going to focus on the training case yeah it is buffering a lot。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_256.png)

![](img/1bffdc57c2785e5647c824db2af3396b_257.png)

![](img/1bffdc57c2785e5647c824db2af3396b_258.png)

![](img/1bffdc57c2785e5647c824db2af3396b_259.png)

Okay， let me quickly try reducing the video quality， I think I can still do that。Okay。All right。

 hopefully that helps do let me know if it's still not working。



![](img/1bffdc57c2785e5647c824db2af3396b_261.png)

Yes， sorry。 I did try and figure out what was going on with my internet。

 but could not find anything wrong so。

![](img/1bffdc57c2785e5647c824db2af3396b_263.png)

Hopefully it doesn't mess up anymore。Okay， anyway， so here I have a vocabulary of AB C， D。

 E start sequence， end of sequence， note that now that we're doing a generation task we need to have these start at end symbols for the reasons that we discussed in language modeling right we need to know when to conclude the decoding process。

 etc。😊。

![](img/1bffdc57c2785e5647c824db2af3396b_265.png)

And this code essentially is just getting all of our sequences into the correct pytorch format。

 One thing that's important to note here is that we have a sequence to sequence model。

 So we have an encodeder and a decoder。 And when we're doing text generation with a decoder。

 it gets an input at every position， which is kind of the shifted sequence of what it's actually predicting。

 So just to explain what that means。 if I want to reverse this sequence， that's in my training data。

 D E E A E blah， blah， blah， and it ends with the end of sequence symbol。

 I have two different things that I'm interested in with my decoder。

 One is what is the input to the decoder。 And remember during training。

 we're passing in the ground truth sequence into the decoder。 So the first time step。

 the decoder gets the star。😊。

![](img/1bffdc57c2785e5647c824db2af3396b_267.png)

![](img/1bffdc57c2785e5647c824db2af3396b_268.png)

![](img/1bffdc57c2785e5647c824db2af3396b_269.png)

of sequence token and the target is what the decoder is trying to predict。

 So it's trying to predict E， which is the last word of the sequence。

 And then the next input is E to the decoder and it's trying to predict the next word of the sequence。

 which is E and then it gets in the ground truth next word I should say character here。

 and it's trying to predict the next character D here。

 So hopefully you understand the distinction between the input of the encoder and the target。

 you can see that the target is just shifted over by one position So we're not predicting the start of sequence token ever we are only using the start of sequence token as input to our decoder at the first time stuff hopefully that's not confusing at this point。

 but if it is feel free to ask and I can clarify it more。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_271.png)

![](img/1bffdc57c2785e5647c824db2af3396b_272.png)

Okay， so again we have a training loop， I'm not going to go over this。

 you can look at it if you're interested， but it's just computing the cross entropy loss at the sequence level this time。

 so since we're making a prediction at every time step we're going to take the average cross entropy loss at every position of the 500 sequences that we have。



![](img/1bffdc57c2785e5647c824db2af3396b_274.png)

![](img/1bffdc57c2785e5647c824db2af3396b_275.png)

![](img/1bffdc57c2785e5647c824db2af3396b_276.png)

So that's all I want to say about this first cell and all of our work will be in the second cell where we're going to be focusing strictly on the decoder for this task。



![](img/1bffdc57c2785e5647c824db2af3396b_278.png)

![](img/1bffdc57c2785e5647c824db2af3396b_279.png)

![](img/1bffdc57c2785e5647c824db2af3396b_280.png)

Okay， so let's take a look at our init function here where we're going to set up our parameters so we have this is again just a one layer thing we're not looking at multi head attention。

 just single head attention， but all of these are very trivial modifications over this base code base of like efficient mask self attention。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_282.png)

So we have our character embeddings， these are like a substitute for word embeddings。😊。

But here obviously we're not using words， we're using characters and we have position embeddings and so here we're not using the transformer method of the sinusoidal hardcoded embeddings。

 but rather we're just creating another randomly initialized word embedding object embedding object here and I've just arbitrarily made 20 of them so every position from  zero to 20 or 19 I should say is going to be associated with its own word embedding that's going to be learned from scratch this is the same method that Bert uses for its position embeddings。

 it doesn't use the sinusoidal embedding function of the transformer。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_284.png)

![](img/1bffdc57c2785e5647c824db2af3396b_285.png)

Okay， so we have our query key value projections like we did in the previous exercise and we have our softm layer。



![](img/1bffdc57c2785e5647c824db2af3396b_287.png)

![](img/1bffdc57c2785e5647c824db2af3396b_288.png)

Okay， so here I've also copied in some of the code from before， we have our dumb slow attention。

 which is what was in the for loop from the previous exercise。

 so this assumes that your query is a single vector Q and your keys and values are matrices。



![](img/1bffdc57c2785e5647c824db2af3396b_290.png)

![](img/1bffdc57c2785e5647c824db2af3396b_291.png)

![](img/1bffdc57c2785e5647c824db2af3396b_292.png)

We have our fast efficient version of this， which we call smart unmaskked attention。

 which is doing the same。

![](img/1bffdc57c2785e5647c824db2af3396b_294.png)

The same computation as we saw in the Dot product attention function。



![](img/1bffdc57c2785e5647c824db2af3396b_296.png)

So here theque， this is going to be used for our source attention。

 where the keys and values are going to come from the encoder and the queries are going to come from the decoder。



![](img/1bffdc57c2785e5647c824db2af3396b_298.png)

So with that we get the scores of the and then what we're going to be implementing here is the mask attention。

 which is going to be used for target side self attention in the decoder。

 so that's what we're going to focus most of our time on implementing。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_300.png)

![](img/1bffdc57c2785e5647c824db2af3396b_301.png)

![](img/1bffdc57c2785e5647c824db2af3396b_302.png)

Okay， so let's go through this forward function just to see what scaffolding code is already here。

 Our input here is now no longer。😊。

![](img/1bffdc57c2785e5647c824db2af3396b_304.png)

![](img/1bffdc57c2785e5647c824db2af3396b_305.png)

Well， let's take a look at the input just to see what it looks like。



![](img/1bffdc57c2785e5647c824db2af3396b_307.png)

![](img/1bffdc57c2785e5647c824db2af3396b_308.png)

So it's a single sequence as before and the first dimension is going to be the batch size。

 the second dimension is going to be the length of that sequence。

 which in our first cell we set to 10， all of our training examples are going to have length 10。

 these are all 1，2，3，45，67，8910 character long sequences。



![](img/1bffdc57c2785e5647c824db2af3396b_310.png)

![](img/1bffdc57c2785e5647c824db2af3396b_311.png)

![](img/1bffdc57c2785e5647c824db2af3396b_312.png)

![](img/1bffdc57c2785e5647c824db2af3396b_313.png)

Okay， so we get this thing as input and we first are going to get get the position embeddings for each of those 10 positions so that's in this pausems object and we're going to take the character embeddings associated with the input and the first thing we do is add the position embeddings to those character embedding so this is again what is happening in the transformer and so for the encoder I didn't want to focus on this at all because it's not important So we're just going to do the value projection and assume that those are the output here of course you would want to so exercise to try at home implement self attention for encoder this should be very straightforward actually if we have time at the end we can do this but the mass。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_315.png)

![](img/1bffdc57c2785e5647c824db2af3396b_316.png)

![](img/1bffdc57c2785e5647c824db2af3396b_317.png)

![](img/1bffdc57c2785e5647c824db2af3396b_318.png)

![](img/1bffdc57c2785e5647c824db2af3396b_319.png)

![](img/1bffdc57c2785e5647c824db2af3396b_320.png)

![](img/1bffdc57c2785e5647c824db2af3396b_321.png)

![](img/1bffdc57c2785e5647c824db2af3396b_322.png)

Self attention only happens at the decoder， so we're going to focus on that。



![](img/1bffdc57c2785e5647c824db2af3396b_324.png)

So for the decoder， we do the same thing that we did before we get the character embeddings associated with the decoder inputs。

 which is。😊，Confusingly named outputs here。 Maybe I should。



![](img/1bffdc57c2785e5647c824db2af3396b_326.png)

Rename this。

![](img/1bffdc57c2785e5647c824db2af3396b_328.png)

To decoder inputs to be more consistent with the thing that I printed above。

 we're going to add the position embeddings to these。

 the same set of position embeddings and then project to query key and value。



![](img/1bffdc57c2785e5647c824db2af3396b_330.png)

So this is where we start and now the first thing that we want to do is compute the self attention on the decoder side。

So remember that this is not as trivial as what we saw in the previous exercise because we want to avoid cheating right。

 we don't want the attention weighted average to include value vectors that occur at time steps that we're not currently at yet right because we don't want information about what comes in the future to influence our network。

 otherwise it can easily figure out you know what it needs to predict。



![](img/1bffdc57c2785e5647c824db2af3396b_332.png)

So okay， how do we get started again， just like before。

 we're going to start with an inefficient solution which hopefully makes it clear currently what we're doing and then we're going to look at a vectorized solution。

So to start with， I'll make an object called decoder states， I'm going to initialize this to。Co。

Max1 by the hidden dimensionality。

![](img/1bffdc57c2785e5647c824db2af3396b_334.png)

And I'm going to store each attention weighted average corresponding to each decoder time step in this decoder states matrix。



![](img/1bffdc57c2785e5647c824db2af3396b_336.png)

Okay。So we can consider this N by D Hi， of course。 And now we're going to do our standard looping based solution here。

 So for。

![](img/1bffdc57c2785e5647c824db2af3396b_338.png)

![](img/1bffdc57c2785e5647c824db2af3396b_339.png)

H。We're going to loop over every time step in the decoder and now it's not as simple as what we saw before where we can just get use all of the keys and all of the values to do this computation here we actually have to slice our keys and values to account for the current position we're at because we don't want to cheat。

😊，So I'm going to create a new variable calledPrevious keys。



![](img/1bffdc57c2785e5647c824db2af3396b_341.png)

And I'm going to take the decoder keys。 This is， of course， target side， self attention。

 Maybe I'll make that clear here， targetrget side。

![](img/1bffdc57c2785e5647c824db2af3396b_343.png)

![](img/1bffdc57c2785e5647c824db2af3396b_344.png)

Self attention in decoder。So the keys and values are just the previous hidden states in the decoder。

And so I don't want to use keys that occur in the future。

 so I'm going to go from zero to the current time step so if I go to I+1 that's going to include the current time step。

 which I do want to include in my self attention computation。

I'm going to do the same thing for the values。So I'm just writing out the zero to be more clear。

 of course you don't have to include it in practice， so this is going to include all keys。

Up to and including the current time step。

![](img/1bffdc57c2785e5647c824db2af3396b_346.png)

Z。And keys here is of course， referring to these decoder keys。All right。

 and the same thing with the values。

![](img/1bffdc57c2785e5647c824db2af3396b_348.png)

So an interesting thing here is that this， the shape of this previous keys and values is going to change as we increase the position that we're at in the decoder。

 So let's make this more clear。 I'll just print the size of this previous keys object。

 and hopefully that'll make it more clear what's actually going on in this。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_350.png)

![](img/1bffdc57c2785e5647c824db2af3396b_351.png)

![](img/1bffdc57c2785e5647c824db2af3396b_352.png)

![](img/1bffdc57c2785e5647c824db2af3396b_353.png)

So you can see that at the first time step I'm only allowed to look at the current key right everything else is in the future so it's cheating to look at it。

 so I have a key matrix of size1 by 50 in the next time step I'm now allowed to look at two things in the next time step I can look at three things four or five up until the final time step where I can look at everything。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_355.png)

So hopefully this is clear， I'm using a different number of keys every time to avoid looking at things in the future that's the the critical thing to take away from this if you don't remember anything else about this exercise。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_357.png)

![](img/1bffdc57c2785e5647c824db2af3396b_358.png)

Oh no， quality is bad。呃。Perhaps I should have recorded this beforehand and uploaded it。

Sorry about these issues。Okay， so it looks like I'm not connected。It comes back soon。Okay。

Looks like it's back， here's my。All right， so it seems to be better now。Okay， so we have the。

These this variable length of keys and values due to the the ever increasing time step of our decoder。

 so hopefully that makes sense。 and now we can just apply our do slow self attention that we already computed or implemented in the previous exercise for this so I can do self do slow attention And remember this takes the current query that we're at so Dqueries I and it takes my previous keys and previous values as the keys and values。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_360.png)

![](img/1bffdc57c2785e5647c824db2af3396b_361.png)

And then I'm going to put this into my decoder states matrix。



![](img/1bffdc57c2785e5647c824db2af3396b_363.png)

At position I。

![](img/1bffdc57c2785e5647c824db2af3396b_365.png)

Okay。I mean， I could have just made this one line。And was done。



![](img/1bffdc57c2785e5647c824db2af3396b_367.png)

Okay。So this is with the loop。

![](img/1bffdc57c2785e5647c824db2af3396b_369.png)

And now I will'll go back to the efficient computation with the mask in a little bit。

 I want to just finish up this coding block and get to a point where we can train this network even with this dumb。

 slow attention ISP like Xfinity has really low upload bandwidth with。 Yeah， I'm on a spectrum。

 I don't think it's great either。😊，Anyway， so let's implement the source attention as well。

 this is pretty straightforward。😊。

![](img/1bffdc57c2785e5647c824db2af3396b_371.png)

嗯。Let's do source attention we can do this just using our smart smart unmask attention function because remember in the source attention we don't have any issue with cheating we already have all of the information about our encoders or representations Those don't depend on the current time step of the decoder so I can do this by。



![](img/1bffdc57c2785e5647c824db2af3396b_373.png)

![](img/1bffdc57c2785e5647c824db2af3396b_374.png)

![](img/1bffdc57c2785e5647c824db2af3396b_375.png)

![](img/1bffdc57c2785e5647c824db2af3396b_376.png)

What did I call the source attention equals？嗯。So now we're going to use our smart unmasked attention。

 we haven't yet implemented the masked attention， and this takes in as input the queries from the decoder side and then the keys and values from the encoder side。

Quries come from decoder， Ps values。From encoder so again。

 this is this should be easy to understand based on all of our prior discussions of the source attention in transformers。

 we want some connection between the encoder and decoder and this is what gives it to us。😊。

So now we have these two things， we have the decoder self attention。



![](img/1bffdc57c2785e5647c824db2af3396b_378.png)

Okay， sorry， it disconnected again， I was just saying that in the transformer。

 we don't actually use the query embeddings for the source attention。

 but we instead use the output of the decoder self- attention。

 which in this case is this decoder states variable。



![](img/1bffdc57c2785e5647c824db2af3396b_380.png)

![](img/1bffdc57c2785e5647c824db2af3396b_381.png)

So this gives you a more contextualized representation of the decoder embeddings。Okay， oh， great。

 I'm not connected again。Okay， it looks like I'm somewhat connected now。

So now let's go ahead and combine these two representations。

This is also pretty straightforward all we do is just add them together so really nothing fancy here。

Let's go ahead and print the size of these just to make it more clear。



![](img/1bffdc57c2785e5647c824db2af3396b_383.png)

嗯。

![](img/1bffdc57c2785e5647c824db2af3396b_385.png)

Decoder states dot size， source attention dot size。 So these should both be the same size。

 which will yeah， so I get for both of these an 11 by 50 matrix or each row corresponds to either the source attention representation at that position or the self attention representation of that position And in the transformer to combine the input from the source attention and the self attention。

 you just add sorry， you just add these two representation。 So。



![](img/1bffdc57c2785e5647c824db2af3396b_387.png)

![](img/1bffdc57c2785e5647c824db2af3396b_388.png)

![](img/1bffdc57c2785e5647c824db2af3396b_389.png)

![](img/1bffdc57c2785e5647c824db2af3396b_390.png)

Combine decoder self attention with source attention。 We're just going to add them。

 So I'll just keep it in the source attention variable。Plus， decoder states。Okay。

 so now that we've computed both self attention and source attention。

 the scaffolding code will do the prediction in the softmax layer。

 one little thing that is not super important an implementation thing is that for the softm we're going to reshape all of the the source attention hidden states into。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_392.png)

![](img/1bffdc57c2785e5647c824db2af3396b_393.png)

![](img/1bffdc57c2785e5647c824db2af3396b_394.png)

I mean， this is relevant only if you have a batch size of more than one。

 but we basically flatten out the first two dimensions。

 so the matrix is of size batch size times sequence length by hidden dimensionality again。

 is not this is not relevant for this example since we have batch size of one。

 but if you want to experiment with larger batch sizes this is important just for the way in which ptorrch deals with the softmax。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_396.png)

Okay， so let's see if this works， please work。

![](img/1bffdc57c2785e5647c824db2af3396b_398.png)

Okay， cool， so the loss is going down and that indicates that our network is successfully learning this sequence reversal on the training data。



![](img/1bffdc57c2785e5647c824db2af3396b_400.png)

![](img/1bffdc57c2785e5647c824db2af3396b_401.png)

![](img/1bffdc57c2785e5647c824db2af3396b_402.png)

Okay， so now just to get back to the most important part of this exercise。

 which is how do we make this faster？

![](img/1bffdc57c2785e5647c824db2af3396b_404.png)

![](img/1bffdc57c2785e5647c824db2af3396b_405.png)

嗯。Okay， so。How can we compute decoder self attention faster？

We can't just use smart unmaskked attention， right because the mask is required to prevent us from cheating。

So as before， we're going to do all of our code in the function up here。

 where's smart mask attention， so let me call this fast decoder states。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_407.png)

![](img/1bffdc57c2785e5647c824db2af3396b_408.png)

![](img/1bffdc57c2785e5647c824db2af3396b_409.png)

Cool self。mart。Maskked attention and this is going to take in my queries， my keys。

 and my values as inputs。

![](img/1bffdc57c2785e5647c824db2af3396b_411.png)

Okay， so that's great and now let's take a look at how we actually implement this。嗯。All right。

 so just like in the smart unmased attention， we're going to be taking advantage of the matrix product between the query matrix and the key matrix。

 but we want to first apply a mask to the key matrix and the value matrix before we actually do this。

So how do we actually do this first let's get the size of our query matrix again so we we basically just want the max length。

😊，And this is going to define our mask。 And so remember， we went over how this mask looks。 right。

 It's this lower triangular matrix where we essentially want to be revealing only up to and including the time step that we're currently at。

 So Pytorch provides this nice function。😊，callled Tri or trial or whatever you want to call it that will give you the lower triangular part of an input matrix。

 so it's going to set all of the upper elements in the upper triangle to I think zero we will see here。

So to get all of the lower triangular elements to be one， I'm going to put in as input。呃嗯。

A maxlen by maxlin matrix。 This is one too many parentheses。 So let's take a look at how。This looks。



![](img/1bffdc57c2785e5647c824db2af3396b_413.png)

So if you look at this matrix that was printed out。

 you see that this is actually exactly what we want and we can compare this to the output of the floor loop。

 which was showing us we had an increasing dimensionality of keys at each time step you can view each row of this matrix is corresponding to one time step and which keys need to be masked at this time step and which keys need to be unmasked。

😊，So our mask is this matrix where the lower triangular elements are set to1 and the upper triangular ones are set to zero。

 although we'll see that we need to change the zeros in a bit to be compatible with our softmax。



![](img/1bffdc57c2785e5647c824db2af3396b_415.png)

Okay， so we have our mask， hopefully that makes sense why we're doing this， if not， as usual。

 write a question。And so now what we're going to do is we're not going to use the mask directly to mask out the unnormalized scores。

 but we're going to apply this at the Sonax。 So I'm going to just copy this code from the。

And so this is going to get all unmasked dot products at once。



![](img/1bffdc57c2785e5647c824db2af3396b_417.png)

But now I'm going to apply this pytorrch method called maskked fill， which。

Is going to fill in every part of the scores matrix where the mask at the corresponding position is and again。

 this is the same dimensionality as the mask， which is why we can do this。



![](img/1bffdc57c2785e5647c824db2af3396b_419.png)

![](img/1bffdc57c2785e5647c824db2af3396b_420.png)

So maskask fill lets you set the value of any element that where the mask has a particular value to a specific number。

 so here our mask has where we want to change this as where the mask is zero。

 we want to set this to some very， very low negative number。

 close to negative infinity because this is going to allow us after we apply the softmax to get these elements to something close to zero。

😊，So I'm going to use sorry to negative infinity， if my bad not。Yeah。

 I think that's what I said Okay， so some very negative number。

 which is going to let us after the softm， which I can also copy from up here。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_422.png)

It's going to set all of the scores where the mask is zero to zero after the softmax。😊。

And let's take a look at this just to make sure it works。



![](img/1bffdc57c2785e5647c824db2af3396b_424.png)

Okay， so it's kind of messy， but you can see that for the very first sequence it put 100% of the probability in the first key and0 on every other key。

 so this is exactly what we want right for the second sequence here our second time step。

 66% probability on the first time steps， hidden state 34% on the second and0 everywhere else。😊。

For the third time step， I guess it decided to put all of its probability mass on the third time step。

 but you can see that this has worked right the mask is successfully constraining the keys that we don't want to influence this distribution to0。

 which means that when we take the value attention weighted average of the value vectors since the score is0 for all of these value vectors。

 they're not going to come up in the weighted average。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_426.png)

![](img/1bffdc57c2785e5647c824db2af3396b_427.png)

![](img/1bffdc57c2785e5647c824db2af3396b_428.png)

So hopefully that makes sense。嗯。😊，And so finally I can just。Return this。

 So there's not much difference between。These two functions。

 the key difference is with first creating this mask and again。

 this is something that you could likely cache in your init function if you're going to have the same length inputs at all times like we do in this trivial case。

 if you're going to have variable length inputs， then you probably don't want to do this and you probably want to initialize it in the self attention computation itself and then the mask fill part is important because we're applying the softm so we can't just elementwise multiply mask with scores here。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_430.png)

And you should also think about why we can't just take the softms of the unmask dot products and then mask the resulting scores。

 So actually I can show you this， although I don't want to waste too much time but we're already way over so let me just show you what happens if you do the other approach。

😊，So we have our unorized scores。 We're going to get rid of this mask filling。

 and we're just going to multiply the scores with the mask。 So what happens here and this should。



![](img/1bffdc57c2785e5647c824db2af3396b_432.png)

Tell you。Whoops。

![](img/1bffdc57c2785e5647c824db2af3396b_434.png)

So we see the issue here。If we do this without， if we multiply the mask with the scores after the softm。

 we don't get well formed probability distributions， right。

 because that the original distribution had sum to 1。 Now we're masking out all of the elements。

 except the first one， but the first element was0 in the original。

In the original softmax distribution。 so when I apply this mask。

 I just get a vector of all zeros in the second time step here。

 I'm only allowed to look at the first and second time step。

 and there's probability of 2% on the second time step， but there's zero probability everywhere else。

 So you can see that this is not the way to implement the mask self attention。

 This is why we need to compute the softmax only after we do the masking。😊。



![](img/1bffdc57c2785e5647c824db2af3396b_436.png)

U。Okay， so。

![](img/1bffdc57c2785e5647c824db2af3396b_438.png)

嗯。Yeah， I think this should do， so this is the correct version。



![](img/1bffdc57c2785e5647c824db2af3396b_440.png)

Alright， so we've implemented the fast version of the masked self attention。 And now let's just。



![](img/1bffdc57c2785e5647c824db2af3396b_442.png)

![](img/1bffdc57c2785e5647c824db2af3396b_443.png)

Okay。

![](img/1bffdc57c2785e5647c824db2af3396b_445.png)

I'm a little confused on the time step。 Can you explain it again。

 Could you clarify what you mean by the time step？So just as a refresher。

 the decoder in this text generation setup is producing a single word at a time right。

 so one time step corresponds to if we go back up here to our data at one time step at the first time step I get my decoder as input gets the start of sequence token is input and is asked to predict D。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_447.png)

And so of course， at training time， I have access to the full ground truth sequence so I can parallelize all of these computations。

 but I need to ensure that at the first time step， I'm only looking at the key associated with the start of sequence position and none of the keys associated with any of these other time steps because those are actually what I want to predict in the future。

 so that's the intuition， let me know if that wasn't actually what you were asking and I can clarify further。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_449.png)

![](img/1bffdc57c2785e5647c824db2af3396b_450.png)

But I wanted to wrap up here with a kind of timing experiment just to motivate why we want to do this fast。

 vectorized operation as opposed to the for loop version。So to do this， oh， and before we do that。

 let's just again make sure that these two things are equivalent。 So decoder states。

 maybe I'll call this slow decoder states and fast decoder states Are these two things equivalent we will shortly see。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_452.png)

![](img/1bffdc57c2785e5647c824db2af3396b_453.png)

![](img/1bffdc57c2785e5647c824db2af3396b_454.png)

Let's just print out the very first time steps。

![](img/1bffdc57c2785e5647c824db2af3396b_456.png)

嗯。

![](img/1bffdc57c2785e5647c824db2af3396b_458.png)

Representation。Just see if they match。

![](img/1bffdc57c2785e5647c824db2af3396b_460.png)

And yeah， they look pretty equivalent here。 So the embedding hidden dimensionality here is larger than before。

 But you can see that these are identical。 So the fast and slow versions are doing the same thing。

 Now， let's in the last few minutes， go ahead and time these and see if the slow one is actually slower than the。



![](img/1bffdc57c2785e5647c824db2af3396b_462.png)

![](img/1bffdc57c2785e5647c824db2af3396b_463.png)

![](img/1bffdc57c2785e5647c824db2af3396b_464.png)

Pa one。So we're going to just use the Pytorch time sorry Python time function。

 there are better ways of doing this timing there are libraries that you can use that probably account for various confounding factors but。



![](img/1bffdc57c2785e5647c824db2af3396b_466.png)

![](img/1bffdc57c2785e5647c824db2af3396b_467.png)

![](img/1bffdc57c2785e5647c824db2af3396b_468.png)

![](img/1bffdc57c2785e5647c824db2af3396b_469.png)

This is a。Decent way of doing this。 Oh， and I should say。



![](img/1bffdc57c2785e5647c824db2af3396b_471.png)

嗯。Time equals time dot time and smart time equals time dot time minus。

Start time Okay so basically I'm just timing everything that happens within these two timing calls this is a little harder to do when we're on the GPU。

 although right now we're on the CPU there's some possible synchronization issues。

 but this should be fine for now。

![](img/1bffdc57c2785e5647c824db2af3396b_473.png)

![](img/1bffdc57c2785e5647c824db2af3396b_474.png)

![](img/1bffdc57c2785e5647c824db2af3396b_475.png)

![](img/1bffdc57c2785e5647c824db2af3396b_476.png)

So okay， I want to print out the。Time difference， so let's。Let do this dumb time。

I see that I'm not connected， this is probably a good time to write this print statement。嗯。Yeah。

 it should be fine。And。呃。Should。I don't know what level of precision I should。Use here。But。



![](img/1bffdc57c2785e5647c824db2af3396b_478.png)

Yeah， let's see what happens here， See we haven't made any dumb errors。



![](img/1bffdc57c2785e5647c824db2af3396b_480.png)

All right， so our dumb time took， so this was the one with the  four loop took 0。0 seconds。

 I believe it's in seconds to do this computation， whereas the smart one that was fully vectorized took an order of magnitude less time so you can see that there are big benefits from parallelzizing this computation。



![](img/1bffdc57c2785e5647c824db2af3396b_482.png)

![](img/1bffdc57c2785e5647c824db2af3396b_483.png)

![](img/1bffdc57c2785e5647c824db2af3396b_484.png)

And I should also mention that an LSTM has to operate in this format where you loop over every time step in the decoder because the representation at time step T depends on the representation at time step T minus1 so again。

 this is one of the examples of why transformers are preferred over recurrent neural networks for these kinds of text generation applications because we can parallelize entirely the decoders computations at training time and we can't do this with masked computation with a recurrent neural network。



![](img/1bffdc57c2785e5647c824db2af3396b_486.png)

U。Okay， so I guess that's。

![](img/1bffdc57c2785e5647c824db2af3396b_488.png)

All I wanted to show oops， let's just make sure that we can train this network again。嗯。



![](img/1bffdc57c2785e5647c824db2af3396b_490.png)

So we'll use the fast decoder states here。Oh my god。



![](img/1bffdc57c2785e5647c824db2af3396b_492.png)

Next， decoder states。All right， so this is just printing out the time difference for every example in training and you can see that the loss slowly goes down to under one with more training it would certainly go down even lower than that。



![](img/1bffdc57c2785e5647c824db2af3396b_494.png)

![](img/1bffdc57c2785e5647c824db2af3396b_495.png)

All right， so I know we didn't implement a full transformer here to implement a full transformer。

 you would have to， first of all， make your encoder a real thing and not just a bunch of embeddings。

 second of all you would want to make these attention computations。

 use multiheads instead of just a single head。 This is a straightforward modification where you can do all of this with a single matrix product instead of looping over your heads Again。

 you want to avoid loops in your code whenever possible。

 so you don't have to do that for adding multiple heads。 third， we of course。

 have some feed forward layers from the transformer block that we missing。

 we also have dropout and layer normalization and residual connections between the layers that are missing and you should feel free to add all of those things to this this example if you want。

😊。

![](img/1bffdc57c2785e5647c824db2af3396b_497.png)

![](img/1bffdc57c2785e5647c824db2af3396b_498.png)

![](img/1bffdc57c2785e5647c824db2af3396b_499.png)

![](img/1bffdc57c2785e5647c824db2af3396b_500.png)

![](img/1bffdc57c2785e5647c824db2af3396b_501.png)

![](img/1bffdc57c2785e5647c824db2af3396b_502.png)

![](img/1bffdc57c2785e5647c824db2af3396b_503.png)

The critical component of the transformer and the thing that you need to make sure you understand is how this masked self attention works in the decoder and how we're able to parallelize across the entire sequence without looping through it。



![](img/1bffdc57c2785e5647c824db2af3396b_505.png)

![](img/1bffdc57c2785e5647c824db2af3396b_506.png)

Okay， so that's it for next time we'll be talking about applications of vision and language so like multimodal tasks with a focus on navigation because it should be pretty interesting and see you then。



![](img/1bffdc57c2785e5647c824db2af3396b_508.png)
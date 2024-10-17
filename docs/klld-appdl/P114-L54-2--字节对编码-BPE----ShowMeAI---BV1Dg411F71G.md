# P114：L54.2- 字节对编码（BPE） - ShowMeAI - BV1Dg411F71G

The next paper is going to deal with the next problem that we saw that the more unknown words that you have in your translation。

 the quality of your translation goes down， the blue score goes down and the reference is wrong so don't worry about that I'm going to fix that but there is byte pair encoding and this was the second speaker in our colloquium who introduce this method and it's now taking off and you're going to see why it's a very easy method for pre-processing your sentences and creating your subword units so what is a byte pair encoding it's an old algorithm。

 it's a data compression technique and how do you how do you use it you iteratively replace the most frequent pairs of words or pairs of byte in a sequence with a single unused byte but what is a byte a byte in the context of natural language processing or translation is going be a character。



![](img/8180bfe6a9e9bf5f58c1be893aad1086_1.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_2.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_3.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_4.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_5.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_6.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_7.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_8.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_9.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_10.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_11.png)

or a bunch of character sequences so youre merg characters to form your words so your words don't necessarily need to have any meaning as long as they are useful you can use them for translation so let's see I'm going introduce the algorithm using an example and the example is this maybe this is your data set maybe this is your dictionary in your dictionary you have low lower newest and widest and you want to process that dictionary and come up with your byte pair encodient sequences。

 This is the algorithm So this is a good exercise you can just copy and paste than algorithm in Python and just run it and it's going to give you byte pair encoding so that's the algorithm it's very simple and beautiful it's elegant the algorithm So what is it actually doing in the face of an example this example in particular let's say this is your dictionary and the number of times。



![](img/8180bfe6a9e9bf5f58c1be893aad1086_13.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_14.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_15.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_16.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_17.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_18.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_19.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_20.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_21.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_22.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_23.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_24.png)

That the word low appeared in your dictionary is five times。

 the number of times that the word lower appeared in your corpus is two times。

 The number of times that Uest appeared is six times and y does is three times。

 You're going to add spaces between them。 and then that's the end of the word symbol。

 So you're just going to add them。

![](img/8180bfe6a9e9bf5f58c1be893aad1086_26.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_27.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_28.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_29.png)

And then what we are going to do is going to go through pairs of words pairs of sorry characters so we are going to go through pairs of characters and count the number of times that you are appearing let's count L L is appearing five times here L is appearing two times here so seven in total and then that's it so L is7 then youre going to go through maybe let's say E there is no E here no E here there is ES here E is appearing six times and there is another ES here it's appearing three times6 plus three is going to give you nine so9 is bigger than seven and this turns out to be more frequent than L and it's actually the most frequent pairs of words pairs of characters in your corpus because that's the most frequent one you're gonna to pick that and merge it so L is the same this word is the same then new S。



![](img/8180bfe6a9e9bf5f58c1be893aad1086_31.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_32.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_33.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_34.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_35.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_36.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_37.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_38.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_39.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_40.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_41.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_42.png)

ES you merged it。 There is another E you merge that。

 Now we go we go ahead and do the same exercise again。 LO。

 we know that it's gonna appear seven times so we don't worry about that。

 You do the same exercise for other pairs of characters or character sequences and now let's take a look at E and T So E and T is appearing six times here。

 pair of E and T is appearing nine times6 plus sorry ET is appearing six times EST is appearing three times6 plus three is99 is bigger than the rest of these pairs。

 We're gonna choose that pair of character or pair of bys and merge them So you're gonna merge it here You're gonna merge it here and then you can you keep doing the same exercise。

 Now the most frequent one is E and the end of the word So you're gonna merge them。

 You have L O is the next most frequent one。 you merge them L。



![](img/8180bfe6a9e9bf5f58c1be893aad1086_44.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_45.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_46.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_47.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_48.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_49.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_50.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_51.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_52.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_53.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_54.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_55.png)

LO and then there is LW and then you keep doing that until a hyperparameter that you choose so this is the number of iterations that you're willing to pay okay how many rounds。

 how many merges you're going to willing to do you're going to be willing to do okay so that's a hyperparameter that you choose but once you do that in the end you're going to end up with your dictionary it's your new dictionary some of them makes sense it's low it has a meaning then you have low ER end of word newest and white。



![](img/8180bfe6a9e9bf5f58c1be893aad1086_57.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_58.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_59.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_60.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_61.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_62.png)

Now the rest of it is that you're gonna do word embedding these are gonna be your words okay low is your word low E end of word is your words etc。

 this is your new dictionary now and you can do word embedding on that okay perfect the question is what happens during testing if we see a new word how we' going to merge that word or how we're going to decompose it and then merge it back so at test time you have an outof vocabulary word so you have a word that is out of this vocabulary maybe lowest lowest is outside of this vocabulary so whatever are you going to do you're going to do the same operations on lowest so you're going to score these operations that you are doing during training you're going to store that actually during this algorithm you're going to store that and then during testing you just apply that rule first of all you're going merge ENS so you're going merge ENS then you're gonna。



![](img/8180bfe6a9e9bf5f58c1be893aad1086_64.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_65.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_66.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_67.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_68.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_69.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_70.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_71.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_72.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_73.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_74.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_75.png)

Mge EST and then you're going merge LO and then you're going to merge LW and that's going to give you two segments and these two segments are now part of your dictionary see low is here this is part of your dictionary and EST end of word is also part of your dictionary and then you can just merge them so what is the effect what is the big picture now you can have character level language models you can have word level language models and you can have by pair encoded models for your words let's see what happens。



![](img/8180bfe6a9e9bf5f58c1be893aad1086_77.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_78.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_79.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_80.png)

![](img/8180bfe6a9e9bf5f58c1be893aad1086_81.png)

If you do if you only have a corpus and you do nothing at that corpus so whenever you have a space you're going to separate out your words and you do nothing you're going to end up with 100 million tokens and this is the number of this is the sequence length of your entire corpus you can treat your entire corpus as one long sequence this is a number of tokens it's going to be 100 million and then you're going to have a lot of vocabulary it's going to be 1750 words in your dictionary and this is crazy okay and you're going end up with some unknown words if you do character level you're going to have much fewer characters in your dictionary it's going to be 3000 but then you're going to have a very long sequence length so this is going to explode in terms of the sequence length then there are some other。

mitigation frameworks like maybe use character diagramgrams。

 character trigrams etc These are some techniques from before so we don't worry about them let's see by pair encoding and it's going to do a balance between the tradeoff between tokenken length and the number of token the number of types that you're gonna have your vocabulary size so this is reasonable is' going to give you 63000 words for your dictionary size and the number of tokens in your corpus is not going to explode unlike character sentence character modeling and you can actually do joint pairs of languages you can have English and French and then you can do by pair encoding for the joint you're gonna to end up with some unknown words that's okay but it's not that bad it's 32 of them and the size of your vocabulary is not that crazy and the size of your sequence length is not that crazy also but this is impressive that you're going to end up with0。

words when you do bike pair encoding well is the effect let's see some examples。

 this is your source sentence， this is your reference sentence， if you do by pair encoding。

 it's going to decompose Gazung Hes for Sungs insa to Gezung Hes for in10 but then if you do more iterations。

 it's going to make more sense same thing here for other examples， this is for German。

 this is for Russian。I guess I'm gonna stop here and for those of you who want to leave you can leave and for those of you who have questions and want to stay and ask I'll be around I've got two questions ones easy the the 60k and the 90k is that just the number of merges that parameter you're talking about I guess this 60k and 90k they have something to do with this but then this is a function of the number of iterations that you do the number of merges Yeah and then the number of unknown words that is on some other like like do have you have I guess like a two different corpes and you do the by pair encoding training on one corpus and then read through the other one and see how many words are still unknown？

So usually when you do these types of models like word models， word level models。

 you're gonna to set aside and unknown token for whatever that is unknown maybe during testing or even maybe during training and then you actually have a word vector for unknown but here by unknown this would have been an unknown lowest it's not part of your dictionary so that's going to belong to the category of unknowns but this is no longer unknown because you're decomposing it into lowest and S into low and S and then it's not going to be treated as an unknown I guess my question is how can we have anything that's unknown if we're building our dictionary from reading through a corpus and keeping track of everything that's in there unless you have an a budget of whatever size that you want I mean if you're really？

To pay the vocabulary size to be infinity then yes。

 you are not going to have any unknowns Even then you're building your vocabulary or your dictionary from a corpus maybe from your training corpus but then during testing there is gonna to be some unknowns regardless of how big your dictionaries and then there is another hyperparameter that you usually set the size of your dictionary it cannot be infinity。

 you cannot it's not doable So that's that's why there's unknowns in these cases that theyre they're doing some kind of training set or training corpus and then doing a test set and there's unknowns and the test you always have that even if you have even if you escape scrape the entire internet you you are going to end up with an algorithm that you want to take it into production and in production there are going to be some new words that you have never seen。

It's not a matter of mathematical observation that you have training testing and validation this is actually a real problem there is going to be unknown in production time okay and testing is just supposed to simulate what you're what's going to happen to your algorithm in reality in real life Lucas I had another question but if you want to jump in I don't want to hold you up No I say I was just listening curious the last question I had is how do you break potential ties or ambiguities like I'm guessing there's a lot of words where you can break it up into multiple different subbytes and is that done then with that ranking you were talking about like the most the most common the most frequent bytes are the ones that are used first when then breaking up a word so during the learning phase of by encoding this is exactly what is happening so what what are you learning during B pair encoding。

You're learning what to marriage and the order of marriages So you first always marriage ES and then EST then EST and of word got it and these guys you're gonna store and there is only one way that you're gonna merge lowest and that's it yeah there is no other way to merge it and that's why byberry encoding is beautiful it is beautiful than it's taking off that makes sense people are using it right and left because it is powerful it's simple powerful so given given a new word you just follow that list of instructions from the top to the bottom Yes that makes sense and is this is you're achieving your objective function that you can have open vocabulary when you have zero unknowns it's like character level models but much less tokens and probably also some power that the bys themselves are meaningful like you were saying with like breaking down the German word Yes see。

This happens a lot in German， you're going to have a lot of these types of words that are being created out of other words。

You can actually see a sentence within a German word this is crazy yeah it is cool All right。

 thank you for your time yeah sure。
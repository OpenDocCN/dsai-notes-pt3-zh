# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P57：L11.1- Python中的Spacy入门 - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Heaton welcome to applications of deep neural networkss with Washington University Now we're going to start a look at natural language processing with Cars in particular we're going to begin by looking at some tools that help us preproces the data to the neural network we're going to talk about Space for the latest on AI course and bell notified of are primary deal natural language processing neural is dealing characterrate stories Tsure Island basically LS of it reproduces that the second way that you can deal with it is on the word level and we dealt with it on the word level for the captioning really you can make both techniques any type of problem Word level NLP can be good because。



![](img/ff26651c6e28d6ee53469ef48ed52d86_1.png)

You can use additional libraries available to you in Python to actually process those words before they go into the actual neural network。

 characteract level has its advantages because you're not doing that because you're letting the neural network actually figure out all of the things about English suffixes prefixes all these grammatical type expression。

 Some techniques are better for others。 The more historic method for natural language processing was heavy grammatical analysis。

 The more modern and newer techniques are pretty much end to end where the neural networks operate on the raw text directly。

 However， you still will sometimes do some processing at the word level。

 So we're going to see how to use some of the python packages to work with the actual words that are in your text before you actually send them on the neural network。

 As far as natural language processing libraries available for Python I mean other than Tensorflow there are several but。

Two of the ones that I've seen particularly stand out in Caagle competitions and related literature to this are NLTK and Spacey。

 NLTK was around for longer than Spacey。 It's been used for quite some time。

 I've used both of these at this point， I prefer spacey。

 and that's the one that we will be using for the class。

 It's a little more object oriented and object oriented in a good way。 believe me。

 there can be objectoriented in a bad way， meaning that it literally transforms the words into individual objects that give you a fair amount of information about these individual words。

 Now， installing spacey， it should have already been installed when you went through in module1 and did all the Pip installs that I gave you for this class。

 Spacey was one of the packages that I specify that you should install。 However。

 if you just install Spacey， it won't work。 It needs a lexicon dictionary。

 And I'll suggest that you install the English one for this class because that's what we're using。

 if you haven't。Stall the dictionary。 most likely you haven't when you try to run the code in this module。

 you're going to get an error such as this to install spacey dictionary。

 This is the command that I found works about the best if you run into problems。

 you may want to Google them or post something in in the class piazza or Sla and I'll see what I can do as far as if you're getting a specific error and also post something in the comments。

 I've run into just about every error imaginable。 well that's not true。 somebody always surprises me。

 but I can't necessarily always debug everything because I have to have it physically on my computer giving you problem。

 So believe me if you get an error。 Google is your friend just copy and paste this and put it into Google and you'll probably be taken prompt to stack overflow Some of the terms that you will hear with this tokenization is a big one And tokenization is where you take sentences and you break them into the individual work。

More difficultifficult than it sound。 Let me just put a cell above here。

 Consider some of these sentences。 If I just gave you the sentence。

 this is a test period that'd be easy to token the words are this is and a test。

 So's four words in there。 you will then get more complicated sentences like okay but what about this。

 Now you need to decide how are you going to tokenize this。 You may not want to lose that comma。

 that comma might be useful or maybe you want the comma to go away。

 So if you're breaking this into a list of word。 it might be okay comma but what about this。

 So you have to decide if you're breaking on white space or not。 then you have things like this。

 if you're breaking on punctuation， now it's going to be u is a word S is a word and a is a word you would like to keep that together。

 but unless you have some knowledge of the language， you won't really know what is going on here。

 these will just seem like three sort of disjo。Letters and that's why you have to install the dictionary for this。

 You also have to deal with things like， okay， I don't typically hyphenate data。

 but you may not want to break those into two words。 So if deal hyphens like that。

 But sometimes hyps do like if you're going to do an dash or something like that where you do a rapid shift。

 you wouldn't want to combine that into this no。 it's doing a abrupt change in the sentence。

 I think I will do this。 No， wait， I will do this or maybe that sounds good So these are some of the issues that you will run into when you're trying to tokenize sentences and look at the example one that I have here。

 There's the U period K period。 So you don't you want that to stay together。 and the dollar sign。

 you might be tempted to strip that off。 but that does give you information about that one。

 So we can run this and I will show you how spacey tokenize tokenizing is probably one of the most common things that you will do with word level。

Natural language process。 Another common one that you'll do is it will strip the words to the root form。

 So buying would become by。 Now you're losing some information there。 But that way。

 if you're doing simple lookup， look would become look rest of these are all in their base form。

 but this breaks it up into a nice set of words for you。

 So you don't have to parse it and do the tokenization yourself。 believe me。

 never look for spaces and use regular expressions and do tokenization yourself。

 It's actually a pretty hard problem that requires a dictionary to be loaded。

 that way you can keep things like UK together。 This is also kind of neat。 I don't use this as much。

 I prefer the end to end where I'm not dealing with English grammatical forms like verbs and adjectives and things like this。

 This gives you space these best guess at what these words are。 Now the problem though。

 is it's contextual。 So word can operate sometimes as either a noun or a verb。

 It just depends on how the words being used。 So this can be very difficult。

 It's not just a simple lookup。 This can also be useful because this can let you very quickly figure out what。

Different words are as far as that their're numbers。 There's other ones in here too。

 you can like none。 There's a few other likes。 I can't think of another one offhand。

 but it lets you know if the word is like something so true。

 The one in the dollar sign1 is like a number Also billion is even though it's a word is like a number of root if you want to go more hardcore on grammar you can even get them the sentences diagram for you。

 So if you run this I want a laptop an iPad laptop and a dog So I was trying to see if it could figure out that list of words there sort of does and it gives you a English sentence diagram and you get this actually as a traversible tree that you can use in your code as well。

 I usually don't use these， but it can be kind of interesting sometimes to see the diagram of a sentence really complicated sentences automatic diagrams tend to tend to fail often enough by the way。

 one thing that is easy to run into as a problem when you run this diagram。

Notice that star is still there。 So if you try to run this next thing， print out the sentence。

 you tend to think why is my print taking so long。 Well。

 it's because this guy up here is still running because it has to start a web server to actually display that to you and you can see that is evident by that So it's good to just break that and now you can run these other thing This is what I was telling you before where you take the words back to their root level。

 this is very useful。 I will use this often because then you don't have to worry about like hanging hanging All those would go to hang and this is just a list you can iterate over that and handle those as you want stop words This is a very common term in natural language processing you can see all the stop words here。

 these are words that are very common in English but have usually and I emphasize usually very little value So the stop words are often removed or deemphasize and this is just a list of the stop words So very common thing that you would do as you would loop over。

Sentence like this and remove the stop words。 You're using relatively simple word counts and statistical analysis for your natural language processing probably need to remove the stop words。

 An example， though I ran into this when I was competing in a natural language processing on Cale I was printing out the sentences that my program was not parsing correctly And one sentence in particular it was kind of interesting。

 It was what is I Well， what is I， It's the part of the company that handles the computer and data systems for the corporation。

 Well， the first thing that my program was doing putting everything to lowercase。 What is it Okay。

 that's a whole different question That is like I don't know if you brought something to show me at class a new electronic device and laid it on my desk I'd be like what is it So just dripping everything to lowercase can get you in trouble And then when I converted that sentence to。

Remove the stop wordss， it became this。A blank line because all three of those words were removed because they're all stop words。

 So this is a legitimate question that's asking something。 what is what is it。

 but you have to realize these common acronyms and not just strip it or you're going to lose every time you make a transformation and remove junk or clean up every time you clean something you're losing information and maybe that information is not valuable。

 but you have to you have to be aware of these things in natural language process。



![](img/ff26651c6e28d6ee53469ef48ed52d86_3.png)

Thank you for watching this video。 In the next video。

 we're going to talk about more natural language processing tools， particularly word to Vec。

 This content changes often。 so subscribe to the channel to stay up to date on this course and other topics in artificial intelligence。

😊。
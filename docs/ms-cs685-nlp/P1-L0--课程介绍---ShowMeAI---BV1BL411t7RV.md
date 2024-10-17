# P1：L0- 课程介绍 - ShowMeAI - BV1BL411t7RV

All right， hey everyone， so this is the first introductory lecture of CS685 the Advanced NLP class this fall。

 my name is MoHt， I'll be the instructor， I'm a professor here at UMass whose primary research focus is in natural language processing and I'm excited to focus on some very recent and revolutionary techniques that have come up within the field of NLP over the past couple years。

So before I get into exactly what kind of topics we're going to be covering here。

 I wanted to go over some logistics， I know this is especially important this semester where everything is remote and it's certainly a new experience for me and maybe also for many of you incoming graduate students。



![](img/9f6f35569e3aea3c81a2ade7981caabe_1.png)

All right。So like it's posted on the course website and again you should certainly check out the course website for everything This class will be completely asynchronous so all lectures will be pre-recorded videos like the one you're watching now either to be posted on YouTube or somewhere else if people are having issues with quality or access and so the plan is every week I will post new lecture videos definitely on Mondays and sometimes on Wednesdays as well and for each video there will be some accompanying readings which you should hopefully plan to do before watching the videos things will make more sense that way hopefully and all of the links to these things will be posted on the course website。

😊，So this is not something that I've done in the past but because we're remote and I really have no way to enforce that you are actually watching these videos like I would normally with you know taking attendance or having some attendance checks in lie of all of that I will have a weekly quiz on all of the topics that we covered in that week these will be lightly graded so just to make sure that you put in a good faith effort to answer the questions and theyll be submitted on Grcope so basically every assignment you have here will be submitted on Grcope。

 you should be added to you all should be added to gradecope by the end of this first week。

 also to Moodle and Piazza。Okay， right， there's also no quiz for this first week。

 I think we're probably going to have to work through various issues that come up with students and their you and your access to the various course materials。

 especially for those of you in countries with restricted internet。

I also should mention that we will have office hours every day from Monday through Thursday。

 we've scheduled these so that they will be accessible to people who are not only in the US but also in other time zones like India and China where I know many of the grad students currently are。

 which means that for most of the TAs and myself we'll be having 8 amm Eastern time office hours。

But yeah， hopefully this will provide a way for you to get some more like live in person feedback or any questions that you have during lecture。

 you can ask during these office hours so these will be on Zoom。

So I'll talk about this a little more but there will be one midterm in this class and occasionally so every other week or so we'll release optional practice problem so you don't have to do these but they will help you prepare for the exams so because everything is remote this semester we obviously cannot have an in-person exam which means really the only way to do this is to have you know like an open book open internet exam so the problems will be more conceptual in nature and hopefully not something you can easily Google I guess hopefully for me not for you but yeah the intent behind releasing these practice problems is to help you get prepared for the types of questions that will be on the exam and to give you something else to discuss with us during office hours so again you don't。

to do these if you don't want to， but they're just there for。

In case you're worried about some aspect of the material。

All right so the TAs for this class are my own PhD students so all three of them to Son and Calpeche they're very experienced with NLP research they've all publish papers in top NLP conferences and so you should feel free to ask any of them questions at any level or depth regarding the material here。

 they're all very familiar with it some topics they might even be more knowledgeable than I am so yeah please do attend their office hours if those times are convenient for you so again the links to the office hours oh I think that's on the next slide but yeah they're pasteed on the course website regarding email please use this instructor's Gmail account for everything you could possibly want to email me or the Ts about。

😊。

![](img/9f6f35569e3aea3c81a2ade7981caabe_3.png)

This could involve you know medical absences or other sorts of things that are preventing you from accessing or completing the assignments yeah do not email me directly I won't respond so please just use the instructor's account it's meant for this course。

All right。

![](img/9f6f35569e3aea3c81a2ade7981caabe_5.png)

Finally， office hours， so right， as I mentioned before， we have three office hours scheduled at 8 a。

m， so this is to I think this is the hour that works for most time zones。

 although it is a little late in China， I believe for those of you on the West Coast of the United States Colp will have office hours at 2 p。

m on Thursdays。We are open to adjusting these times if it turns out that there aren't any office hours that are convenient for many of you。

So again， do let us know on Piazza or on email or on other there's other ways you can contact us to tell us about these issues。

 there will be no office hours for this first week the TAs are completing internships and we're still you know getting prepared with the materials so all office hours will begin on August 31st。

 which is the start of the second week of the semester。

for days or weeks in which homeworks are due or like the week before the exam。

 we often extend our office hours for having past semesters to two hours each and we are prepared to do that for this semester as well。

 so do keep that in mind。

![](img/9f6f35569e3aea3c81a2ade7981caabe_7.png)

All right， so there are many ways in which you can contact us beyond just the course instructor's Gmail account。

 we have an anonymous form， this is also linked on the course website so if you don't want your name associated with a comment and you don't want anyone else to know about it。

 you can use this form， there's also piazza you will be all enrolled at some point soon where you can post you know questions or comments that other people in the class can also help answer so myself and the TAs will be fairly responsive on Piazza or at least we try to be but if you have a general question it's probably in your best interest to post on Piazza because there are like 120 something other students who can also answer or chime in if they have the same question so Ive decided to not record all my videos。

Like way ahead of time， but instead record them week to week。

 so whatever pertinent questions or comments that come up on the anonymous form or on Piazza。

 I will try and respond to them in the weekly videos。

 so this is a good way if something is confusing to you or to a bunch of you and this is indicated on Piazza。

 I will address these these issues。

![](img/9f6f35569e3aea3c81a2ade7981caabe_9.png)

All right。So the class has no official prerequisites。

But the following will certainly be useful and if any of these things you maybe have forgotten or not covered in a previous class。

 then you should try and brush up on them outside of class。

I guess everything is outside of class now， but yeah like outside of the assigned reading and stuff like that。

 so we will provide resources like links to tutorials and easy to understand blog posts or notes that you can use to familiarize yourself with some of these concepts。

 but programming is certainly important， we'll be using Python and Pytororch throughout the class。

 so Pytororch is a library for deep learning that all of my students use for their research and many NLP toolkits are built on so it's very useful to learn not only for NLP but for any sort of machine learning research and even in industry。

So you'll need to be okay with probability， linear algebra and basic mathematical notation。

Since this is an advanced NLP class， we will not be reviewing too much background on this。

 so again you will need to put in some effort outside of the assigned readings and assignments to brush up on this if you need to。

One thing that is especially important with the types of models we'll be dealing with is matrix calculus。

 so we'll be taking a lot of partial derivatives of various loss functions with respect to different weight matrices in neural network models we won't be going in this class into too much depth into weeds of back propagation。

 but it will be important to at least understand the notation here when I talk about representing a word as a vector and then projecting it into another space using a feed forward layer these are just basic matrix vector products which you've probably seen in linear algebra but again these will come up throughout the class so just want to。

Put that expectation out there now。

![](img/9f6f35569e3aea3c81a2ade7981caabe_11.png)

Okay。What do we have next right so how are you going to be graded as I mentioned before there will be these weekly quizzes starting the week after next those will account for 10% of your grade。

We will have three problem sets， so they'll be all combinations of written answers where you might have to write out some math or provide a short answer response to some sort of question and they'll also include coding components so all the homeworks will be hosted on Google Collab which is a free service that Google provides to researchers that allows you to to access a machine with a GPU for free this is incredibly useful if you want to be training models at any scale that's non-trivial。

 although it does have its limitations like you can't you know train an insanely large model for very long they do have timeout restrictions of I think 12 hours so like they'll kill your whatever process you're running after 12 hours。

 but on the whole it's much better than you know trying。Do something on your laptop by yourself。

That said again， I know many of you could be in countries where access to things like Google Collab is restricted。

 so I do want to hear from you if that's the case because we can also posts things like notebooks and zip files with associated Python files that you can download and submit but Google Collab makes everything easy。

 we've used it in previous semesters and it's been pretty successful so I hope that it works out this semester。

All right， so around mid October there'll be a midterm again。

 this will be challenging on the part of myself and the TAs to actually create because we expect。

 I mean it's hard to release an exam and say don't use Google right there's just no way to enforce it so the types of problems on here again will be maybe a little more conceptual and like what would you do in this situation of kind of problems。

Obviously you're not supposed to collaborate on this midterm， this is not something we can enforce。

 but we would hope that you you don't do this it's a violation of the honor code。All right。

 and then the last part of your grade will be and the biggest 35% will be final project so tentatively right now we're envisioning groups of four。

 but it kind of depends on how the class grows and what we think is manageable on the part of myself in the Ts but essentially we're going to let you choose any topic that you want that's related to NLP obviously and you will have to first propose a project with your group and then on the last day of final exams which I totally forget the date I think December 4th or something submit your final report。

AndW whichch is worth a quarter of your grade。 So for the final projects。

 we're still deciding how to organize this， but usually we。

Have a period of maybe a week or two at the beginning of the semester where we'll allow people to form groups on using Piazza so there's a thread on piazza to let you know post your ideas and see if anyone's interested in joining your team after the period for forming groups expires anyone who isn't already in a group will be randomly assigned to to a group so that's generally the process we will do this very early in the semester to maximize the time that you have to work on your project。

We still haven't decided yet how to do so traditionally we have these project presentations where you know every group has a poster and they you know present what they've done to the rest of the class instructors and other people from like companies and other faculty at UMass and so on I'm not sure how we can do this on something like Zoom。

 but maybe we can， so that's something that I'll let you know about in later weeks as the final report deadline comes closer。

😊，All right so do you need to buy a textbook no you don't everything you need will be provided as links to PDF on the website again。

 this is an advanced NLP class it's intended for I mean it's a grad level class right there's a lot of PhD students taking this class and a lot of master's students and really there's more of a research focus in the topics that we'll be discussing throughout the semester so most of the readings will be。



![](img/9f6f35569e3aea3c81a2ade7981caabe_13.png)

Pretty recent conference papers from venues such as ACL and EmNLP and so on so these are some of the most prominent conferences research conferences in the field of NLP there will be this week and maybe next week。

 some readings from an NLP textbook but aside from that will primarily be looking at research papers So your first homework will also involve picking out conference paper that you think sounds interesting in writing a little summary of it so this is just to get you some experience in reading these things because oftentimes they do not contain all of the background knowledge that you will need to understand what's going on in the paper a lot of that knowledge is assumed and so a large part of this course will be developing the background that you need to understand these。

😊，The newest wave of NLP papers。So while this class is very research focused that doesn't mean the methods and stuff we're discussing here will be are like completely impractical in industry settings that's not at all the case。

 actually NLP is a very fast moving field and most of the stuff that we'll be talking about at least the high-level ideas are already used in cutting edge industry NLP labs and products。

 so as an example Google Trans which I'm sure many of you have used over the years has completely changed in the underlying model from a more traditional phrase-based MT system to a neural network system that is used many of the models that will be discussing in this class and likewise for many other tasks as we'll talk about later in the same video the way of approaching。

These tasks has completely changed over the past two years。

 so it's a very exciting time for NLP and it's also a time where the research and industry are kind of intersecting they slowly converging to the same methods。

😊，O。So now that all the logistics stuff is out of the way。

 let's just briefly get into an introduction of what exactly NLP is。

 so we could start with what is a natural language。So by natural。

 we mean languages that have evolved through human use and not things that say humans have invented。

 like clling on， obviously is a controlled fictional language and programming languages are also not something that we'll be discussing in this class。

😊，Okay， so that's a pretty broad set of languages right。

 but then there are many tasks that kind of are under the umbrella of natural language processing。

 so basically anything that refers to modeling language using computers can be classed as NLP。😊。

And before we get into that， we we should talk a little bit about what the different kind of levels of linguistic structure there are。

 because it's important for many tasks to model just one of these levels or multiple levels and we'll look later in this class at models that kind of apply to across this the spectrum of levels。

 So let me move my。😊。

![](img/9f6f35569e3aea3c81a2ade7981caabe_15.png)

Video up here。As an aside， I also imagine my video recording skills will improve considerably through this semester。

Hopefully that's the case。Okay， so of course the first level of text right is characters right a the alphabet。

 for example， we can split up this sentence， Alice talked to Bob into these individual characters and each one in isolation doesn't tell us very much right but when they're all put together they convey some meaning。

😊，But。So characters can be combined into things like sub wordss。

 which is under the umbrella of morphology， so this word talked is actually it has this stem of talk which carries the semantics of this verb。

 and then also the suffix ED which indicates that this talking action happened in the past。😊。

So beyond that， we get into just normal words。Alice talked to Bob， there's five different words。

 we include the period there at the end， and now each of these words is conveying some meaning in isolation。

 right Alice is a person an entity two is a preposition Bob is another person and we can associate these things with their parts of speech so for example。

 talked as a verb in the past tense and two is a preposition， a period is a punctuation mark。😊。

But so this is a low level of syntax， the parts of speech they apply to individual words。

 but at a higher level we also want to know about how these words combine together to convey the meaning of the entire sentence right so this is where we get into the kind of tree structure of language where we have these different constituents So for example。

 this phrase to Bob here is a prepositional phrase it's composed of a preposition and a noun and then when you compose this with this verb talked。

 you get a verb phrase talk to Bob finally you get this full sentence when you add the punctuation and Alice Alice talk to Bob So syntax at this level is kind of referring to the grammatical rules that make up a language and these are the rules that define how you can。

😊，Use words together。All right， so then we get to things like semantics and discourse which are now getting closer to the actual meaning of these we started all the way down at characters right but now we're talking about things like Alice is an agent。

 Bob is a recipient and Bob is the recipient of this communication event right Alice is conveying some information to him through his this talk event。

 there's also other things you might want to encode in a semantic representation right that what time did this event happen of course。

 in the past， we know that from the morphology right talk and the stics。

So a lot of what we'll be focusing on this semester is on these last three or four sorry the top three or four levels of the hierarchy here and in particular we're not going to be forming explicit symbolic representations of semantics like in this example。

 but rather we will be looking at vector space representations of words， phrases。

 sentences and even documents， so these are things that humans can't easily interpret like they can with this。

 like if I read this box at the top， I clearly see that Alices and agent and Bob is a recipient。

 I can interpret it， but with the outputs of the models that we have and use nowadays I can't just look at a sequence of you know 10 different。

Real valued numbers and come to similar conclusions on what is contained by those numbers。All right。



![](img/9f6f35569e3aea3c81a2ade7981caabe_17.png)

So let's talk about some of the tasks that we can tackle within NLP。

One probably the most common paradigm learning paradigm for NLP is supervised learning so here we assume that we have access to something called a training data where we have examples that are paired with labels and so these labels can come from human annotation and as an example I could you know go to Amazon and crawl a bunch of product reviews and also get the corresponding review score with each review right so I might have a review that says you know this camera was completely bad and it didn't work and it's associated with a score of one out of five so if I collect you know hundreds of thousands of these examples now I have a very large training data set for this task of you know given a review。

😊，ickThe review score。So this task is an example of sentiment analysis which is of course very popular in industry。

 people want to know what companies want to know what people are saying about their product right so I might deploy a sentiment analysis model on Twitter to see you know for every tweet that mentions my product。

 what is a sentiment of that tweet and this could give me some information on the popular perception of this product。

So other tasks that are tackled in a supervised setting where it's required to collect this label data set of examples which in the NLP case are pieces of text so documents or sentences or so on paired with labels so in the sentiment case this will be positive or negative and for other tasks the label space looks different so for a question answering one common research problem within NLP is this kind of reading comprehension setup up so you're given a question and you're given a document and you assume that the answer to the question lies somewhere in the document so your model is asked to find the answer of that question。

😊，There are many variants of this setup right I could be given a single question and a huge collection of documents and asked to locate the answer within that collection。

 I could be given just a question and nothing else and a model might have to generate an answer to that question using any resources it has available so this could be you know a model that's able to。

😊，Access the internet or some huge knowledge source like Wikipedia。

There are many other subtasks within question answering that we could discuss and maybe we'll discuss later in the semester。

There's also tasks like textual entailment， so this is commonly framed as given two sentences identify whether the first sentence entails or contradicts the second one this is closely related to the problem of paraphrasse detection right and another popular task that will spend some time on the semester's paraphrase generation so given a sentence can I have a model that actually produces a new sentence that is a paraphrase so it has the same approximately the same semantics of the first sentence。

Machine translation is an obvious。You know， a well known application of NLP。

 you're given a sentence in some source language and a user asks a model to produce a translation of that sentence in whatever the user picks as a target language。

So machine translation also very commonly a supervised learning problem where I have ahead of time a big data set of sentences in language A。

 and their are corresponding translations which have already been produced by some external translators in a target language B。

All right， but I will say that you know there is increasingly more work on doing these things without any labeled data。

 so unsupervised machine translation is a very exciting new research field within NLP where you're asked to build an NLP model to translation sentences but you have no parallel data so you don't know for any sentence in the source language what its translation in the target languages and it's pretty impressive that given no mapping between these two languages。

 you can still learn pretty decent translation model so if you've seen the movie arrival it's not anything as cool as what goes on there but。

Similar in principle。Maybe笔。

![](img/9f6f35569e3aea3c81a2ade7981caabe_19.png)

Okay， so we just talked about supervised learning， the more recent developments in NLP and really most of the progress。

 oh， I should move my camera。

![](img/9f6f35569e3aea3c81a2ade7981caabe_21.png)

![](img/9f6f35569e3aea3c81a2ade7981caabe_22.png)

Sorry。This。Moving back and forth will hopefully be resolved at some point in the future。All right。

 so right， as I was saying， most recent progress in NLP has been fueled by advances in selfsupervised learning so this is actually a term that wasn't widely used and only started being used popularly within the last maybe year year and a half so just another point that all of this stuff is super new but in self-supervised learning we're not restricted to a smallish labeled data set that you know people had to put an effort to create here we just have a collection of text right so I can get text anywhere I could download the entire internet and have trillions or more I don't know how many tokens or sorry words they would be in in the internet but probably an insane amount。

😊，But I don't have any extra labels， right， No one's going to go on and label the entire internet with the random things like is this positive or negative。

 It's just not feasible。 So in self supervised learning， we don't have these labels。

 but we instead use the text that we have to create our own labels。 And then。😊。

Because we're no longer bounded by the size of our training data right as I just said。

 we can download as much text as exists that humans have ever written and is available in machine readable format and I can create labels out of this text and the primary use for self-supervised learning is to learn representations of text so this could be words of phrases or sentences or documents。

So what does it mean to create labels out of the text that that probably doesn't make sense right now one of the most popular objectives for self-supervised learning is language modeling and we'll spend a lot of time on language modeling over the next couple of weeks。

 but at its core basically you're giving a model the beginning of a sentence or a document or some piece of text and you're asking it to predict the next word so what word comes next in this document。

😊，So if you think about it， you can see how this task can be used in a self-supvised fashion right if I'm given an insanely large collection of text。

 I can easily create training data out of this text for this task of language modeling right because I can just keep chopping it up into chunks or prefixes of a document right so if I had the sentence let's go back。

😊。

![](img/9f6f35569e3aea3c81a2ade7981caabe_24.png)

Sorry。So if I had the sentence， Alice talked to Bob right。

 I can produce a bunch of examples for language modeling out of this sentence， for example。

 I can give the model Alice and ask it to predict talked。

 I can give the model Alice talked and ask it to predict two。

 I can give the model Alice talk to Bob and ask it to predict the period。

 right so I'm basically just cutting the sentence in various points and for every single example。

 every prefix of the sentence， I have a corresponding label。

 the label in this case is the next word that occurs in that sentence。



![](img/9f6f35569e3aea3c81a2ade7981caabe_26.png)

![](img/9f6f35569e3aea3c81a2ade7981caabe_27.png)

Okay so there's language modeling， another popular objective function for self-supervised learning is masked language modeling。

 so it's pretty similar except here I give you the entire document not just some prefix。

 but I remove certain words or spans of text and then I ask a model to given the unmasked text。

 predict the missing words so predict what was masked。😊。

Okay I guess just as another aside I like to have these like questions and yellow boxes throughout my lectures。

 usually these are questions that I asked to the class in like in-person lectures but since I can't do that here these are questions that I will usually leave for quizzes and stuff that I'll go over in subsequent weeks。

 but the answer to this question of course is I've already answered it right it's how much ever data that I can get in machine reutable format so you know humans have produced an insane amount of text and this is why self-supervised learning is so powerful is I have access to many orders of magnitude more data for these tasks like language modeling and mask language modeling。

All right so what does representation learning mean I've kind of glossed over that this is a very important point in modern NLP and the goal is if I'm given some text I want to create a representation of that text that captures there's a typo on the slide captures its linguistic properties。

😊。

![](img/9f6f35569e3aea3c81a2ade7981caabe_29.png)

These could be things like syntax， Disccourse semantics that we discussed on that previous slide so currently our representations of text。

 our state of the art representations are real value low dimensional vectors so as an example here these are word representation so the word today could be represented with a4 dimensional vector of 0。

35 negative 1。3 2。2 and 0。003。😊，So of course， I can't look at this and make any sense of what that word means。

 right？But for a computer， if it gets you know a huge list of these words along with their representations。

 it can start making sense of the vector space in which all of these words are embedded。

 so maybe words like cat are similar in the space to words like dog and not similar to words like today。

 maybe words that have the same part of speech are similar to each other in this vector space。

 maybe you know words that are semantically similar are close to each other。

 so these are the kinds of intuitions that we have when we're talking about these vector space representations of text。

😊，So when we have a selfsupervised model， we're able to learn very powerful representations of text because we have access to unlimited training data and if you imagine this task of say language modeling。

 predict the next word， right， Alice talk to， predict the next word， if I have that input。😊。

Think about what a model has to understand in order to make Bob a highly probable continuation of that sentence under its model prediction。

It has to know that it's likely that a person is going to follow that prefix Alice talked to right because people generally talk to other people or at least some sort of noun or some sort of object。

It's definitely not going to be another preposition right， I wouldn't have well。

 I guess it could be that's a lie， but it's not going to be。A verb。Okay， now and' Alice talked to。

Yeah， so it's very unlikely to be a verb right， but it's likely to be a noun。

 it's likely to be a name of a person and so already you can see that the model has to learn these linguistic properties of the prefix in order to make a reasonable prediction of what comes next This is some of the intuition why self-supervised learning is such a powerful objective。

😊，All right， and so finally， when we put these two things together。

 the self supervised learning and the supervised learning， we run into this paradigm that is。😊。



![](img/9f6f35569e3aea3c81a2ade7981caabe_31.png)

The method of choice for basically every NLP task right now， which is transfer learning。

 So I'm going to have two phases here， a pretraining phase where I take a large selfsupvised model which is trained on as much text as I can feed it。

 And then I'm going to take my small supervised data set。

 maybe my Amazon reviews and fine tune the parameters of my huge pretrain model on the label data So you can think of it as my pretraining step。

 the self-supervised step is learning a lot of general linguistic properties and things like syntax semantics discourse that are broadly useful for all NLP tasks。

 right， anything that requires understanding language and the fine tuning phase is going to kind of guide the model to perform well on of much more specific tasks。

 So maybe it doesn't need。😊，To remember syntax to solve whatever this downstream task is。

 or maybe it doesn't need to know anything at the semantic level。 Maybe it's like a， I don't know。

 So the fine tuning phase is essentially。Kind of focusing the model on a particular task。All right。

 so since this is such a successful paradigm， most of this class will be focusing on this high level concept of transfer learning within NLP。

So it's a very exciting direction， many of my own students work in this。

 so it's a good chance for everyone to learn more about， yeah， these cool new methods。



![](img/9f6f35569e3aea3c81a2ade7981caabe_33.png)

All right， so a little bit more now that we've provided an overview of what topics generally we're going to cover in this transfer learning framework。

 more specifically I'll be dividing this course into about four high level units。

 each of which will be three weeks。So the first unit will be background and again。

 since this is an advanced class normally we might spend much more time on this for something like an undergrad or even 500 level class。

 but we will be spending roughly three weeks on background so we'll focus on language modeling we'll start in our next lecture on。

😊，Things like so non neuralural approaches to language modeling which involve counting and this will include a basic probability refresher。

 but then we'll quickly move over to neural language models from there well look at popular neural architectures that people use today so things like the Transer and then we'll shift to the transfer learning unit where we will talk specifically about the recent transfer learning methods a lot of them are named after Mppets so Elmo Bt they're like Sesame Street models。

We look at variants of these models， so different training objectives。

 we talked about language modeling and mask language modeling as self supervised objectives。

 there have been many other things proposed since then， but know those are the core things。😊。

Also analysis right so if my model is producing these。Vs of vector representations of text。

 how can we make sense of what the model is learning so there is some pretty cool work on this front also that we'll cover oh。

 I forgot to mention applications so how exactly do we apply this transfer learning paradigm to solve tasks like sentiment。

 question answering and so on。😊，The next unit will focus on the general tasks that are within text generation。

 so these are things like translation， paraphrase generation summarization and so on。

 but we'll focus on more recent work that has shown a lot of promise and things like few shot learning so if you've seen open AIs GPT3。

 it has a lot of exciting results on learning from very limited examples。

 actually not even learning its。Solving tasks with kind of priming really priming a language model so this might be one direction that future research and NLP is going to take in which we minimize the role of these labeled dataset sets for the fine tuning phase over time well also look at very interesting work on the intersection between retrieval and text generation but yeah that will make more sense once we get into that unit and finally we have a kind of grab bag of important topics that we're going to cover at the end of the course so things like how do you construct a good data set for the fine tuning phase this is very important nowadays because the models are so powerful that they can latch onto any sort of artifacts during the data set creation method。

And this has happened several times recently within NLP research。

It's important to go over this whole process to make sure you're taking the best steps you can to create a usable and robust data set。

There's also evaluation so as we get more and more tasks that are possible to accomplish within NLP because of these know more and more powerful models。

 evaluating them becomes increasingly tricky right so for example some people in my group work on creative text generation so like generating stories and it's very unclear how you can evaluate these right we can't just use something like accuracy like you might use with sentiment analysis because that concept doesn't make sense。

😊，Then we'll talk about security there's as these models get more powerful and get deployed。

 there are many more security concerns some of which are specific to the types of models being used。

 for example， there is a recent work。😊，Out of。I believe Berkeley that。

The researchers were able to steal the model underlying Google Translate。

Using relatively little money。If you're in industry or thinking about going into industry and working on NLP。

 these concerns are becoming very important。Finally。

 we'll talk about ethical considerations of a lot of this work which are becoming increasingly important as we have models that you know are capable of generating text and are deployed to users in the wild what exactly do these do these models do when they're confronted with out of distribution inputs also what kinds of biases do they encode about various you know subsets of the population and so on so this is what will close out our semester with？

😊，Okay。So for next time be on the lookout for homework zero。

 it's going to be released hopefully this Wednesday and due September 4th。

 this should be fairly straightforward it's mainly a review of math and also an introduction to Pytororch or a refresher for those of you who already have experience with it。

 there will also be some as I mentioned earlier， questions on reading a research paper and writing something about it。



![](img/9f6f35569e3aea3c81a2ade7981caabe_35.png)

So the next video， next set of lecture videos， I haven't decided yet how to do these exactly if I should make shorter videos or longer videos。

 this video is already far longer than I intended it to。

 but yeah please do comment on your preferences on Piazza or using any of these other methods to let us know。

😊，Of course， if you have technical issues or course or registration or access issues again。

 please do contact us， hopefully we can get these all resolved within the first week All right。

 so I wanted to conclude by actually going through some demos of NLP systems just to have give you a more concrete idea on what some of these tasks look like and later in the semester well be actually you know designing models in your homework assignments to solve some of these tasks but right now I just want to give a high level overview so。

😊。

![](img/9f6f35569e3aea3c81a2ade7981caabe_37.png)

If I switch windows。Yes， okay。All right， also let me move my thing over here。



![](img/9f6f35569e3aea3c81a2ade7981caabe_39.png)

Okay。So this website is hosted by Alllan NLP which is part of the Allen Institute for Artificial Intelligence I actually did a postdoc here before joining UMass。

 so I know many of the people that develop this demo but I think it's a great way of getting a basic introduction to a lot of different NLP tasks and actually it allows you to interact with the models directly rather than me just showing you random examples on slides。

So we'll start with this reading comprehension task I mentioned this before as you have some document and you have a question about that document and you want the model to figure out what part of the document answers this question so here we have a description of a basketball game between the Mavericks and the Sps I guess it's a playoff series between the Mavericks and the Sps and the question is how many points do the Sps beat the Mavericks spy and Game7。

So one of the constraints of these models is that they cannot produce any text that is not contained by the document。

So in Game seven， we see if we go to the end of this document。

 game7 was on the Spurs home court and the Sps beat the Mavericks 119 to 96。

 so I guess this is like a 23 point， so the answer to this would be 23 points。

 but there is no mention here of 23 points。So what can the model do This is an example of some of the limitations of the model if we had run here。

 this is actually querying a model with this input and we see that the answer was 119 to 96。

 this is what the model predicted， which I guess is the best thing it could do right。

 it gives you the actual score instead of the margin。😊。



![](img/9f6f35569e3aea3c81a2ade7981caabe_41.png)

![](img/9f6f35569e3aea3c81a2ade7981caabe_42.png)

![](img/9f6f35569e3aea3c81a2ade7981caabe_43.png)

So right， this is an example of the model's limitations。

 but also it's not that bad right it's doing something decent。

 we could ask it an easier question so again I can just type in questions。

 I could ask about where was game Oh yeah yes， where was game。😊，7。O， didn。Okay。

 so here I would expect the answer to be maybe San Antonio or Spurs Home Court。



![](img/9f6f35569e3aea3c81a2ade7981caabe_45.png)

And then the spurs home court。

![](img/9f6f35569e3aea3c81a2ade7981caabe_47.png)

So it's you know for these simple kinds of questions it's pretty good but for more complicated questions these models can really struggle so I would encourage you if you're interested to play around with this model and see if you can break it one of your homework assignments later on in the semester will be very related to doing stuff like this so coming up with inputs that break existing models let's also take a look at sentiment analysis because we discuss this as well so I'm going to use this Roberta model which is one of the best performing models for the task of sentiment analysis。



![](img/9f6f35569e3aea3c81a2ade7981caabe_49.png)

![](img/9f6f35569e3aea3c81a2ade7981caabe_50.png)

![](img/9f6f35569e3aea3c81a2ade7981caabe_51.png)

Um，Maybe I'll use a existing example so I don't have to come up with the one。

So unremittingly awful that labeling it a dog probably constitutes cruelty to canines。

So this is clearly negative about this movie， all of these sentences are movie reviews。



![](img/9f6f35569e3aea3c81a2ade7981caabe_53.png)

![](img/9f6f35569e3aea3c81a2ade7981caabe_54.png)

AndThe model is 100% sure that it is negative。 So right。😊，And let's see， I'll go over one more task。



![](img/9f6f35569e3aea3c81a2ade7981caabe_56.png)

Right， so they have a language modeling demo， which again， we talked about before。

 So let me put in our sentence。 Alice talked to。And。Oh my god。对。Okay。

I guess that didn't work out so well， I'm not sure what this。

Clearly I didn't plan these examples out beforehand。Let's try another example。

I'm just copying this from the。Language modeling is a task of。All right。

 so modeling is probably not a great continuation to the sentence how about we go with using。

The model then predicts。 So you can see it's predicting the next word。

 And then we're just going to keep predicting the next word。

 So language modeling is the task of using data to。Predict the future behavior of。A group of。

Individuals period， okay， so it's not great， but it did produce a grammatically correct sentence。

And yeah， hopefully that gave you a good insight into this task right of predicting the next word given a prefix How about mask language modeling。

 I'm just going to use an example here to avoid what just happened with Alice talk to Bob the doctor and the emergency room to see mask patient So what goes in the mask the model predicts his。

😊。

![](img/9f6f35569e3aea3c81a2ade7981caabe_58.png)

![](img/9f6f35569e3aea3c81a2ade7981caabe_59.png)

![](img/9f6f35569e3aea3c81a2ade7981caabe_60.png)

This is also an example of gender bias within these models。

 you see the low percentage assigned to her here， this is an issue with the well。

 a lot of the issues with the training data of this model seeing just in general text wherever it was trained on。



![](img/9f6f35569e3aea3c81a2ade7981caabe_62.png)

That doctors were more likely to be associated with masculine pronouns。But of course。

 it's not only an issue with the data， but also with the models。

 this is something we'll talk about in the final unit of this lecture。



![](img/9f6f35569e3aea3c81a2ade7981caabe_64.png)

Okay and then there's many other tasks that you can play around with here。

 so I think this has already gone on far too long so I will stop here， but yeah。

 look out for the homework and next video to be released on Wednesday。



![](img/9f6f35569e3aea3c81a2ade7981caabe_66.png)

All right。
# 【双语字幕+资料下载】使用 Scikit-learn 进行机器学习，4小时实战视角刷新知识框架，初学者进阶必备！＜实战教程系列＞ - P5：5）sklearn 管道 - ShowMeAI - BV16u41127nr

![](img/6759ee1a4176e478df5915cb285d57a7_0.png)

。Well， in this video， we're going to be learning about Pscant Learn pipelines。We've been learning how to use linear regression as a model。 and often our model will have to transform the data in some sort of way before we can actually analyze it。 and so we'll end up with for our models are these pipelines where we do a series of transformations and then at the end we'll use an estimator is what they call it in PsyAL to actually make predictions。

And so for this example， I may be using a slightly more complicated data set in Chicago which is right on Lake Michigan。 they have all these sensors on different beaches which are measuring things about the waves and so I'm maybe looking at this data set all these measurements so I can see well here's an Ohio Beach here's 63rd Street Beach。



![](img/6759ee1a4176e478df5915cb285d57a7_2.png)

And then I know all these things about these sensors， like how warm is the water， turbidity。 and other things like that， and the why that we're going to try to predict is well how big are the waves on this speech。And we're going to be using things like like wave period to predict or maybe by looking directly at what beach we're on。

![](img/6759ee1a4176e478df5915cb285d57a7_4.png)

And so theres some garbage data in here， so I've cleaned that up。 so this is a picture of all the data where I have the wave period on the X axis and then on the Y axis。 I have wave height。![](img/6759ee1a4176e478df5915cb285d57a7_6.png)

![](img/6759ee1a4176e478df5915cb285d57a7_7.png)

Then I also try to break it down and to look beach by beach。 so here I'm kind of pulling out all the beaches as a sortrded list that's unique。![](img/6759ee1a4176e478df5915cb285d57a7_9.png)

From the beach name， and then what am I doing down here， I'm drawing each beach separately。![](img/6759ee1a4176e478df5915cb285d57a7_11.png)

So I'm creating some subplots。And I'm looping over those。 and I'm basically plotting each beach。 right， I'm doing some filtering in pandas。 I'm plotting each beach in a different Ax region。 And so I look at this。 and so there's a couple observations right away， often before I do modeling。 I like to just do a lot of scatter plots and try to get an intuition from what's going on。



![](img/6759ee1a4176e478df5915cb285d57a7_13.png)

One is that I do see that what beach runron is an important variable。 some of these beaches have different patterns in terms of the waves。The other thing I see is that the relationship between wave period and wave height is not linear。 it's not as if the bigger the wave period， the bigger the wave height or vice versa。

 what I see is often there's kind of like this hump in the middle right so kind of if we want to get the biggest waves。 we need a wave period that's somewhere in the middle。![](img/6759ee1a4176e478df5915cb285d57a7_15.png)

So I'm going to be making four different models here that try to analyze this data and they're each going to be using different variables in different ways first will be something very similar to what we've done before。 I'll try to predict the wave height based on wave period just using a simple linear ear regression and we'll see what performance we have there next we're going to learn how we can do a polynomial effect right so that means if I'm drawing a line on here while the line doesn't have to be straight anymore。



![](img/6759ee1a4176e478df5915cb285d57a7_17.png)

Finally， I'm going to look at well not finally， but next I'm going to look at what beach if the only thing I know is what beach I'm on。 how well can I predict？And then finally， I'm going look at the combination of both beach and wave period。 with wave period being treated as a polynomial and see how much I can predict there。So in terms of my imports， I have some things that we've done before we've the first thing we learned was how to do a linear regression。

 we would fit our linear regression to training data set and then we would evaluate it on a test data data set at the very end along the way we might also do crossvalidation within just the training data so these things are old and then these things down here are new right so in order to be able to。



![](img/6759ee1a4176e478df5915cb285d57a7_19.png)

Deal with this data and I want in a polynomial way I might have to transform it using this polynomial features thing if I want to deal with categorical data like well what beach am I on that's not a number right that's a category I have to use this thing called one hot enr and if I want to use both of those I have to use this other thing make column transformer to combine them and in total what I'm going to do is I'm going have this pipeline and in the end of the pipeline I'm still going be doing just a simple linear regression。

But I'm going be making all these transformations to the data before it gets to that。 and that's how maybe I'll do these more complicated models。So let's start down here and I may call。 I'm just trying to number these four models of one， two， three。 four just following the numbering up here， as I may have Model 1 is going to be just a simple linear regression。

Like that。 And And then what I could do is I could say M1， well， actually。I could do different things I could say M1 do fit and I would fit that to my x values and then my y values here。 this is uppercase because it's a full data frame and then this is lowercase because it's just done a single series and I guess before I have to do it I actually have to separate out my train data frame from my test data frame。And I say train test。Split Df。And maybe I'll just look at the length of both of these。



![](img/6759ee1a4176e478df5915cb285d57a7_21.png)

。And so about 25% is going into testing， which I'll be fine with that。And so then down here I have to have my trained DF， and then here I can put a list of features。And then over here， I may have my train DF again， and I just may have my Y column。 and so my y column， the thing I'm trying to predict is just while the wave height。

Like that and then my list of features， well first off I've put a list here and that's why I get these weird double brackets。 I'm just going to start with wave period just like that and I probably have to capitalize to match what is in my data frame from earlier if I check back。



![](img/6759ee1a4176e478df5915cb285d57a7_23.png)

![](img/6759ee1a4176e478df5915cb285d57a7_24.png)

Yep， it looks like all these things are capitalizing。And so I can do that。And， and now。 this model has learned the pattern。And so then what I could do is I could say M1 dot predict。Based on my testing data。So I could say test Df， right so I give it only x values and then it's going to predict what these y values are for me。

![](img/6759ee1a4176e478df5915cb285d57a7_26.png)

And so let me oh， might I call it M2 M1。 And so I get all these predictions。 And then what I could do is I can compare those predictions to。![](img/6759ee1a4176e478df5915cb285d57a7_28.png)

![](img/6759ee1a4176e478df5915cb285d57a7_29.png)

What I actually have for that wave period。I can compare these numbers to these numbers down here and at a glance I see it's not very close the easier way for me to do that comparison and actually get a score will be I call the scoring right so the score function will automatically call that predict on this and then it'll compare that to my test D of wave height and it will tell me what percentage of the variance I'm explaining there and I see right now it's terrible right I'm not really explaining anything if I just always predict the average wave height that would be better than what I'm doing right now now of course some of this is luck in terms of like how I did my train test split。



![](img/6759ee1a4176e478df5915cb285d57a7_31.png)

![](img/6759ee1a4176e478df5915cb285d57a7_32.png)

And so the more reliable way to get a measure here。 Let me just print that would be to do my cross validation。 That so I can say cross validation score。![](img/6759ee1a4176e478df5915cb285d57a7_34.png)

And then here I have to give it three things， I have to say， well， what is my model， my model is M1。 what are my x values and what are my y values I'm going to do this up here。And when'm doing the cross validation I usually do that all within the training data and I just try and hold back the test data for the very end of my project to have a final analysis I see I actually get a variety of scores and we can see that yeah it is a matter of luck sometimes I do worse than zero most of the time not I can say how many pieces I want to break my data into remember that I cycle through each piece or fold and it has its turn being the test data set so I can get more here numbers here maybe I'm just going to say scores equals that and I could say scores don't mean。



![](img/6759ee1a4176e478df5915cb285d57a7_36.png)

![](img/6759ee1a4176e478df5915cb285d57a7_37.png)

And so this is probably a better indication of how well my model is doing。 I'm explaining 1/10th of 1% of the pattern， which is not too surprising right all I'm using is the wave period and I'm trying to fit a straight line to this and I can see well yeah。

 no surprise I can't fit a straight line to it。![](img/6759ee1a4176e478df5915cb285d57a7_39.png)

![](img/6759ee1a4176e478df5915cb285d57a7_40.png)

Okay， if I wanted to， let me just copy this for a moment， I'm going to delete it shortly。If I wanted to do more columns， that would be an easy thing to do。 So for example。 if I wanted to also include， let's say like the water temperature。 I could easily add that as another column， right， It's very simple to have multiple x values So I can do that here。



![](img/6759ee1a4176e478df5915cb285d57a7_42.png)

![](img/6759ee1a4176e478df5915cb285d57a7_43.png)

And then down here as well and then maybe I get a slightly different score still not great right was just try delete this here right。 but it's very easy to add these different things and why is that well when I do this and I put that list here。 I'm just showing a simple data frame of X columns that I want to use for my predictions。

![](img/6759ee1a4176e478df5915cb285d57a7_45.png)

![](img/6759ee1a4176e478df5915cb285d57a7_46.png)

![](img/6759ee1a4176e478df5915cb285d57a7_47.png)

![](img/6759ee1a4176e478df5915cb285d57a7_48.png)

Okay， so that's that's how we can add things， let's actually think about how we're going to do this now if I want to have a polynomial vet。 so what we'll do is let me actually delete all of this。😊。![](img/6759ee1a4176e478df5915cb285d57a7_50.png)

![](img/6759ee1a4176e478df5915cb285d57a7_51.png)

I'm just trying to create a demo here， which is going a copy of my train DF and my train DF Im may have just。A waveve period。![](img/6759ee1a4176e478df5915cb285d57a7_53.png)

Let me take a look at this data frame， but we're going to be doing if I want to have say like a quadratic fit。 I want to just add some columns down here that are going to contain that square data。![](img/6759ee1a4176e478df5915cb285d57a7_55.png)

And so I can do things like this， I could say demo。I could say period。Squared。Equals demo。Of wave period。That or I could have like one that's cubed like this。![](img/6759ee1a4176e478df5915cb285d57a7_57.png)

And。And why is that unhappy， Oh， because I'm doing a comparison on an assignment。 so I just assumed that' already exists。![](img/6759ee1a4176e478df5915cb285d57a7_59.png)

And so if I do that， then。![](img/6759ee1a4176e478df5915cb285d57a7_61.png)

And you know， I do I actually want to copy this so that it doesn't complain。I can see what I'll do is that this column while two squared is2，2 cubed as8。3 squared his line。33 cubed is 27。 And so what I can actually do is I can do a linear regression across these things right and so even though secondly the linear regression is trying to act like quadratic or cubic regression because。

![](img/6759ee1a4176e478df5915cb285d57a7_63.png)

Because I'm just treating these as regular columns right and I can put kind of weights to how important these things are and so how can I do this so here I was just manually adding these things If I want to I can use this polynomial features thing。![](img/6759ee1a4176e478df5915cb285d57a7_65.png)

![](img/6759ee1a4176e478df5915cb285d57a7_66.png)

And so down here， may I say Polly。Equals polynomial features， and I can say poly dot fit transform。And what I want to do， I want to transform my data right here， this was what I had before。![](img/6759ee1a4176e478df5915cb285d57a7_68.png)

So I'm going to run this thing。And I see that I get all these different columns。And and if I wanted to， let me capture those in data， right， This is one of those nuy arrays。 which we'll eventually learn about until we learn about it。 I just want to put it in a panda data frame so I can better see what's happening。

 So I going say pandas data frame。![](img/6759ee1a4176e478df5915cb285d57a7_70.png)

And then I'm going put my data there and then I want to figure out what the column names are on those and it turns out that this thing will tell me that as well。 so I can say， I'm sorry Polly will tell me that， so I can say poly do。![](img/6759ee1a4176e478df5915cb285d57a7_72.png)

![](img/6759ee1a4176e478df5915cb285d57a7_73.png)

Feature names just like that， and I have to say columns equals that。![](img/6759ee1a4176e478df5915cb285d57a7_75.png)

And now I can see well I have V x and then x squared。 and I actually have to tell what my original name was for that to work。![](img/6759ee1a4176e478df5915cb285d57a7_77.png)

![](img/6759ee1a4176e478df5915cb285d57a7_78.png)

I actually have to have like a list of that， excuse me。![](img/6759ee1a4176e478df5915cb285d57a7_80.png)

And so I can see， okay， well I have period and I have period squared， and if I wanted to appear。 I could say things like well I want to have it be a fourth degree right so I could have period period squared period cubed period to the fourth。![](img/6759ee1a4176e478df5915cb285d57a7_82.png)

![](img/6759ee1a4176e478df5915cb285d57a7_83.png)

You can see it also is giving me period to the zero which is just a column of ones right and so what I'll often do is I'll disable that it's called the bias column。 so I'll say I don't want that thing。![](img/6759ee1a4176e478df5915cb285d57a7_85.png)

And so now I actually have something that's very similar to what I did above manually and I could do that with my data right I could if I wanted to I could do this transformation on both my training data and then my test data and then that's what I would do all my modeling on now I think to keep things simpler what we want to do is we want to automatically transform and then immediately apply the linear regression and so it turns out that pipelines which I also imported up here。

 make that really easy to do right so I can create a pipeline down here。![](img/6759ee1a4176e478df5915cb285d57a7_87.png)

![](img/6759ee1a4176e478df5915cb285d57a7_88.png)

![](img/6759ee1a4176e478df5915cb285d57a7_89.png)

![](img/6759ee1a4176e478df5915cb285d57a7_90.png)

![](img/6759ee1a4176e478df5915cb285d57a7_91.png)

Like this， and maybe I'll just draw this on this is going to be my second model。 it's going to be a pipeline， and then we have to pass in a list here。![](img/6759ee1a4176e478df5915cb285d57a7_93.png)

![](img/6759ee1a4176e478df5915cb285d57a7_94.png)

And the way the list works is that I will have like transformers。U。 and I might have like one or more of those。And then at the end， I may have an estimator。Right so all of these things are going to be modifying my data in some way。 maybe adding more columns and then at the very end I may actually do my real model and my real model is just a linear。

regression like that。 And then here， well， what are my transformers， well。 I'm just trying to do polynomial features like this。And and I think the degree of two will be fine for us for now and so I have these two things and then the later detail about this pipeline is that we have to name each of our stages of the pipeline and the way that it wants us to do that is it wants us to put these things in parentheses to create a tuple and then put a name as the first part of the tuple。

 so I'm going to call this transformer poly because it's a polynomial transformer and then this thing I don't know I'll just call that LR for short。It doesn't really matter。![](img/6759ee1a4176e478df5915cb285d57a7_96.png)

Allright so let me just take a look here M2 it kind of shows me all these details of it。 but now M2 is just a model right and it's a lot like a simple linear regression I can do it in all the same ways so for example if I head back here all of this stuff I did before。



![](img/6759ee1a4176e478df5915cb285d57a7_98.png)

You I just created M1 as my model and I did all this stuff on it。 I can do all those same things down here right so if I run down here and I just say M2 dofi and maybe I'll just delete this for simplicity everything's the same and I can see while maybe I'm doing slightly better now so what was my score before。



![](img/6759ee1a4176e478df5915cb285d57a7_100.png)

![](img/6759ee1a4176e478df5915cb285d57a7_101.png)

![](img/6759ee1a4176e478df5915cb285d57a7_102.png)

Actually， that's exactly the same。 I was expected to do slightly better。 And why wasn't I doing better， probably because I was evaluating my same model。 That's the curse of the of the copy paste。 Okay， so so before let me just see this。 I was explaining 0。1%。

![](img/6759ee1a4176e478df5915cb285d57a7_104.png)

![](img/6759ee1a4176e478df5915cb285d57a7_105.png)

![](img/6759ee1a4176e478df5915cb285d57a7_106.png)

![](img/6759ee1a4176e478df5915cb285d57a7_107.png)

Well I guess closer to 0。2% of the variance and now I'm explaining more like 4。6% so I can see that model2 is a huge improvement on Model one and the only thing I really did there I'm still doing a linear regression but I'm just giving it a little bit more information to work with by giving it these extra columns I have a column that says something like wave period squared and drawing way back here。

 the intuition is right is I'm fitting a line here。![](img/6759ee1a4176e478df5915cb285d57a7_109.png)

![](img/6759ee1a4176e478df5915cb285d57a7_110.png)

![](img/6759ee1a4176e478df5915cb285d57a7_111.png)

And that line doesn't have to be straight anymore。 It can be a quadratic line that kind of curves。![](img/6759ee1a4176e478df5915cb285d57a7_113.png)

Okay， so we have two of these models。 We have this one。 which was terrible right It told me almost nothing。 Sometimes this one。 depending on your train test data site would actually lead you farther away from the truth。 And if you just always guess the average， this one is actually doing somewhat well。

 right It's explaining almost 5% of the variance。 Let's try the beach。 And and see how we can do that。 So that'll be my third model。 And so if I come down here。 I think for this one， I'm just going to go back to here and try this as a first attempt。![](img/6759ee1a4176e478df5915cb285d57a7_115.png)

![](img/6759ee1a4176e478df5915cb285d57a7_116.png)

![](img/6759ee1a4176e478df5915cb285d57a7_117.png)

Maybe I should have some comments here， right， so this is。This is Po period。![](img/6759ee1a4176e478df5915cb285d57a7_119.png)

And then what was this one up here， so Model one， this was just linear on period。![](img/6759ee1a4176e478df5915cb285d57a7_121.png)

And then I'm going to try doing you know， linear on beach is what I'm trying to do right now。 And so if I have this model， I'm going to call this model 3。And maybe'm going to delete this again just to keep it clean。And may do this down here。![](img/6759ee1a4176e478df5915cb285d57a7_123.png)

The main thing I want to do is instead of having it be wave period， I want it to be the beach name。 and if I had it all the way up here I' just see all that speech name。![](img/6759ee1a4176e478df5915cb285d57a7_125.png)

Okay， so I'm going to head down here and I want to predict。![](img/6759ee1a4176e478df5915cb285d57a7_127.png)

The wave height based on beach name， right， so just like that。 And then this is also beach name down here。![](img/6759ee1a4176e478df5915cb285d57a7_129.png)

And this is going to complain to me and what does it complain about it says could not convert to a float Ohio street name Street Beach is not it to not be converted to a float and that makes a lot of sense right so this thing here if I take a look at it is。



![](img/6759ee1a4176e478df5915cb285d57a7_131.png)

![](img/6759ee1a4176e478df5915cb285d57a7_132.png)

That's categorical data and it turns out the linear regression will eventually learn why。 but it wants everything to be numeric。![](img/6759ee1a4176e478df5915cb285d57a7_134.png)

And so that's a problem。 And so how do I。How do I。How do I deal with this， I mean。 maybe one idea that students sometimes come up with is that I could intde these。 I could say like one means Ohio Beach and then maybe two means a calummet beach。 and then maybe three means， something like Montrose Beach。



![](img/6759ee1a4176e478df5915cb285d57a7_136.png)

![](img/6759ee1a4176e478df5915cb285d57a7_137.png)

![](img/6759ee1a4176e478df5915cb285d57a7_138.png)

And。The problem is is that if I put these numbers like this。嗯。The linear regression model is going to assume they're meaningful。 and so what that means is that if the model learn something about Ohio Beach and then it learn something about Monroose Beach。It mistakenly thinks it know something about calamette Beach just I think that that's somehow the average all these other show and of course that's not true right I mean。

 just I kind of arbitrarily put these numbers here。 there's no reason to believe that this beach has characteristics that are kind of average of other two so that's not going to work right I can't ent it that way。![](img/6759ee1a4176e478df5915cb285d57a7_140.png)

The idea that we going to use instead is called one hot en coatding and one hot in toding looks like this。 one hot ender。It's going to be like that and I can say 112 thatt foot。Transform。I'm going to transform this data right here。And I get this weird thing that's， well。 whatever is that that's like it says it's like a sparse matrix。

We're going eventually learn more about that， but I can convert it to this thing， which is。I is a nuy array， and then that thing I can actually put into， and I'm going simplify this a bit。That thing I can actually put into a data frame or sometimes say panda do data frame。

![](img/6759ee1a4176e478df5915cb285d57a7_142.png)

Just like this and then just like before， I want to figure out what these columns are and so just like with the polynomial transformer。 I could say get feature names，Same deal here， right， I can say what hot dot get feature names。like that and then I have to tell it well， what was I originally operating with and I guess I was like the beach。

![](img/6759ee1a4176e478df5915cb285d57a7_144.png)

And why is that unhappy？So the shape of the values past is this and and indices imply。Something like that， I wonder what is going out right there。 I think my promise is that I need to say like columns equals that。![](img/6759ee1a4176e478df5915cb285d57a7_146.png)

![](img/6759ee1a4176e478df5915cb285d57a7_147.png)

Okay， and so how is this working， so the first one by first row was Ohio Beach。And you see that I have actually a column for each different beach。And what we'll do is we'll set within that。 We'll set it to one。 If it's an Ohio Beach。 and then it'll be 0 and all others。 If I go a few down。

 I see that I have a Mon Rose Beach in position 4。![](img/6759ee1a4176e478df5915cb285d57a7_149.png)

And so that taste， I'll put a one under Mont Rose Beach and then a zeros under others。 And that's what we call it one hot。 right， So I guess the place where it's hot is where we have a one and then everywhere else。 it says zero， So if I have this。![](img/6759ee1a4176e478df5915cb285d57a7_151.png)

Even though I started with some categorical data， I can end up with something where。Where I have a bunch of numbers。And so if I， if I clean this up here。![](img/6759ee1a4176e478df5915cb285d57a7_153.png)

Let me draw back to this。 I may actually delete all of this because this was kind of a dead end。 right， What will be a closer inspiration is the pipeline I used before with。![](img/6759ee1a4176e478df5915cb285d57a7_155.png)

![](img/6759ee1a4176e478df5915cb285d57a7_156.png)

With with the polynoial features because just like polynonoial features as a transformer。 so also is one hot encoding right， so I'm going to tweak this， we're on model 3 now。And this is one hot。And here I can just blowl this away， and I can say one hot in toor。Just like that。 and then I can do my linear regression down here。 and so then I can say down here。

 I can say。![](img/6759ee1a4176e478df5915cb285d57a7_158.png)

I think it was like beach name， right。 So beach name。 and then。Actually， I don't even need this。 right， Im I'm kind of this will automatically do the fitting for me and tell me how well it's doing。呃。I wonder why this is complaining up here。 I get nervous that's thread anyway。 It'll probably tell me shortly。I can say beach name here。

And then let me try that and then sure enough， it's invalid syntax。Because I didn't have a match there。![](img/6759ee1a4176e478df5915cb285d57a7_160.png)

。And so this does even better than before， right， so I guess just looking at the beach name is even better than knowing what the wave period is。![](img/6759ee1a4176e478df5915cb285d57a7_162.png)

Right， so my model is getting better and better。 right first。 I started with just a linear model on the wave period。 and then that's terrible right I'm now even explaining 1%。![](img/6759ee1a4176e478df5915cb285d57a7_164.png)

![](img/6759ee1a4176e478df5915cb285d57a7_165.png)

And I said， well let's do a polynomial fit on the wave period and I'm explaining almost 5% and well about 4 and half percent。 then I just look only at the beach and I get 5。5% and so the kind of natural next thing to do is well let's do the regression on both beach and and also polynomial of the wave period and maybe I can do even better maybe that both these things are providing me some information。



![](img/6759ee1a4176e478df5915cb285d57a7_167.png)

![](img/6759ee1a4176e478df5915cb285d57a7_168.png)

And so here is where I get to have a challenge， right because I want to do one hot en coating on the beach name。 and I want to do polynomial features。![](img/6759ee1a4176e478df5915cb285d57a7_170.png)

![](img/6759ee1a4176e478df5915cb285d57a7_171.png)

My other column right I have to have some sort of way of combining these things and it turns out that that's that last piece that I imported up here。 the make column transformer is going to let me stitch together multiple transformers each of which applies to a different column so I going come down here and I may copy this for my inspiration for kind of Model 4。



![](img/6759ee1a4176e478df5915cb285d57a7_173.png)

![](img/6759ee1a4176e478df5915cb285d57a7_174.png)

![](img/6759ee1a4176e478df5915cb285d57a7_175.png)

![](img/6759ee1a4176e478df5915cb285d57a7_176.png)

I time I have model 4 now。 And what am I going to do？ So this is what has to change， right？

 somehow I have to have。Something here。That can capture both columns， right。 because what I'm going to do down here is I may pass in both beach name and wave period。Like that in an effort to predict my wave height。And so how do I do that， Well。 I I call that thing that I imported， which was make column transformer。

And when I'm calling that thing and when I'm calling that。 what I'll do is I'll have just a series of transformers。 And I'll have like transformer。One and then transformer two， and if I wanted to， I could have more。 but I don't need that in this case。Each of these things。

 each of these transformers is going to be a tuple and the tuple will be the transformer。And then it will be a list of the columns that it applies to right so both are going to be like this right I have these tuples and maybe I'll just try to put a new line there。

So we have these two transformers。And then a list of columns。 And so I think what I want to do is I want to do one hot encoding on the beach name right so I'm going to copy my one hot encoder right here。 and then what column does that apply to Well that applies to the beach name column。 And then my other one was polynomial features， which I should just copy from up above。

 that was this thing right here。![](img/6759ee1a4176e478df5915cb285d57a7_178.png)

![](img/6759ee1a4176e478df5915cb285d57a7_179.png)

Polynomial features。It is my other introtter。 And what does that apply to that only applies to wave period。Okay， so I have this model for now and then I can well try running it and now I see I'm getting up to 9。5% of variances explained， which is actually， well， I guess I wish I was explaining 100%。 but I could see by kind of considering both these factors I'm explaining quite a bit more than I would have otherwise。

So one last thing I want to do before I wrap up this video is I want to talk about why we have these names here and I can use this。We can use pipelines like a dictionary。Right， so so for example。 that means I can put both here and what will that give me。 that will give me this column transformer that I created。



![](img/6759ee1a4176e478df5915cb285d57a7_181.png)

Right here。 And so if I wanted to， I could kind of peek at what this thing is doing as a way to debug my model。 I could say fit， transform。![](img/6759ee1a4176e478df5915cb285d57a7_183.png)

And then what I could do here is I could say， well， this is the data I'm working with so I could see。![](img/6759ee1a4176e478df5915cb285d57a7_185.png)

That well and then I guess I'd actually need to have some column names here as well。 but I can see well， this is what I'm dealing with， let me do a data frame。![](img/6759ee1a4176e478df5915cb285d57a7_187.png)

![](img/6759ee1a4176e478df5915cb285d57a7_188.png)

Here。I could see that it has all these columns here that have the one hot en toading。And then I have these columns here that are doing polynomial features on other things。 so this is the data that I'm using to try to predict what the wave height is。 so even though I'm kind of starting with just these two columns。After I do all this transformation。

 I'm actually I'm giving the linear regressionion here at the end of my pipeline。 quite a bit more information to work with， and that's why we're able to do much better here。So as the very last step， what I would like to do， so I saw that Model4 was clearly the best one so that's the one I'll recommend now it's possible if I'm doing four different models one of them just kind of by lock does better and that's why I hung on to my training data I only used around my testing and I'll use training data for cross。



![](img/6759ee1a4176e478df5915cb285d57a7_190.png)

Validation scoring。 So at the very， very end， I may fit this data to these things。Just like that and。![](img/6759ee1a4176e478df5915cb285d57a7_192.png)

Then let me just run that and then I could use it to make predictions right。 let me just remember how to do this because it's useful。 I could use this to make predictions on my test data frame。Like that。I could make all these predictions for what the waves could be。

 or I could as a convenience score how good those predictions are against my test DF of。wave height。And I see well now I'm explaining 8。4% of variances right so I did do a little bit lucky there。 but still I can say this is clearly better than my other models were。

![](img/6759ee1a4176e478df5915cb285d57a7_194.png)
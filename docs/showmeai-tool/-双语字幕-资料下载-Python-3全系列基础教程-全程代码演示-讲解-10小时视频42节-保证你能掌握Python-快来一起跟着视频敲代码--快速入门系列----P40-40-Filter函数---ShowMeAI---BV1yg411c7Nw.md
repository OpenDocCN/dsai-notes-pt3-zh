# 【双语字幕+资料下载】Python 3全系列基础教程，全程代码演示&讲解！10小时视频42节，保证你能掌握Python！快来一起跟着视频敲代码~＜快速入门系列＞ - P40：40）Filter函数 - ShowMeAI - BV1yg411c7Nw

![](img/8136362644f8a25b56808178af805eb5_0.png)

Welcome back， everyone。 In this video， we're going to cover the filter function。 And this is very similar to the map function we covered in the previous video where we have some sort of function。 I actually put this as fun because I think filters are fun and some sort of iterable containers。 It's going to return true if it matches the filter。 This is important。😊，If it matches the filter。

 it will be placed in the result。 Otherwise， it will not。 This is a really powerful way of filtering things。We're going to look at two example usages of the filter function。 The first one is just simply getting a subrange。 And when I say simply。 this is actually pretty powerful。 So I'm going to import a random。We've talked about random before。 and then I'm going to say some values， and we're going to make a blank list of values。Or x in range。And we're going to make 10 items。 And in those 10 items， we want to get a random number。 Some must say V do append。And we going to say or random。That。Rand range。

 This is going to take a range from  one， I should say，0 all the way up to whatever there we go。 So we're going to say R range。And then we're just going to print this out。Just so we can see what our range actually returned。Let's go ahead and run this so we're just getting some random numbers 96， I mean。

 you see they're just all over the place if I' run this multiple times and you see the numbers are changing down there。So what we're going to do now is say， I want to note the lower half of this。Bss walks in the room and says， I don't want anything over 50。 Okay。 so I'm going to make a little function。We're going to take our value。I'm going to say if。Value。

Is less than 50。Then I want to do something with it。I want to return。Rue。 because the boss said he only wants to see values less than 50， otherwise I'm going to say else。And we're going to return。Alsose。This is about as simple as it gets。 This is basic filtering。 That's really what a filter does。 Does it match yes or no。That's it。

 That's really as complex as it needs to be。 So I'm going to say F equals。 and we're going to go ahead and filter。Using the lower function。 Remember。 we had this conversation in the last video。So we have our function call and then we have our values。This list of values right here。Each one of these is going to get called turned。

 So it's going to call it on 57，72 dot， dot and so on。 And the logic here is it's going to say。 is that individual value like 57。 I it less than 50 falses，70 falses too true。 I think you understand the logic here。 So let's go ahead and。Print this out I'm going say print。F。And I want to say。Less than。I help if I put that in the actual votes there。Le， than  50。

When your keyboard betrays you， Okay， so we're going to convert that into a list。Otherwise。 we're just going to get back a function object， which really doesn't help us out a whole lot。So here's our number set and the items that are less than 50，1733，45 and 11。 So this is what I mean by it is extremely fun and powerful。Very quickly。

 can you just take some sort of data set here and just say， you know what。 I only want to see certain items and then build some sort of custom logic to get a subrange of that data。Now， even though this video series is aimed at the complete newbie。 I don't like to stay in newbie land very long。 So we're going to jump into a little bit more of an advanced topic。

 and we're going to actually filter types。 So when I say filter types， we're talking about classes。 So we're going to filter an animal。And we're just going to make a class real quick here and' going to set your name。My name error。 My keyboard has betrayed me。And we're going to say。Instructtor here。Bear with me super quick as I make some little plumbing code。Get our constructor up and roll in here。

Self dot name。Wells name， All right， now that we've got our animal class。 and I'm not going to make this super complex。We could just take this copy。Haste。 let's call this hat。It's going to inherit animal。And because we're inheriting。 we can get rid of this and we can get rid of this。And it's super simple from here。

 we just say super。Get it super simple。 Anyways， I won't quit my day job。 We're gonna go ahead and initialize it with the name。I could actually spell name。 There we go。 And because I know there's also dog lovers out there。 We're gonna make a dog class as well。 And anybody who knows dogs and cats know， they typically don't mix swell together。

 Although I've been pretty fortunate in life where every dog and cat combination that I've had。 they've just really gotten get along together really well。 So animal。😊，We have a cat。 which is an animal dog， which is an animal， but these are two different classes that don't even know the other exists。This is where the complexity comes in， and you're going to see this time and time again。

What have we just done？Well， we are making a list。That will be called animals。 And we're going to dump at some dogs into the same list。 Some must say poor X in range。And we want from under 10。I should say 0 to 9， but we're going to go ahead and let's say。If。And then we're going to do something a little funky here。 We're going to say x。Moud to。Well 0。

 basically， what we're doing here is we're saying we only want the even number。Then we're going to go ahead and say animals dot append。We're going to make a new cat。And we're going to give it some type of name。 So let's go back up here real quick。 And I'm going to say name equals。Animal。Plus， whatever the number is。All right。

 so once we've gotten to this point， then if it's not even， it is， well， you guessed it odd。 and we can just simply grab this。AndMaybe I should have done that backwards because cats are just odd。 Dos are usually pretty even， but cats are usually really weird。All right， so anyways。 we've got that。Now we're going to go ahead and print out。Are animals。

Just so we can see that we have a mixture of them and sure enough， a bit of godly g on the screen。 but we have cat dog， cat dog， cat dog， cat dog。Very simple。 very easy to understand what we've just done。 We've made a list that contains both cats and dogs and is just a jumbled mass。Now， I want to sort this out a little bit。 Can't say 4 a in animals。

And I'm just going to print this out make it look nice and pretty on the screen。And I'm just having a good day。Enjoying my coffee。And we'll say animal。And super smart of me to do this。 Now， it looks super great。 And I'm going to impress the boss。 and I'm going to get a raise and oh， name。 Yes， cause we hard coded it。Very easy to fix this。Yes。

 my boss is walking around the corner。 I'm going to show him this。 I'm going to save the company millions of dollars。 And sure enough。 I have my nice little collection of animals here。 And the boss says， that's great。😊，But。 I only want cats。And then I only want dogs。 I want two different lists。

 but you have to maintain this single list。Now， I got to write all this code。 Well。 this is where the filter function comes in， as you might have guessed， some must say deaf cats。And we're going to make a cat filter。That just sounds really， really cool。 a cat filter。 So we're going to turn is instance。And I'm going to say， is that value。An instance of the cat class。

That's it， that's really as complex as we need to make this。 we just want to make sure it is an instance。We can do the same thing for dogs。And then we can use that filter function。To utilize these two functions。To their fallalest extent。So I'm going to say4 C in。And then I want to make a list。And we're going to filter。Because remember。

 filter is going to return a filter object。 We need to convert that to a less。 We're going to filter the cats。Using the animals。Slow and way down。 So it makes sense here。We're going to go ahead and print。Actually， I going say cats。And I am going to explain this in case you're completely lost。 Don't worry。All right。

 so what we're doing is very similar to our 4A in animals。 except for we're saying4 C and we're going to make a list from whatever filter gives us and we're telling filter。 use the cats function。And use the animals collection。 Remember animals is a mixture of cats and dogs。And we're just going to say for each item。

 determine if it is a cat， which're is going to return is instance。And then we can do the same thing。Or dogs。Very simple， very easy to understand， and when we run it now we have beautifully separated these。Now， we have cats。And those are the evens， and then we have dogs， and those are the odds。Okay。Prety much sums it up for this video。 main takeaway from this is filter is going to return a alter object。

 We need to pass it a function and some sort of iterable container From there。 it just really needs to return a true or a false。 If it's true。 it's going to end up in the result list。![](img/8136362644f8a25b56808178af805eb5_2.png)
# 【双语字幕+资料下载】Python 3全系列基础教程，全程代码演示&讲解！10小时视频42节，保证你能掌握Python！快来一起跟着视频敲代码~＜快速入门系列＞ - P6：6）Python字符串操作 - ShowMeAI - BV1yg411c7Nw

![](img/09ef0dc5bcb480ff88b22238827c1783_0.png)

Welcome back everyone， this is Brian， we're going to continue our journey on Python 3 and we're going to continue with basic string operations now。When I said strings are complex data types， I was not joking and there's no way we can cover everything in these little two videos。

Especially because we haven't even covered the fundamental logic of programming。 So we have to stick with the basics for now。 Don't worry， later on in the series。 we are going to revisit some of the more advanced things we can do。 But right now。 you have to learn to crawl before you can walk。 So let's start crawling。

I'm going to say variable STR is going to be。Hello world， this is a string。Very。 very simple and we're going to start off with here。What we're going to do in this video is we're going to do things like getting the length of the string。 repeating the string， replacing characters and things of that nature。

 and even slicing them and getting the specific indexes or positions within the string。![](img/09ef0dc5bcb480ff88b22238827c1783_2.png)

![](img/09ef0dc5bcb480ff88b22238827c1783_3.png)

Let's dive into the basic operations。 So first things first。Let's say we want to get the length。 I'm going to say print。 We're going to call the lens function， which is not limited to just strings。 but it is super， super handy for strings。And we are going to against it。 just print out a comment here。Get the length。When we run this。

 we can see this is 30 characters long。 Now， you might be inclined to say in a wait a minute of zero based in。 so it's actually 29。 No， it actually gets the length。 not the position that's fundamentally different as you're going to see later on。So now that we've got the length， we can do other things as well。

 let's say we want to repeat a string。 and this is going to hurt your brain just a little bit here。We've talked about how you cannot do mathematical operations with a string。 Remember。 we were trying to add an integer and a string together。 Well。 you can do what's called string a math。 And this is what I mean by it's going to hurt your brain。

We're going to say SR times 3。Now， I know what you're thinking。You're thinking you're going to get some sort of weird thing because you're trying to multiply。 but actually what you're telling Python to do is take this string。And you guessed it。 multiply it by3 and return a giant string。 Let's demonstrate。Hello world， Hello world， Ho world。

 So it did exactly what we thought it would do here。Yes， the first time I did that。 I kind of SAT back in my chair and went， wait， what is that right。 But it is actually a thing with Python。 If you're coming from another language。 you're probably sitting there just staring at your screen going， what which craft is this？

 But it's actually super handy if you need to repeat a string。Now let's go ahead and let's look at replacing。And if you're coming from another language， well。 this is exactly what you think it is。 It's just dead， simple。So in Python， strings are a de type。 but they're also a first class object， meaning they have functions built right into them。

 We haven't really covered functions yet。 but just know you can say your variable name dot and then call some code。 and we're going to call the replace function。And what this is going to do。It's going to take the string and replace a section of it。 So let's say I want to replace hello。With。Hla， so if you're from Mexico or Spain or any Spanish speaking country。

 that would be the correct way of saying hellla was Holla。I'Pro mispronouncing that。 but you get the point。 you can simply replace it， so。Oah world， this is a string。 makes it super simple to do that。 You don't have to figure out where things are。You can also do something like split a string。 So if you're coming again from another language。

 you've done this before。And I'm going to say SDR， I want to split。And notice how it's looking for a separator here。 So let's go ahead and split this on that comma。If you're not coming from another language， you're like， wait， wait， wait， slow down。 what is splitting， So we're going to take this string。And turn it into two strings。

 and we're looking for a separator value。 in this case， this comma right here。 So it's going to say hello world。 and then this is a string。 and it's going to give us two strings back。Here we go。Hello world。 and this is a string now you may be going， now wait a minute， this comma is here。

Look at these little brackets。 You got this in bracket， this beginning bracket。 What it's done is it's created a data type we haven't talked about yet。 but we will in the next few videos， And it's put two strings into that data type and then handed it to us。 Very convenient way of saying， hey， split those up。As you go on programming。

 you're going to actually use that quite a bit。Now。 let's say we want to know if this starts with something。 so must say SR。And I want to say。 starts with。Does it start with a letter H。I'm almost embarrassed to type that commentt starts with because it's pretty self explanatory what it's doing。 but just in case it's going to return a bull and it's going to tell us hey， yes。

 it does If we switch this to like J Does it start with the J。Alttz。Very simple。 handy way of determining what's going on。We can through the magic copy and paste。 switch this to ends width。And let's say we want to make sure this ends with an exclamation。True。 true。 There we go。And。Let's go ahead and look at uppercase， lowercase and capitalization。

 we're just going to say print。And we want upper。It's going to give us hello world。 This is a string all in uppercase。 You notice how it's got these brackets here。 And that's because it is a function。 If we omit those。 we're going to get a built in upper of string object。 And then this number。

 You ever see something like this。 Basically， what you're trying to do is call a function without。It's brackets and you need those， you're wondering what this number is， that's a location in memory。 so an object is simply something that exists in memory and that's its location。So admittedly。 this message is not super helpful for beginners， but I just wanted to explain what that was。

roundund this out， let's say。Lower， and I want to capitalize。So now we have all uppercase。 all lowercase， and capitalize the way it should be。Let's take a look at slicing and when I first heard this term。 I actually had like this vision of whipping out a lightssaber and slicing something in half。

 and it's actually not far off from what we're talking about。 we're talking about getting a sub string。Now， when I say a substr， remember。 this string is just a series of characters and each one is at a position， so the zero would be here。And then one and so on and so on and so on and so on。

 So what we want to do is get a substr or a slice。 Think of it like you have a pie in front of you and you're going to get a slice of pie。 you're not taking the whole thing just apart。 So for example。 I can say I want the word world or I want just T H out of the word this or this specific space。 Or I wanted to get everything in the end up to that point。 You can do things like that very。

 very rapidly in Python。And this， if you're coming from another language， I'm going to tell you。 is extremely cool once you wrap your head around it。So I're going to say print。And we're going to take our variable。 now we're going to put those brackets there。 that indicates we're getting a slice。The format here is very simple。 We want the start。

A colon and an inposition。So the start position in this case。 we're going to say the0 or the starting position。 and we're going to end in 5。 And what this is going to do is it's going to get the first five。This is a zero based index。 Let's print this out and see what happens here。One， two， three， four。

 five hellello is five letters there we go， so it did exactly what we're trying to do here。Like I said， it looks a little confusing at first， but once you start wrapping your head around it。 it's not super hard。Now I want to start。At the sixth position， and I'm going to omit the ending。And what we're doing here is， we're saying。We want to get from the sixth position all the way to the end。

 so when you emit something， it automatically defaults to the beginning or the end。 depending on which one you o。So the sixth position would be， you guessed it。World。 all the way over here。T works as expected。Let's go ahead and grab this and。Let's try something a little bit different。We're going to start at negative 7。Now， you may be going。

 wait， what negative， how can we have a negative7。Well， when you have a negative。 you actually start from the end。So because we're starting with a negative。 it's going to start back here and count backwards。Actually pretty cool how that works。 so let's run this。And the last seven is string exclamation Prety pretty cool。

 try doing that with some other languages and some are going to be very cool。 some are just going to completely infuriate you depending on the language。And now let's get a substr， we're going to say from6 to 11。And we want to get。6 to 11。 just for our notes here。See what that looks like and it is the world world。Very cool， very simple。

 very easy。Now， if you're coming from another language you're probably still stuck on this right here。 don't worry， whenever you see that negative symbol。 just think you're starting from the end and working backwards。Now， slicing is cool and all。 but it's not super helpful unless you can actually automate the way of getting the number because no one wants to sit here and count things。

 right？So let's look at how to get the index or the position of something。What I'm going to do is I'm going to say L equals。And we're going to look for the comma。 Now if we look at our original string， we've got this comma right here。 but we don't know the position it's at so I'm going to hide that off the screen and we just want to know hey。

 we want to look for this。We're going to do it two different ways。 We're going to say。C equals SDR find This is what I love about Python。 It's very。 very intuitive Fine does exactly what you think it would it finds something。 It's going to tell us what we're looking for is the L and it's going to tell us where it's at。

Or if it doesn't find it， when say negative one， if not bound。Let's go ahead and say print。And I want to say。Fine return。C。Let's run this， see what it does。So whoops。 actually misspelled fine there。 Ey fix。 So find return C。 So it is at the 11th position。 We didn't have to sit here and go 1，2，3，4。 And we'd be here all day doing that。 Instead。

 we want the computer to do the work for us。 So we know this at the 11th position。 Now we change this。To just something。Let's just do a single T。You see fine return negative one。 So in this case， when you see negative one， you can say it's just simply not there。 It's not going to return to 0 because remember，0 is the starting position。So。Findd is really。

 really cool， but if you're coming from another language， you're probably looking for index of。 which is something totally different。So I'm going to say I equal SDR index。We're going to give it the same thing， the L。And now we want to this。And we're going to say find return。Ay， and let's see what this does。 Now， remember。

 we have this tea in here。Where is T in here， It's Well， right there， But it's a lower case。 not an uppercase。 So it should return a negative one， or will it actually， no， it does not。 Instead。 it gives you what's called a value error substr not found。This is a convenient way of saying， hey。 that must exist or throw an error。 something we're going to cover in future videos。

 Just know that find will not return an error。 and index will return an error。 So most of the time you're going to want find。 But if you're coming from another language。 you think you want index and you really want find。S confusing。 Sometimes will， row and air。Just want to make sure we put that in there just in case。And let's switch this back。

And you can see they both return 11。Because we're looking for that comma， remember。 index will throw an error fineablell just simply return a negative  one。Wrapping this up。 let's go ahead and say we want to create a new string from the substring， how do we do that？

So we want to say x equals SDR。 and we're going to slice that string。We're going to o the starting position because we want to go from the beginning。 and we only want to go to the position of this comma。If that seems super confusing。 let's slow way down so we have a string。And it says， hellello world， this is a string exclamation。

 So we're looking for this guy right here， which we found at the 11th position。And we're saying。 okay， so from the very start。Eello world actually just going to copy this whole thing right down here。Copy this， put it right here as a comment。There we go。So we're going to say from the very beginning right here。All the way up to the position we find。

 we want to create a string and call it X。 Now， we want to take that and just simply print it out。Hello world， super， super simple。So quick recap。Stringings are first class objects in Python。 they are Unicode by default there UTF 8， although you can specify some other way of doing it。 Googles your friend if you need to do that immediately。

And you can do some really cool things like get the length， repeat it， replace it， split it。 make sure it starts with ends with upper lower capitalization。 You can slice it， dice it。 do whatever you want to do。 and you can search for or find things within the string。 And if you need to throw an error if it doesn't exist， you can use index。

 which I do not recommend because it's not really a good idea to throw an error in your code most of the time。 and you can create your own strings from substrs very simply very easily。😊。![](img/09ef0dc5bcb480ff88b22238827c1783_5.png)
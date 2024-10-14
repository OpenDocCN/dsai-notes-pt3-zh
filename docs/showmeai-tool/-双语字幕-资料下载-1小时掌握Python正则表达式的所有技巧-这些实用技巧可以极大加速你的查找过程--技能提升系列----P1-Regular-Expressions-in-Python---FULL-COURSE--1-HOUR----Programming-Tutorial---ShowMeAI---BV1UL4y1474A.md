# 【双语字幕+资料下载】1小时掌握Python正则表达式的所有技巧！这些实用技巧可以极大加速你的查找过程~＜技能提升系列＞ - P1：Regular Expressions in Python - FULL COURSE (1 HOUR) - Programming Tutorial - ShowMeAI - BV1UL4y1474A

Hey， guys， welcome to a new Python tutorial Today， I want to show you how we can work with regular expressions in Python。

 Regular expressions or short R E or rex is a powerful method that is used to search for matching text patterns。

 For example， typical patterns that can be extracted from large text files with regular expressions or emails or domain names。

😊，So at the end of this tutorial， you will be able to understand what this regular expression here does。

And theres a lot to cover in this tutorial。 Don't be overwhelmed。

 I promise that once you have understood the concepts， it's not so hard any more。

 and it can simplify and speed up your search tasks a lot。

 So if you watch the whole tutorial and you will be able to understand any pattern that you want to look up。

So now let me quickly show you what we will cover in this video。



![](img/da8ee5de7a086ab699eec08ed957b1f1_1.png)

So， of course， we will see how we work with the R module in Python。

 Then I will show you what methods we have to search for matches。 what we can do with a match object。

 Then we will talk about matter characters and more special sequences that can be used in patterns。

 Then we talk about sets， quantifiers， Con。 And then grouping， then modifications。

 So how we can modify strings with Rs。 And at the end， I show you some different compilation flags。



![](img/da8ee5de7a086ab699eec08ed957b1f1_3.png)

So let's start。 So as I already said， Python has a built in module that is called R E。

 which we can use to work with regular expressions。 So we have to import R R。

 And then we can start working with regular expressions。

 So let me show you a very simple example first。 So let's say， here I have some test strings already。

 So let me copy and paste this here。 So this is our test strings。



![](img/da8ee5de7a086ab699eec08ed957b1f1_5.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_6.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_7.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_8.png)

And now， let's say， for example， we want to search for the pattern ABC。

 So we see we have this three times here。 And now let's say we want to look for ABC。

 and we create a pattern。 So let's say pattern equals。

 and then we use the R E module and the compile method。 And then here we say R。

 and then the string ABC。 So I we'll explain what R means in a second。

 And then we can use this pattern to find matches。 So we say matches equals pattern dot find iter。

 And then we want to find the matches from the test string。

 And now this will be a object that we can iterate over。 So we can say for matches in matches。

 And then we simply。

![](img/da8ee5de7a086ab699eec08ed957b1f1_10.png)

Print the match。So now let's run this。 And then we see we have two matches。

 So this is a match object。 and we can see more details。 So， for example， we can see the span。

 So this is the start and the end position。 So this is 3，4 and 5。😊，And this is our match， ABC。

 and a second match at position 12。 So this is position or index 12 in our string。

So we see that we have two matches here。 and what we also see here that our regular expression is k sensitive。

 So it doesn't include the。Uppercase ABC into our matches。 So this is one thing that we must know。



![](img/da8ee5de7a086ab699eec08ed957b1f1_12.png)

So one thing that I want to mention here is that instead of compiling our pattern explicitly。

 we can use the find It method directly on the R E module。

 So we could also just write that our matches equals R E dot find Iter。

 And then we want to look for our， let's say， string R ABC， And then from our test string。😊。

So you can use it directly on the R E module。 And then we will， if we run this。

 we will see that we get the same results。 So there is not much。



![](img/da8ee5de7a086ab699eec08ed957b1f1_14.png)

Of a difference here。 But I prefer to do it this way to explicitly compile the pattern and bind it to this object here。

 So this improves readability and is also a little bit more flexible。So I prefer it this way。

 but you should know that you can use both ways。

![](img/da8ee5de7a086ab699eec08ed957b1f1_16.png)

And now let's talk about the why I'm using this R here briefly。

 So this means that this is a raw string。So， for example。

 if I have a string A and this includes some special characters like a tap。

 So a backslash T that this is a tap or a back slash N for new line。 And then I have a string。

 So now if I print this。 Then you will see that we have the tap here at the beginning。

 So it didn't print the backslash T。 And in a pattern。

 I usually want to look for the actual characters in my pattern。 So then I can write an R here。

 And then this means that this is a raw string。 So Python will print this the same way as it is specified here。

😊，And yeah， so I recommend to always use a raw string for your patent。

 You can use just a normal string， but remember that you should use a raw string。



![](img/da8ee5de7a086ab699eec08ed957b1f1_18.png)

And yeah， so this is a short example how a regular expression is used。

 So typically we come up with our pattern， then we compile it。

 and then we use the pattern to find our matches。 And I will show you the different methods that we have on the matches now。

 So now let's go over the methods to search for matches。 So we already have seen the find iter。



![](img/da8ee5de7a086ab699eec08ed957b1f1_20.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_21.png)

methodethod and this will give us a match object。 and I will show you what we can do with a match object in a second。

 So now let's talk about the other methods。 So there are three other methods。

 So we can use the dot match method。 So here dot match。 Then we have search。

 and then we also have find all。 So。😊，Now， let's look about the find all method first。

 So if we can say pattern dot find all， then we will simply get the string。 So if you see here。

 I'm printing the whole match object。 So now if I want just a string， then I can use find all。

 and now if I run this， then it will just print the two strings that I'm looking for。



![](img/da8ee5de7a086ab699eec08ed957b1f1_23.png)

So this is defined find all methods。Now， the match method determines if the expression matches at the beginning of the string。

 So this will only return one match。 So here I can say match equals pattern and then match。And now。

 if I print the match， So let's print。The match and run this。

 Then we will see this is none because the match looks only for patterns at the beginning of our string。

 So ABC is not at the beginning。 So now if I use 1，2，3 as a pattern。

 then we will see this is at the beginning， So this will return one match。

 And we also have the pattern here again。 But again， the match does only return the first。



![](img/da8ee5de7a086ab699eec08ed957b1f1_25.png)

Match if it is at the beginning of the string。And now we also have the search method。

 so the search method scans through the string and looks for any location where the RE matches。

So if you use， for example， let's look for the match ABC again。

 Then we will see this will return none because ABC has to be at the beginning。

 And now if we use the search method， then it will find the match object again。

 And it will simply return the first match。 So we have search， match， find all and find iter。

 And this is my preferred method。 So from now on， I will only use this one。

And then we also have some function that can be used to modify an object。

 So we also have split and s。 So I will come to them later。

So now let's continue using the find iter method。 and let's have a look at what we can do with the match object。

 So again， let's say our matches equals pattern。 and then find iter。

 and then let's iterate over this。 So for match in matches。 and then we want to print the match。



![](img/da8ee5de7a086ab699eec08ed957b1f1_27.png)

Then。

![](img/da8ee5de7a086ab699eec08ed957b1f1_29.png)

Again， we see we have the whole match object here， and we can use four different methods on this so we can use the group method。

 We can use the start and the end method。And we can get the spam， so。Let's start with the span。

 So this will give me the。Start and the stop index where this pattern is located。

 So let's print the match dot span。 So then we simply get this as a tuple here。So。We get 3 and 6。

 So this is a tuer， and we can also get the。Just the start and the end right away by saying print match dot start and。

Print match dot。And。Oh， sorry。 Here is I dot match dot start。

So then we get the start in the stop index。 And now let's talk about the group method。 So now。

 if we call match dot group， then we will get or print the。Actual string of the match。

 And we can also give this group method arguments to find the group 0 or  one and or 2。

 And we will talk about this grouping later。 But for now on。

 if you just want the string then from the match， then just call match dot group or group 0。

 So this is the same。😊，And yes， these are the four different methods that we can use on a match object。



![](img/da8ee5de7a086ab699eec08ed957b1f1_31.png)

And now let's come to the meta characters。 So in regular expressions。

 there are these me characters that have a special meaning。

 So these are all the me characters we must know。 And you don't have to know them by heart。

 So I recommend that you keep a cheatee sheet somewhere with all this stuff。

 And I will also provide a cheat sheet on my website。

 So you can check it out on Python minuseng dot com。 And this is all you need to know。😊。



![](img/da8ee5de7a086ab699eec08ed957b1f1_33.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_34.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_35.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_36.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_37.png)

So now let's talk about these me characters one by one。



![](img/da8ee5de7a086ab699eec08ed957b1f1_39.png)

And then I will show you what this means。 So the first one is the dot。

 So the dot means that we want to look for any character。

 So any character except a new line character， then the carrot means that we want to look for a pattern that starts with that starts with the pattern we are looking for。

 So that starts with a string。 hello， for example， then the dollar sign is the opposite。

 if we want to look for a string at the end of our text。



![](img/da8ee5de7a086ab699eec08ed957b1f1_41.png)

Then we have some quantifiers。 So the asterisk， the plus and square brackets。

 and I will talk about them later in more detail。

![](img/da8ee5de7a086ab699eec08ed957b1f1_43.png)

Then we have the set operator， which I will also cover later。Then we have conditions。

And grouping with parentheses。 So I will also talk about this later。 And， of course， we have to look。

 we have the back slash。 So with the backlash， we can get more special sequences or we can escape character。

 So， for example， if we actually want to search for the dot。

 Then we have to escape this in our pattern。

![](img/da8ee5de7a086ab699eec08ed957b1f1_45.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_46.png)

So now let's talk about the first three and show you some examples。



![](img/da8ee5de7a086ab699eec08ed957b1f1_48.png)

And then later， we will cover the other meta characters in more detail。 So now， first。

 let's say we want to look for the dot and then print all the matches。 Then we see we get all。



![](img/da8ee5de7a086ab699eec08ed957b1f1_50.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_51.png)

All the characters in our string， because the dots is looking for any character， except new line。



![](img/da8ee5de7a086ab699eec08ed957b1f1_53.png)

So， this is the dot。And now， let's say we have a dot here at the end。

 And we actually want to get this dot。 So then we escape it with a back slash。 And now。

 if we run this， then we just get the dot。 So now let's print the whole match object。



![](img/da8ee5de7a086ab699eec08ed957b1f1_55.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_56.png)

Then we get the dot， and we see that it is at this position。 So this is the dots。

 And then let's have a look at the carrot。 So this is the carrot。

 So let's say we want to look for  one to 3。 if it starts with this。And then we get one match object。

 And for example， now， if we look for ABC， then it will return nothing because it's not at the beginning。

 And the opposite， if we want to have a look， if we want to look if this is at the end。

 So then we can say dollar here。 And now if we run this。 and this will find nothing because again。

 sorry， we have the。AndCo on here。This will find nothing because， as I said， it is case sensitive。

 Now， if I am looking for upper case， ABC and dollar at the end。



![](img/da8ee5de7a086ab699eec08ed957b1f1_58.png)

So then it found the match at the end。

![](img/da8ee5de7a086ab699eec08ed957b1f1_60.png)

Alright， so now we will talk about the other meta charactersers later。

 And now let's look at some more special characters。

 So there are more special characters that start with a backlash。

 So there is the back backlash and small D， this looks for any ditchit。 So0 until 9。

 Then there is the capital backlash capital D。 So this matches any nonditchit character。

 Then there is backslash small S。 This matches any white space character， For example。

 space tap or new line。 Then we have backslash capital is S。

 this matches any nonwhitespace character。 So for all these patterns， all these special characters。

 the capital pattern is kind of the opposite of the small character here。😊。



![](img/da8ee5de7a086ab699eec08ed957b1f1_62.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_63.png)

So then we have backlashlash small W。 This matches any word character。

 So we have characters from a to C。 We also have all the capital characters。

 and also ditches and the underscore。Then the capital Ws the opposites of any non word character。

 non alpha numeric character。Then， we have the。Back slash B。

 So this matches where the specified characters are at the beginning or at the end of a word。



![](img/da8ee5de7a086ab699eec08ed957b1f1_65.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_66.png)

And again， we have the opposite。 So where this is not at the beginning。

 So let's have a look at them in detail。

![](img/da8ee5de7a086ab699eec08ed957b1f1_68.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_69.png)

So let's use another test string here。 So let's， for example， use this one。



![](img/da8ee5de7a086ab699eec08ed957b1f1_71.png)

And now， if we want to look for any ditchit here， we can simply say we want to look for back slash D。

 And now if you run this， then we will see we have three matches， the dts 1，2， and 3， Now。

 if we use the opposites So capital D's or any non ditchit。

 then it will find all the characters except 1，2， and 3。



![](img/da8ee5de7a086ab699eec08ed957b1f1_73.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_74.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_75.png)

Then let's have a look at the white space。 So backslash S finds any white space character。

 So here we see we have a space here， a space here and a space here。 And then again， the opposite。

 any non white space character is any other character。😊，So this is the S special character。Then。

 let's have a look at。

![](img/da8ee5de7a086ab699eec08ed957b1f1_77.png)

the。W character。 So any alphanumeric character。 So if I put in a W here。

 then it finds all the word characters。

![](img/da8ee5de7a086ab699eec08ed957b1f1_79.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_80.png)

And again， the opposite capital D， This will just find the spaces in this example。

 And now let's have a look at the。

![](img/da8ee5de7a086ab699eec08ed957b1f1_82.png)

back slash。B， so now if I am looking for hello， then it will find it because it is at the beginning of a block。

And a block is not only the beginning of a string， but the beginning。

Of any block that follows a white space character。 So， for example， if we look for。Hey。Then。

 it will also find there。嗯。Hey， but it will only find this pattern and not this one。

 because it's looking for matches that are at the beginning of a block。So for example。

 if we put this。Before a space， then it will find。Then it will find this pattern or this match， too。

And again， the opposite。 Now， if we are looking for this and we put。Oh， he here again。

Then it will find this hay， because it is not at the beginning of a block where this is at the beginning of a block。



![](img/da8ee5de7a086ab699eec08ed957b1f1_84.png)

So these are the special sequence， special characters that we should know。



![](img/da8ee5de7a086ab699eec08ed957b1f1_86.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_87.png)

And now， let's continue with sets。

![](img/da8ee5de7a086ab699eec08ed957b1f1_89.png)

So we can use square brackets to look for sets。 And let me show you what this means。

 So let's say we only have this string now。 But now， let's say we only want to look for。



![](img/da8ee5de7a086ab699eec08ed957b1f1_91.png)

And nonnumeric characters。 So only for these ones， then we can use a set for this。

 So a set is a pattern between square brackets。 And now here in this set。

 we can use multiple multiple characters that we want to look up。 For example。

 we want to look for a L and a O。And now， if we run this， then it will find all these characters。

And you must be careful here because it doesn't look for L O。

 but for any single character that we put into this set。And we can also specify ranges here。 we can。

 instead of， let's say， we also want to have the H and the E。 Then it will find any。



![](img/da8ee5de7a086ab699eec08ed957b1f1_93.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_94.png)

Character here。That is not a number。And also， not the backlash not the underscore。

 So we can also specify a range here。 And this is a very typical。

 very common example and regular expressions to use a dash C。 So A to C。 So all the。



![](img/da8ee5de7a086ab699eec08ed957b1f1_96.png)

Lower case characters。 Now if you run this。Sometimes it's not saving this file automatically。 So now。

 if you run this， then we see that we will find。

![](img/da8ee5de7a086ab699eec08ed957b1f1_98.png)

All the。

![](img/da8ee5de7a086ab699eec08ed957b1f1_100.png)

Letters here。 And we can also look for dits。 So let's say we want only the ditits 2 and 3。 And again。

 here， we can have a range。 So we can say 1 to 9。 So this is， or let's say0 to 9。

 And this will find all the ditches。 So this is the same as using back slash D to find a ditit。



![](img/da8ee5de7a086ab699eec08ed957b1f1_102.png)

And so， yeah， so if you want to specify a。Range， then the the dash can be used to。

 to declare to define the range。 And now if you use it after a range。

 then it's looking for the actual dash。 So now if you also want to look up a dash。

 then we can find it here。 And if you put it between two things， then it is a range。

 So be careful here。And we can also。Right our different range is back to back。 So for example。

 if you have。Hello here in upper case letters。 And first of all。

 let's say we only want the lower case letters。 And then we also want to have all the uppercase characters from A to C。

 Then we can write this back to back so we can say small， A to C or a dash C， then capital a dash C。

 Then this will also include all the uppercase characters。 And again。

 we can use back to back and also include numbers。

![](img/da8ee5de7a086ab699eec08ed957b1f1_104.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_105.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_106.png)

So， yeah。 then it also finds the numbers here。 So the ditits。 So， yeah。

 so this is how we can use sets with this brackets。



![](img/da8ee5de7a086ab699eec08ed957b1f1_108.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_109.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_110.png)

And now let's talk about quantifier。 So we have these quantifier， the meta characters。

 So we have a an asterisk。 So a the the multiplication sign。 This means0 or more。

 Then we have the plus this means one or more。 Then we have the question mark。 So this means0 or one。

 And this means， or this can be used when we want to look for an optional character。

 So it may be there， but it may also be not there。

![](img/da8ee5de7a086ab699eec08ed957b1f1_112.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_113.png)

Then if we want to look for a specific exact number， we can use curly braces。

 and then a number here will look for the exact number。

And then we can also specify a range with minimum and maximum。

 So if we put two numbers between the curly braces， then it's looking for a range。



![](img/da8ee5de7a086ab699eec08ed957b1f1_115.png)

Okay， so let's have a look at them in detail。 So let's say we have a string。 let's say hello。

 underscore 1，2，3。 And now let's say we want to have or we want to find diits。 And remember。

 we can do this with with backlashlash D。 and then it will find all the digits。

 and let's say we want to look if we have0 or more。 So then we use an asterisk。

 And then it will also find all the other characters here。 because here there is no diitchit。

 but it was looking for0 or more。 and in this case， our match is just an empty string。😊。



![](img/da8ee5de7a086ab699eec08ed957b1f1_117.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_118.png)

And then again， an empty string， empty string， empty string。 And then here we have diitchits。

 and then it will combine them into one match。 So now， if we just use the。

And use it without a quantifier。 Then it puts any every single ditchit S one match。

 And if we want to look for0 or more， we can use this with an asterisk。 And now in this case。

 a plus is better。 So we want to look for one or more。 And then we will see it has only one match。

 and it combined all the ditits into one match。 Then let's say we want to look for a diitchit that has an underscore in front of it。

 So let's say we want to look for underscore and then the diitchit。 then it will find the one。

 And but now let's say we don't know if there is an underscore or not。

 So now if the string looks like this。 And then if we run it， then it doesn't find a string， a match。

 And then we can say that the underscore is。

![](img/da8ee5de7a086ab699eec08ed957b1f1_120.png)

Optional by using the question mark。 And now if we run it， it finds all the matches。

Because it doesn't has an underscore。 And now， if we do it like this。

 then it will find the same matches because it can also have an underscore here。

So this is the question mark。And now let's talk about specific ranges or or a specific number of， of。

Characters， so now if you want to look for three ditits。

 then we can see a dititchit and then curly race and then 3。 Then it will find our match。

 So now if we are looking for four of the ditits and runners， then we don't have a match。

 and we can also use a range here。 So this can be can be between one and 3。

 and then it will also find the match。😊，So these are the quantifiers。 Now。

 let's stop for a second with all the concepts and just make or just do an example。

 So let me copy this。

![](img/da8ee5de7a086ab699eec08ed957b1f1_122.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_123.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_124.png)

String here。 And now let's use some of the concepts that we already know。

So let's say our string is now the date string。 So this is dates in different formats。 So。

 for example， here， we have the day then the month and then the year。

 and this is separated by a colon。 Then here it its the year first。 then a colon。

 Then here we have year month and day separated by a dash。 Then here by a s。

 and also by an underscore。

![](img/da8ee5de7a086ab699eec08ed957b1f1_126.png)

And now， let's say， we only want to extract。The dates with this format so year， month and day。

 and only with a dash in between， so。

![](img/da8ee5de7a086ab699eec08ed957b1f1_128.png)

Let's do this so。The first thing we can do is now here is to look for。



![](img/da8ee5de7a086ab699eec08ed957b1f1_130.png)

This patterns of 4，2。 and again， two ditits。 So we can write this up。 So backlash D， backlash D。

 back slash D。 And then let's say， first of all。

![](img/da8ee5de7a086ab699eec08ed957b1f1_132.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_133.png)

We want to look for any character between。 So remember， the point is a meta character。

 So this is looking。 if we have a look at this here， this is looking for any character。

 except new line。

![](img/da8ee5de7a086ab699eec08ed957b1f1_135.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_136.png)

Then we have two diits。 So backlashlash D， Then again， we can have any character and then D and。



![](img/da8ee5de7a086ab699eec08ed957b1f1_138.png)

Back slash D。 So， for example， if our string has also some text in it。 and now if we run this。



![](img/da8ee5de7a086ab699eec08ed957b1f1_140.png)

Now， it's called dates， the string。 Now， if we run this， then it will find all the。



![](img/da8ee5de7a086ab699eec08ed957b1f1_142.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_143.png)

嗯。All the statess with， with the numbers。 but only in this format。 So 4，2，2。 So， for example。

 it didn't put the text here， the hello text in here。

 and it didn't put this date in here because it has a different format。



![](img/da8ee5de7a086ab699eec08ed957b1f1_145.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_146.png)

So， now。This is our first try。 and now what we can do here is， for example。

 the next thing we want to do is to find only these in this format。 So now let's have a look at。

 So let's exchange the dot by a dash。 So this is looking for an actual dash。

 And then we have only the dates in this format。

![](img/da8ee5de7a086ab699eec08ed957b1f1_148.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_149.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_150.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_151.png)

So 4，2 and two numbers separated by a dash。 And let's say we this may also be a valid date。

 So we can also looking for a slash as an separator here so then we can use a set。So remember。

 a set is defined in square bracketets， and then we can define the characters that may be at this position。

 So， for example， we have a dash and we have also or may have a slash。 And again。

 here we are using a set。 So then we have dash slash。And are closing our set。 And now。

 if we run this again， then we see。

![](img/da8ee5de7a086ab699eec08ed957b1f1_153.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_154.png)

3， we see that this is also included in the matches。 And now， let's say， for example。

 we are looking only for dates in May or June。 So how do we do that， So the month here。



![](img/da8ee5de7a086ab699eec08ed957b1f1_156.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_157.png)

So what we do here is now， this is not。

![](img/da8ee5de7a086ab699eec08ed957b1f1_159.png)

Any diitchit。 So here we are only looking for month。



![](img/da8ee5de7a086ab699eec08ed957b1f1_161.png)

0，5 and 0，6。 So we always have a0 here， and then we can again use a set。

 And here we can use let's say only 5 and 6。 And now if we run this。

 and we only have the dates in May or June。 And remember， we can also use a range here。

 So let's say we want to have May， June and July。 then we can say 5 to 7。



![](img/da8ee5de7a086ab699eec08ed957b1f1_163.png)

And then we have all the dates from May to July。And now let's use a quantifier here。

 So instead of writing for D's here， backslash D， we can say D and then curly braces and use the quantifier for。

 So we want to have exactly four ditits here。 And here we want to have exactly two diits。

So then we can do it like this。 So this finds all the dates in。And May June or July in this format。

 So this is one typical example， how regular expressions are useful。



![](img/da8ee5de7a086ab699eec08ed957b1f1_165.png)

And yeah， so now let's continue。 So we already covered a lot here。

 So let's talk about conditions next， so。

![](img/da8ee5de7a086ab699eec08ed957b1f1_167.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_168.png)

Let me copy another string and to another example。 So here I have another string with some names， so。



![](img/da8ee5de7a086ab699eec08ed957b1f1_170.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_171.png)

Let me copy and paste this year。 This is my new string。 So here we have a Mr。 Simpson。

 a Mrus Simpson， a Mr。 Brown， a Miss Smith and a Mr。 T。

 And sometimes we have a dot between Mr and sometimes not。And now， let's just extract all the。

Different names here。 So， for example， there is some more in our file。 So， for example。

 we have hellello world。

![](img/da8ee5de7a086ab699eec08ed957b1f1_173.png)

1，2，3。Date。嗯。And now we only， we want to extract only the names， and we want to have the whole name。

 So let's build up our pattern here。So let's look for Mr first。 So first， we want to look for a Mr。

 So M。 And then we have a whitespace。 So back slash S。 And then we have one or more character。

 So word character。 So here we use a back slash W。 And then we say plus。 So this， remember。

 this is a quantifier， So one or more。 And then I'm looking for the my string here。

 and I don't actually write the space here because I have this back slash S。 And now if I run this。

 then we see that we have one match here。 So this is our Mr。 Simpson。 So here we have the M R。

 and then a space。 And then。

![](img/da8ee5de7a086ab699eec08ed957b1f1_175.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_176.png)

1 or more word characters。 And now， as a next step。

 let's also include a Mr where we have the dot here。So。We can have the dot。

 And now if you just write it like this and run it。Then it finds。 sorry。

 I have to use back slash dot， of course， here， because it's looking for an actual。

 I want to look for the actual dot。

![](img/da8ee5de7a086ab699eec08ed957b1f1_178.png)

And now it only finds Mr。 Brown and Mr。 T， but not Mr。 Simpson any more。 So now， as we just learned。

 we have the optional quantifier with a question marks。 And now let's make our dot optional。

 And now if we run this。 Then we have all the Mr。

![](img/da8ee5de7a086ab699eec08ed957b1f1_180.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_181.png)

And now let's talk about where conditions are useful。 So in this case， we may not only have Mrer。

 but we may also have a miss or a misses。 So then we can use a condition。 So we use parentheses here。

 And then we separate them。

![](img/da8ee5de7a086ab699eec08ed957b1f1_183.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_184.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_185.png)

So let's have a look at this here。 This meta character is the either or。 So now， if we used this。

 we can write Mr or miss。

![](img/da8ee5de7a086ab699eec08ed957b1f1_187.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_188.png)

Or missus。 And then if we run this， then we see it extracted all the names from this text。



![](img/da8ee5de7a086ab699eec08ed957b1f1_190.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_191.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_192.png)

So this is where a condition is useful。And as we have just seen， we grouped this condition。

Together with the parentheses。 So this is， again， one meta character。

And now let's talk about grouping a little bit more。 So let's do another example for this。

 This is also a typical example So let's copy some emails into our text。

 and let's say we only want to extract the emails from this string here。 So again。

 let's build up our pattern。

![](img/da8ee5de7a086ab699eec08ed957b1f1_194.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_195.png)

So what we can do here is we can use sets to do this。So let's build this up。

 So let's say we want to have some characters here。 So this may be word characters。

 but this may also be a dash and numbers。

![](img/da8ee5de7a086ab699eec08ed957b1f1_197.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_198.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_199.png)

So let's use a set here。 and let's use back to back ranges here so we can use small a to C or capital a to C。

Or also the diitchit 0 to 9。 or we may also have a dash here。

 So now we are you looking for any of these characters here and we want to have multiple of them。

 So we say we want to have multiple。 So one or more。 So this combines this group into one match。

 and then it is followed by an at sign。 So now if we compile this and run this。

 then we see that it extracted all these patterns here with any words or numbers or dashes and then an at sign。

 So this is the name before the email and then。

![](img/da8ee5de7a086ab699eec08ed957b1f1_201.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_202.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_203.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_204.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_205.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_206.png)

Our email can have different domains。 So for example。

 we have at Gmail dot com at Gm X dot D or at my domain or my dash domain do org。

 So we want to extract all the different domains。 And the next thing we want to look is to look for only for word characters。

 So the domain doesn't have a diitchit in it。So the only allowed characters are。

 let's use another set， and here we use again， maybe be a to C， capital A to C， and also a dash。

 and then we have the dot。So now let's run this。 And， of course， there are again， one or more。

 So here I have to do a plus。 and then it's looking for one or more。

So now we see our match also includes the domain name and the dot。And then here at the very end。

 let's do another set。 So here we say our ending， for example， we can say here we have dot。嗯。Sorry。

 again， I missed。 I was not looking for an actual dot here。 So this is a typical mistake that I make。

 So now it， for example， it would have also found this one here。

 but this is not a valid email address。 So I have to look for the actual dot by using the back slash。

And then let's say I'm looking only for dot com， but it can also be dot D or dot org。 So。

 for example， I can use a group here by using parentheses。

 and then use the condition here Com or D E or dot org。

 So now it would only find these endings here and now let's not use a condition。

 but I just wanted to show you the condition here again， but we can also just use a set here。

 So let's use the set。 and again here we may have。A to C and A to C in capital。 And then one or more。

And。No ditits here。 So now if you run this， then this will extract all the emails for us。

 So this is a typical regular expression pattern to look for emails。

 And this is what I showed you in the beginning。

![](img/da8ee5de7a086ab699eec08ed957b1f1_208.png)

So now you understand what this means。 and now let's talk about grouping a little bit more。

 So there was one case just where I used the condition。

 and then I have had to use parentheses but we can also explicitly group our match object here into different substrs。

 So for example， I can put all of these before the a sign into a group。 So now let's use parentheses。

 and then。

![](img/da8ee5de7a086ab699eec08ed957b1f1_210.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_211.png)

Let's use the a sign。 and then let's use the domain name。 So this is one group until the dot。

 And then we have one group to have the ending year。And now we have three groups here。

And as I showed you in the beginning， now， if we run this， then this will give the same results。

 And here we are printing the whole match object。

![](img/da8ee5de7a086ab699eec08ed957b1f1_213.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_214.png)

And then we can use the dot group to return the actual string。And this is by default。

 This is group 0。 So this is the whole match string。

 But now we can also print the single groups that we just defined。 So we， for example。

 we have group 1，2 and 3 now， and now if we run this and print this， then we see。



![](img/da8ee5de7a086ab699eec08ed957b1f1_216.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_217.png)

Let's just print the group one for now here。 Let's comment this out too。

 Then we see it only prints this group here。 So only the name of the email before the Ed sign。

 then here， this is the second group。 So now if we print the group 2， then this is the domain name。

 And if we want to have the ending。

![](img/da8ee5de7a086ab699eec08ed957b1f1_219.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_220.png)

Then we can print group 3。 So this is where grouping is useful。

 If we only want to have a look at specific things in in our match， Then we can use parentheses。

 Now let's move on。 So now let's see we talked about grouping。 Now， let's talk about modifications。

 So we have two methods to modify a string， So we have the split method and we have the sub method。

 So let's talk about both of them。 So the split method will split the string into a list and splits wherever our regular expression matches。

 and the sub method will find all substrs where the regular expression matches。

 and replaces them with a different string。😊。

![](img/da8ee5de7a086ab699eec08ed957b1f1_222.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_223.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_224.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_225.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_226.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_227.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_228.png)

So let's look at two examples。 So let's say， let me grab a string here， so。



![](img/da8ee5de7a086ab699eec08ed957b1f1_230.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_231.png)

Let's use this one， again。So this is our test string。

 And now we use the pattern equals our E dot compile。 And then we are looking for the raw string 1，2。

3。

![](img/da8ee5de7a086ab699eec08ed957b1f1_233.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_234.png)

嗯。Oh， sorry， let's use a different one。 Do I have it here， No， let's write it myself。

 So let's say ABC，1，2，3。A，B，C， D， E， F， and capital letters， again，1，2 3 and ABC。

 And now let's say this is our patterns，1，2， and 3。And now we say our split it equals。

 and then we say pattern dot split and give the test string as argument。

 And now let's print the split it。 Now， this will be a list。Where our string split it oh， sorry。

 this was a bad example。 So let's use ABC as split。

 And then we have splits where it split it our string into different substrs。

 and used this pattern here as the split。 So here as the matching split So here it has ABC。

 So it split our string into this part。 So there we have one to 3 And then this part。

 And then it found our pattern again， ABC。 And then again， it split the string。 And then at the end。

 we have the rest of the string。 So this is the third substr that it found and。

And returned with this split method。 So this is the split method。And now。

 the sub method with the sub method， we find。All the substrs where our pattern matches and then replace them with a different string。

 So let's say our testing string equals hello world。😊。



![](img/da8ee5de7a086ab699eec08ed957b1f1_236.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_237.png)

And then let's say you are the best world。And use the， so we use the word world two times。

 And then let's say we want to look for the pattern world。

 So we say pattern equals our E dot compile。 and then an R raw string。 And here we have world。

 And then we say our spt string equals， and then we use pattern dot sup。

 And then what we want to put in as replacement。 Let's say we want to put in planet。

And we also have to put in the test string。Now， it took our test string。

 looked for all the matches where pattern matches。 it looked for world and replaced them with planet。

 So now this will return another string that was modified。 And now if we print this。

 Then we see it printed Ho planet， you are the best planet。 So this is the sub method。 and。😊，Now。

 let's do another example to combine all that we have learned。



![](img/da8ee5de7a086ab699eec08ed957b1f1_239.png)

And again， use the sub method。 And yeah， so let's do this， so。



![](img/da8ee5de7a086ab699eec08ed957b1f1_241.png)

So let me grab this string here。 So this is our URL string。 So here we have， again。

 let's say we have different things here。

![](img/da8ee5de7a086ab699eec08ed957b1f1_243.png)

And then we are only looking for URLs， but they may have different formats。 So for example。

 we have an H TTP URL an H TTPS URL， and then sometimes we have a WwW。

 and sometimes we don't have this。And then we have the typical domain name， and。



![](img/da8ee5de7a086ab699eec08ed957b1f1_245.png)

Ending。

![](img/da8ee5de7a086ab699eec08ed957b1f1_247.png)

So， yeah。 So let's extract this。 So let's build up our pattern again So pattern equals R E dot compile。

 and then a raw string。 So now let's start by saying it starts with H T T P。

And then a colon and two slashes， and。Then we have W， W， W， and then we have a dot。 So an actual dot。

And then， we have。1 or more were characters， so。For example。

 we can use a set here again and use a to C and upper case a to C and also a dash here。 So like here。

 And so then we have a plus So one or more。And let's put this into a group here right away。

 So this will return the same thing。 And then we can later use this group here。And the next thing。

 we again， have a dot。 So back slash dot。 And then again。

 we can use a setier a to C and capital a to C。And now let's try this out。

 So let's say matches equals pattern dot find either。 And then we call this URL。

 And then for matches in matches， we want to print。



![](img/da8ee5de7a086ab699eec08ed957b1f1_249.png)

The match。 and let's try this and run this。 And then we see we made some mistakes here。

 And this is because here I have to say plus of course， a one or more and now it only found this URL。

 because it didn't find this one because we have H Ttps here。 and this one doesn't have www。

 So the first thing we can do here is to use an S。 and this is an optional S。

 So remember S question mark So this is optional then and if we don't put this into a group。

 then the question mark will only refer to this character here So now let's try this out And now we see it also found the H Ttps URL。

 and now the same thing。

![](img/da8ee5de7a086ab699eec08ed957b1f1_251.png)

With the Www So this may be there or may not be there。 So again， let's put this into a group。

And then use an question mark to make this optional。 And now if we run this again。

 then it still doesn't find it。 And this is because our， it must be W W dot。

 So back slash dot which must be optional。 And then I don't need it here anymore。 So let's run this。

 And then we see that it found all of the URLs and extracted them。

 And now let's say our string has only the URLls here。

 And now let's say we want to return a new string where we replaced all of these optional beginnings。

 So it should only print the actual domain name with the ending。



![](img/da8ee5de7a086ab699eec08ed957b1f1_253.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_254.png)

So as we have learned， we can use the s method。 So we can say instead of just finding the matches。

 what we want to do here is， let's also print this。 And then let's say our spped URL else equals。

 and then we use pattern and then sup。 and then what we want to put in the replacement here。

 So for example， if we just say hello， and then U else as a string and then print。



![](img/da8ee5de7a086ab699eec08ed957b1f1_256.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_257.png)

The spt URL。 So then we see that this is the new string here。

 So it replaced all of the matches with hello。 And now， let's say we only want to put this。



![](img/da8ee5de7a086ab699eec08ed957b1f1_259.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_260.png)

In our string and only this， then what we can do here is we can group this， and we already did this。



![](img/da8ee5de7a086ab699eec08ed957b1f1_262.png)

So。We have a group here。 We have a group here。 and let's also put this into our group， into a group。



![](img/da8ee5de7a086ab699eec08ed957b1f1_264.png)

And then what we can do is we can use back references to replace them。

 So here we can say back slash 2 and。We must use a string， So a raw string。

And then we say back slash 2 and back slash 3。 And now if we run this， then this is our new string。

 So if I comment this out， then we see then this is our new string。 and what happened here， again。

 if we have a look at the group。 So we can say let's print all the different group。

 So we have matched that group， So this will be the whole。



![](img/da8ee5de7a086ab699eec08ed957b1f1_266.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_267.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_268.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_269.png)

String。

![](img/da8ee5de7a086ab699eec08ed957b1f1_271.png)

And now so this is group 0 again。 Now， let's have a look at what is group 1。 So， for example， here。

 this is the group1， the first one in parentheses。 And because this may be optional。

 this may also be none。 So the first URL L has none as the first group because it doesn't have W， W。

 W。

![](img/da8ee5de7a086ab699eec08ed957b1f1_273.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_274.png)

And this is the first group。 So now let's print the second group。

 So this is the actual name of the domains at the beginning。

 And then the group 3 is the endings So dot com dot com dot net。

 And now here we use this group2 and group 3 with this back reference。

 And then replace the whole found pattern only with the domain name。 So this is what happens here。

 And so this is also very often used in regular expressions。 And now you know what this means。



![](img/da8ee5de7a086ab699eec08ed957b1f1_276.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_277.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_278.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_279.png)

And I guess， now we are almost。

![](img/da8ee5de7a086ab699eec08ed957b1f1_281.png)

Through with all the context， all the。

![](img/da8ee5de7a086ab699eec08ed957b1f1_283.png)

Things that I wanted to show you。 And now， as a last thing。

 let's quickly talk about compilation flags。 So when we compile the pattern。

 Then we also have the option to use different compilation flags。 So here I listed them。 And again。

 you don't have to remember them。 Just keep a cheat sheet。

 So here we have the different compilation flag。 So askki dot all， ignore case。

 local multi line or verse。

![](img/da8ee5de7a086ab699eec08ed957b1f1_285.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_286.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_287.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_288.png)

So I recommend that you check out the official documentation to see what all of them mean in detail。

 And now I。I just want to show you the ignore case compilation flex。

 So this is also a very common use case。 So let's say we have the string。

 my string equals hello world。 And then we want to look for the string world。



![](img/da8ee5de7a086ab699eec08ed957b1f1_290.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_291.png)

And now， if we compile this and then try to find the matches and print them。 So print the match。 Now。

 if we run this， sorry， this is called my string。 now if we run this。 then it doesn't find a string。

 So because remember this is case sensitive。 Now if we make a capital W。

 then it finds the match world。 And let's say we don't know what our string is。

 So it may be upper case， but it may not be upper K。 So it doesn't matter for us for us。

 then we can just use the compilation fl R E dot ignore case。

 so we can write this out so we can say ignore case。



![](img/da8ee5de7a086ab699eec08ed957b1f1_293.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_294.png)

Or we can just say R R E dot I。And then if we use a small W， then it will still find the match。

 And because now it ignored the cases。 So this is the ignore case compilation flag。 And now， yeah。

 you also have。

![](img/da8ee5de7a086ab699eec08ed957b1f1_296.png)

In these compilation flags。 So I recommend that you check them out for yourself。

 I will provide a link to the official documentation in the description。 And now I think we are done。

 and now you should be able to understand all the different regular expressions。😊。



![](img/da8ee5de7a086ab699eec08ed957b1f1_298.png)

![](img/da8ee5de7a086ab699eec08ed957b1f1_299.png)

I hope it wasn't too complicated for you。 and I hope you enjoyed this tutorial。 If you like this。

 then please consider subscribing to the channel and leave me a like and see you next time， bye。



![](img/da8ee5de7a086ab699eec08ed957b1f1_301.png)
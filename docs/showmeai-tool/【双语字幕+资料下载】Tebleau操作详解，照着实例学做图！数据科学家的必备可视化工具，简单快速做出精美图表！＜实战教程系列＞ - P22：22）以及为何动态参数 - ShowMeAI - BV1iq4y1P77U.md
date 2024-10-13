# 【双语字幕+资料下载】Tebleau操作详解，照着实例学做图！数据科学家的必备可视化工具，简单快速做出精美图表！＜实战教程系列＞ - P22：22）以及为何动态参数 - ShowMeAI - BV1iq4y1P77U

Hi， folks and welcome to another episode of Tableau in two minutes。

 super excited to be talking you through this episode。

 because I think what we're going to talk through today can make a huge difference to the interactivity and how interesting you can make your visualizations when it's all used in the same way。

 This week， we are going be talking about dynamic parameters now。😊。

Pararameterters have been around in Tableau for a long time。 What was new in 2020。

1 was that you can now have these parameters like update when your data updates。

 So if you have a list of values instead of just being a static list of values now you can populate that list of values based on whatever's in the data。

 So if you open a store in a new market or you have a new area director come on board or somebody else。

😡，That value will automatically be populated in that list。 And as long as it's in the data， right。

 we can use that to highlight， you can use it to filter， do all sorts of things with it。

 The other thing you can do is that if you have a workbook that you always want to show the most recent two months of sales。

 for example or the most recent eight weeks of sales。

 you can do that using one of these dynamic parameters。

 Now you were able to do it before with a couple of workarounds， but this makes it so much easier。

 and it makes it more dynamic right So if I wanted to see the last eight weeks of sales based on the most recent date when I opened the workbook。

 but then maybe I wanted to see something different later on。

 like the last eight weeks through two weeks ago。😊，I could change that using the parameter and。

 but I couldn't change that if we'd like hard coded it into the workbook before， so super exciting。😡。

Both of them are really easy to do because they build on functionality that was already there。

 So why don't we take a look at how we can build one。For this first one。

It's something you may not have done because it was annoying to update right whenever the parameter was changed。

 so I've always used like filters and values to try and make sure that my lists were correct。😡。

So let's go ahead and do it。 I'm gonna connect to a data set that I made that's dead simpleim in Excel。

 It's just called my， my small GP data set。 And this has some data on。

People's grades for different tests and different classes it's all made up if you're not from the USA you want to understand what this point score means。

 but basically for an A you get four points for a B， you get three points， C。

 you get two points and so on and so on and so on and that's how you calculate somebody's GPA using those So we have two different tables of this and we're going to use one to update the data later on so what I've done is I've drug out this grades October sheet and you can see we have a test date。

 a student a class a grade and the number of points。

And we are going to go ahead and just build us a quick bar graph that has the student。

And then the number of points that they got right so this is the total number of points we're can go ahead and sort that to make it neat and tidy and then what I'm going to do is I'm going to use a parameter to highlight the number of points that a certain student got in a certain class。

So what we're going to have to do。We' are going to go to create a parameter here。

And we're going to make it a list and it's going to be a string and we're going to use it。

We're going to use class。 Now， you'll notice that I have two options here on the right hand side。

 I used to only have one。 It used to be fixed。 but now I can select that when the workbook opens。

 I want my class value to update。 That's what I want it to load whatever's in this list。

 And we're going to call this class。Highlight Para。We're going to hit okay， all right， awesome。

Then we're going to use that to create a highlight。

 so I'm going to go ahead and create a calculative field。And then we're going to say。

 if the class equals。Clss highlight parameter， then。Highlight。Else， don't。Okay。

 then we're going to take this class highlight field。

 we're going to go ahead and drag it out onto my color shelf there。And I'm going to add this。

To the sheet。And you can see that in orange， we're highlighting all the points that people got in each class。

 and we have English， math and Spanish。Now， let's go back to our data source。

 and we're going to go ahead and we're going to drag out this grades for November， right。

 We're going union it on。 I have another video about un。 if you're interested in looking at that。

 So we're just going to do that for now。 And then we're going to go back out to our sheet。

 And you'll see that even though we didn't actually close and reopen the workbook。

 we now have geography as an option in our。List here too。

 so this list is repulated with new classes based on the new data that we added to it。

 So excellent functionality right means that you don't have to go back and keep reupating your parameter every time you update the data in the workbook or reing the fields to your parameter and because you can do that and you don't have to change it every time the data updates that gives you a whole bunch more flexibility with with these parameter。

All right， so。😡，We've done that。 Let's let's take a look at the other one， right。

 So let's say that when I log in， I'm making a data， a dashboard for my teachers。

 and I want my teachers to be able to see all of the the points that everybody got for each of the tests。

So it's going to open up a new sheet here and what I want it to do is I want it to show one test at a time and I want it to always show what the latest test was to start with。

 but I also want to give them the option to go back and select different dates with different tests if they wanted to do that。

😡，At a different， you know， sort of different time。So let's we'll open up a blank sheet here。

 the first thing I'm going to do is I'm just going to build my basic bar chart so we're going to drag student out to columns。

 we're going to drag points out to the rows again and then we're going to sort it because all sorted data is so much better than unsorted data。

😡，And I'm also just going to set us up for this by going back and removing November data。

From our union here， so we're going to delete November。There we go。And go back to our sheet。

All right， so。😡，Now let's try building our parameter。Oh， sorry， we want a new parameter。

And I want this to be test， date parameter。Bli me can't type today， can I all right， there we go。

 we're also going to make this a list， it's going to be a date。😊。

And we want to add the values when the workbook opens， right。

 because we always want to have the latest date and we want to add them from test date。 Now。

 there you see， there's my three test dates。 What we want to change in order to have it always highlight the last date is this field that says value when the workbook opens。

 Now， right now， it's hard coded to say current value。 So we can't change it at the moment。

 it's always going to be the same value that it currently is， which is which is 101。

In order to change that， what we need to do is we need to create ourselves a calculated field and this calculated field needs to fulfill a handful of criteria Firstly it can only have one value。

 whatever the visualization is whatever we do with the data it can only have one value。😊。

And it has to be based， right， derived from this field that we're using to get it up。

 So in this case， we have to derive a field from test date。That only has one value。

 and we're going to do that with something called a level of detail calculation。

This level of detailed calculation is dead easy。 So if you're not sure how to do them。

 this this isn't going to matter that much。 Again， tons of resources online would recommend you learn how to do them because they are quite。

Helpful， so we're going to call this one last test date。

 and we're going to use a fixed level of detail calculation。 We're gonna say max test date， oops。

There we go Now what this does， what a level of detail calculation does is it says that for our whole data set because this is fixed and we didn't put any any grouping fields in here or any ways to divide the data in here for our whole data set。

 we are going to look for the maximum test date。😊，So let's just go ahead and apply that。

 So we've created that calculatedalc field that popped up right here。 Now。

 let's move this out to our。Field。And then what I'm going to do while we're here is I'm also going to create our filter。

 So this is going to be our test date filter。 And we're going to say if test date。

Equs the test state parameter。Then show。Else。Hide。And all right。 And then we're gonna apply that。

 We're gonna drag this out to our filters shelf。 We're gonna say I only want to see the ones that we labeled show。

 right， So based on this logic， if the test A equals the parameter， we're gonna show it。

 And then let's just test it before we go through everything， right？ That's changing properly。

 Excellent， Good， like the way that's working a lot。 Now， how do we get it to。To add the new data。

 let's go up to edit parameter。Now， you see value in workbook opens was set to current value。

 We've set so that it's going to update the test dates whenever the workbook opens。

 And we want the current value to be whoops， sorry。

 we want the value in the workbook opens to be this latest test date。

 That's going to push it to be the same as this field that we just created。

Every time the workbook opens， right， so let's click that。

 you can see it already updated to be the 20th。But let's see what happens when we add the new data to it。

Alright， we can move that around。 Sos go back to our data source again。

 I'm going to take the grades from November。 I'm going to add them to my， my union here。Beautiful。

 there they are。 And now， when we go back to sheet 2， you see this is updated。 and now we're showing。

😊，11，222020。 So what that allows you to do， right is you can have that default to the most recent test。

 But if a student wanted to see something else， they could also go back and they could look at a different test。

 or sorry if a teacher wanted to see what the 1116 results were。

 they could still go back and do that。 We're not forcing them only to look at the most recent test in this view。

 we given them the option， but we're setting a sensible default。Very cool。 A ton of functionality。

 I'd love to see what you guys come up with when you work with these。😊，So。

 but that does it for this episode。 I hope you found that helpful。

 If you did go ahead and hit the subscribe button。 It'd be great to see you on here。

 We have tons of great tableau content。 I will put a link to the data that I did with this in the video description so you can download Tableau public。

 Really encourage you to follow along。 Great way to learn and。😊，I will see you next time。



![](img/9701594717a65b5fe3eb4525a0af752c_1.png)

![](img/9701594717a65b5fe3eb4525a0af752c_2.png)
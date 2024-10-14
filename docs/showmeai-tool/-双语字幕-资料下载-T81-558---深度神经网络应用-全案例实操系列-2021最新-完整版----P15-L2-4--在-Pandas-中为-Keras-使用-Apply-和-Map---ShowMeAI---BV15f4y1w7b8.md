# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P15：L2.4- 在 Pandas 中为 Keras 使用 Apply 和 Map - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeffine and welcome to applications of Deep neural networks with Washington University In this video。 we're going to look at how to use apply and map functions together with pandas。 This allows you to write Lambda functions or other functions that will be executed across your entire data frame。 This allows you to do relatively complicated transformations to your data frame that might be very useful for feature engineering。

 which allows you to represent the data in ways that will allow your neural network to be more predictive for the latest on my AI course and projects。 click subscribescribe and the bell next to it to be notified of every new video。 applyly and map or two functions that are provided by a pandas data frame that you can use directly on these。 Now we've seen map already for just general Python data structures lists in particular。😊。



![](img/5e8029765ef65f0d9c303a190e424729_1.png)

But map can be used with data frames to do similar types of transformations for more advanced feature engineering that you'll probably have to do with some of the projects in this class。Apply and map can be very， very useful and we'll look at a specific case。

In the later part about how to do just that。So let's go ahead and load in the autompG data set。We are going to do a very simple mapping on it。 This is one of the most common things that you will do with for maps。 This is similar to a decode。In SQL。What we're going to do is this origin value that you have here specifies the region that the car was from。 One is North America。2 is Europe， and3 is Asia。So what we're going to do for this is we're going to take the origin。

We're going to create a column called originig name and we're going to fill it in all cases where this is what the map will do。 it's going to look up the origin value and it's going to replace it with North America for one。 Europe for two and Asia for three， so let's run that。And if I scroll that over a little bit。 you can see North America， North America， Asia for that three。Asia， Europe is two。And so on。

 So this can be a very good way to summarize values if you could actually。I mean。 say you had numbers in here that were all the 50 states。Of the United States of America。 you could put a bunch of values in here that go to the same thing。 You could do one to North America，2 to North America or even state names， Missouri to North America。

 California to North America， New York， to North America and so on and so forth。 Whereas if you saw France， it would go to Europe。 So you can also use this to to summarize。 apply is another。Thing that you can use。With these data sets。Apply basically takes a function。 typically a lambda and runs it against every single。Row in the data。So here。

 let's go ahead and run this， this is calculating something that I call an efficiency。It's basically the displacement divided by the horsepower。So how big is your engine versus how much horsepower do you actually get？

 And this gives you a general indication of the efficiency of the car。 So we could add that in to the data set。 This shows how you're。 you're sort of engineering a feature based on。Based on this ratio。Here I'll show you a more complex example of feature engineering。

 This was actually an assignment in previous semesters。You'll probably see an assignment about like this one in this semester。This basically is using a data set that we have here from the IRS。 which is a United States government。Taxaing authority。And we're going to。

 there's also more data documentation on here if you care to read about it。 but this is basically a data set that gives you the estimated adjust gross income。Plus。 other things for zip codes in the United States， so the fields that you care about are state。 which is the state example， Missouri。Zip code。Is the zip code of within that state？

AGI Stub are six different income brackets。So one is the lowest income， six is the highest income。Each zip code is going to have six rows for it then they give you a count， which is in one。Of the number of people in each of those income brackets。 so that gives you sort of a distribution of wealth in that particular zip code。

What we're going to try to do is put those bands back together so that you have a。Estimate of what what the overall AGI is for that that particular zip code， so this is a reduction。 you've got zip code， you've got six rows for each zip code。 you want to crunch that down to just one row per zip code and just give an overall estimate of the adjust roasted income。

And this is kind of what the file looks like。 See you've got 63017。 this is a zip code that I work in。AGI Stub， so that's your six values they have for each and then the count。So the second to the highest is the largest income。And this shows this particular income if you do probably the most。

Famous zip code in in the United States of America，90210， it'd probably be pretty high。 because that's a very affluent zip code。 So you see a lot of numbers down here。 What we're going to do to put it back together。 These are this is the bands for each of these1 is 1 to 25 k 6 is 200000 or more。 Now， one of the issues with putting this back together is 200000 or more。 That's the R more。

 that's a pretty big category that could be up to， I don't know， probably many millions of dollars。 However， much those guys are making。 So what we're going to do is we're going to establish a median for each of these ranges。125。 Now this last one since we don't know what the ceiling is 2，12500。 That's probably the biggest flaw in this estimate that I'm that I'm putting together。 But you。

 you can see about where those are at。 So the way that we can estimate6，3，0，17s。 average Agi。Is we're going to basically sum all those in ones。 So that's our total count。 We're going to add those all up。 We're going to total up the Agis， but waiting them by the medians。 So we're going to take the count of people that。So the 4710 times 12500 because that's how many people are in bandand one。

 that's the median for band one。Band two， there were two 2780 and 37500 was the median for that one。 so we're essentially this is sort of a weighted weighted sum you have here。And then we're going to divide those， and that gives us the average income for this zip code is around 88。000。Which seems reasonably correct。This is good too because this gives us a value that we can check by hand because we calculated this by hand。

 so our automated process that's going to calculate for everything single zip code should come up with the same value。 So we're going to load that data set into Ram it it's big and gigantic you'd probably want to stream it。 but this is this is loading the entire data frame It'll be loaded in a second。That might have took a while。 That took probably 20 seconds for me。 Now what we're going to do。

 So this is going to show you a good example of using multiple of these techniques together。 Now this data set does have some junk data in it。 So we have zip codes that are0 and 9999。 There's no such zip codes。 they do have a purpose in the data file， but we're simply not using them。So we are going to get all the rows， that's what Lo does for us。

 where the data frame is not equal to zero zip code and the zip code is not equal to 9999。And we're also going to only pull back these fields。 so we're chopping this thing down horizontally and vertically。 we're getting rid of a bunch of columns and all the rows that have these invalid zip codes。

You run that。This is actually very quick and now the data frame has been modified if you were to display the data frame。You'll see that it has literally just these four。And the invalid ones are also gone。 but we're not going to go hunting for them。What we're now going to do is we're going to take all of these AGI stubs and replace those with the medians。Those medians that I gave you one，36， so this is a brilliant application of the map。We run that。

Again， it's very， very quick。And if we look at this。 we now see that those should have transformed and they have the AGI stubs are now。Those actual income medians。 Next， we group it by zip code。 and for each of those zip codes now。 we can basically perform a lambda。 So this is a great use for apply。

 We're going to do apply across it and we're going to basically sum because we want to sum up all of the values。😊，In each of those zip codes， but we're going to sum them weighted。 so we're going to basically wait the n1。 So how many of them we have。 say the 30 there multiplied by the AGI Stub， and then we're dividing the whole thing by in one。

 which。Which is the sum of the N1s， actually， you can see the sum there for that entire zip code。Then we reset the index so that the row numbers align like we've seen before。We run that。That does take just a few seconds。 Let's see what that actually did。 We now pretty much have the data set where we want it to be。Zip code。

 and this is the average for each of those。The column headers are a little bit sloppy， zip code。 that's good， but zero， what's zero， zero should be our average AGI。Our AGI estimate。We'll just rename those two columns and then we display the top。And we can see now we've got this nice output。 You'd probably want a two CSsv then。

 and that that would be a completely valid submission for that previous assignment that I ran in。Last semester。We'll look up our zip code that we calculated by hand， and that matches our 88。689 that we had before。 Thank you for watching this video In the next video。 we're going to continue with using pandas and talk about feature engineering， which is how you。😊。



![](img/5e8029765ef65f0d9c303a190e424729_3.png)

Represent your data set in a way that helps the neural network to be more predictive。 This content changes often， so subscribe to the channel to stay up to date on this course and other topics in artificial intelligence。
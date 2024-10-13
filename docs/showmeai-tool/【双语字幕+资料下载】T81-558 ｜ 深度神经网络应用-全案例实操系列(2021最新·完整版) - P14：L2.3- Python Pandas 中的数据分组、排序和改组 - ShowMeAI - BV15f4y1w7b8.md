# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P14：L2.3- Python Pandas 中的数据分组、排序和改组 - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Heaton， welcome to App of Deep neural Networks with Washington University。

In this video， we're going to look at grouping， sorting， and shuffling of a data set within pandas。

This allows you to do things like an SQL group by where you summarize and aggregate your data to process it in additional ways to get it ready to go into the neural network for the latest on my AI course and projects Click subscribe and the bell next to it to be notified of every new video Pandas data frames can also be grouped sorted and shuffled In this part。

 we're going to look at how to do just that shuffling in a data is very useful You want to be sure that you don't have a number of common targets near each other。

 I mean， the worst possible thing would be to sort your data set According to the target。



![](img/30a851993f0ab2fa4dd62a6efcf8bb3e_1.png)

And then split it evenly to get your training set。And test set from it because your test set would have all low values。

 your training set may have all high values or something similar to that。

 so shuffling is a very good thing to do。This command that I'm running here takes the autompG data set。

 Now if you want consistent shuffling， which is not bad。

 that's actually usually preferable because you may need to reshuffle your data set to add columns or something like that。

 You probably don't want the order changing because you already establish some benchmarks。

 you do want it random， but you want it consistently random， so you can pick a seed number here。

 I'm choosing 42 hitchhiker's guide to the galaxy where that number comes from it's a fiction book you can look it up。

But this is this is basically taking the this line here， resources it。

 this line causes these numbers down this list to be in order。

 it doesn't really matter if you leave the second line off， notice if I run it here。

Those numbers now are not put back to account between zero and one or zero，1， two，3， and so on。

I like to have them in order like that。 So that's why I usually do that。

 It can cause some other strange strangeness， if you don't read。We set those。

You can also sort a data set， so here we'll use the auto miles per gallon data set and we're going to sort it。

 we're going to sort by the name of the car in ascending order。

And we can then print out the name of the first car， which is the AM C ambassador。Brgham and。

Now you have a sorted data set notice these numbers are again out of order so you can tell where the original position was。

 you can use exactly the same reset index command that you used up here to put these back。Again， you。

 you may or may not care about the original sort order before you shuffle it， usually I don't。

 and I almost always reset that。You can also group a data set Grouping is very similar to the group by command that you have in SQL。

 It takes the data usually use one of the categorical values and you group it according to that categorical value。

And you can then count up how many values of each category you can do an average of another column based on groups of that first one。

 so let's look at this。Here's the CARS database again。

We're going to group by cylinders and report the average miles per gallon， so the meanme。

We'll run this。And we see that this is the average miles per gallon。

 so a eight cylinder not surprisingly， gets the worst miles per gallon，6。Is better。

5 is even better 4。 And then these three cylinder ones，3 cylinder cars。

 as our five cylinder cars are a bit of outliers。 They're very rare。

 So that's probably why the miles per gallon drops on those three。

 They might those might have actually been performance cars。 I don't know。 I'd have to。

 I'd have to study the data and explain that。 But nonetheless。

 this is how you very quickly go across all of these and can get average values。

You might want these as a dictionary。This way， you can very quickly look up in that dictionary and find the mean of any of these。

For example， if you wanted to know the mean of a six cylinder car。

 you could run that and it would tell you 19。 that's important to realize that that's6。

 that's not an index， that's a key， so that's the key here。It returns the value of 19。98。

You can also get count of how many cars are at each of these， and this is somewhat important。

You can see why the three cylinder cars are such outliers。

 there's only four of them versus 2044 cylinders， four cylinder。

 at least at the time this data set was created was the most common。

 there were also a lot of V8s back then too。I suspect this distribution would be different in today's day and age。

So this is how you can both sort and group data， this is very the grouping especially you will use this again for feature engineering views very。

 very often you want to group up the data set and look at how how those values are varying according to this。

 for example， say you had missing MPG values。You could just stick in the median of MPG。

 or you could do。I suspect this will be pretty similar to the means。Mostly。

 so you could use the medians and say you had a missing MPG rather than just throwing in the overall median for the entire data set。

 you could look at the cylinders and put in the the missing value of the median by the cylinders that that car has。

 That gives you a much more intelligent way of。Fillling in missing values。

 then simply putting in the overall median， you can use the median for another field that's very strongly correlated。

And in this case， cylinders and miles per gallon are very strongly correlated。

This would be another technique that would be very good to use with the Kaggle competitionet project that we will have later in the semester。



![](img/30a851993f0ab2fa4dd62a6efcf8bb3e_3.png)

Thank you for watching this video on grouping sorting and other techniques in pandas We're going to look in the next video about how to use apply and map This allows you to use Lambda functions to do much more complex modifications to a pandas data frame This content changes often so subscribe to the channel to stay up to dateate on this course and other topics and artificial intelligence。


# 【双语字幕+资料下载】绘图必备Matplotlib，Python数据可视化工具包！150分钟超详细教程，从此轻松驾驭图表！＜实战教程系列＞ - P6：6）Matplotlib 中的基本图形 - ShowMeAI - BV14g411F7f9

I'm going to create a section header here in Markdown。 I'm going to call it section number。 I guess is section number 2 now， isn't it Section number 2。Basic graphs， alright。So let's do some of the basic types of graphs that you might want to work with here。 And actually。 you know what， we， we haven't started using our heart disease data yet。 have we。

 So let's actually scroll back up to the top。![](img/459a65c80f9f13fc0f4dccf9dd01c356_1.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_2.png)

I'm going to create another header here， and I'm going to say load our data。 Okay。 so we're gonna to load our data using pandas。 And if you have not used pandas before。 and if you haven't seen the project data science， Padas megatu， the Padas mega tutorialial。 that will walk you through pretty much everything that you need to know about pandas。

 So I would highly recommend watching that at some point。 But let's go ahead and just import pandas as PD D。And we're going to use pandas to load the data。 So let's type in LS， which handy dandy， Jupiter notebooks converts into the shell command。 or it uses the shell command here。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_4.png)

And it lists out the files that are in the current directory。 So we see our heart disease U I data set。 So I'm going to load this P D dot read CSV。Into a into a data frame。 So let's read that in。If we look at DF。head。 this will give us the top five rows in our data， so we see that we have our age sex。

 we have this column called CP， ettera， et cea， et cea。 and then target is whether or not the person had heart disease。![](img/459a65c80f9f13fc0f4dccf9dd01c356_6.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_7.png)

If we look at DF dot shape， this will tell us how many rows we have and how many columns。If we look at DF dot describe。![](img/459a65c80f9f13fc0f4dccf9dd01c356_9.png)

Df dot， describe。This will tell us some descriptive statistics for each column。 So， for example。 our our average age is 54 in this data set。 And if we go over to targets， the average。![](img/459a65c80f9f13fc0f4dccf9dd01c356_11.png)

Prevalence of heart disease is about 54%。 So the majority of the people in this data set do actually have heart disease。![](img/459a65c80f9f13fc0f4dccf9dd01c356_13.png)

Finally， if we look at D F dot info， this will tell us the number of non null rows。 So in this case。 we have 303 rows。 Looks like all of our columns。 none of them have any nulls。 and all of them are numeric data types。 One of them is afloat。 The rest of them。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_15.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_16.png)

A ints here， integers。Alright， so we've loaded our data。 We're ready to start plotting using this data now。 So we'll come back down here to our section number  two， Section 2， basic graphs。 So let's start。![](img/459a65c80f9f13fc0f4dccf9dd01c356_18.png)

With a scatter plot， start with a scatter plot。So if we take a look at our data frame。And maybe we want to take a look at the scatter plot of two of these columns plotted against each other。 So maybe we're interested。Is there a relationship。 Is there a relationship between age and let's say， your cholesterol level。

 So that's the question we're interested in answering。So I'll actually type that in here。Is there a relationship between。Age and cholesterol。Cholesterol level。So if we look at D F age here。 this is going to return a panda series。 We have a bunch of values。 We can convert this to a numpy array， which is used in plotting mapplotlib here。 And actually。

 I think mapplotlib can also take pandas series as well。 But， you know。 never hurts to convert it to a nuy array first。 And then let's look at the first 10 values here。 So the first 10 values of our nuy array。And let's also look at cholesterol。 Let's look at cholesterol。First 10 values here。Alright。

 so we want to make a scatter plot following the same the， the formula that I told you up there。 the formula for plotting a mat plototlib。 Let's do fig comma X for axes equals PL T dot subplots。We'll do AX dot。 We have been doing AX dot plot。But all we have to do is change it to A X dot scatter。 So instead of doing a line plot， we're now going to do a scatter plot。

And we'll pass in our what we want our x to be。 So x is going to be。The age。 and then we'll pass in away what our Y to be。 So the y is gonna be。Our cholesterol。And then finally。 P， L T dot show。![](img/459a65c80f9f13fc0f4dccf9dd01c356_20.png)

And here we go。 Here's a scatter plot of our age versus our cholesterol。 And at a glance， you know。 at a glance that doesn't appear to be too strong of relationship。 There might be a slate。Positive relationship here。But nothing that jumps out and slaps us in the face。So let's， you know。 maybe we're interested in not。Not every data point that we have in our data set。

 Maybe we're interested in the average by age。 And this will actually give us fewer points to work with as well。 So I'm going to create a。Data frame。![](img/459a65c80f9f13fc0f4dccf9dd01c356_22.png)

That is grouped by age。 And so essentially， what we're going to do。Df。Dot group by。 we're gonna group by the age。 and then we're going take the average of all the other values。 So if I do that， and， you know， I explain this more in the pandas tutorial video。 But essentially what's going on here is we're we're grouping all of our data by the age。



![](img/459a65c80f9f13fc0f4dccf9dd01c356_24.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_25.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_26.png)

And then， you know， for， let's say，40 year olds or。Let's see， maybe for like 45 year olds。We'll have 10 different data points。 So we're going to take the average of those 10 data points to get each one of those values。 So this cholesterol value here， rather than being the cholesterol for a single individual。 is now going to be the cholesterol the average cholesterol for all 45 year olds。

 So let's take this group I。![](img/459a65c80f9f13fc0f4dccf9dd01c356_28.png)

We'll set this equal to DF group by age。 Let's just call it， call it something so that we can use it。And then if we look at this data again and ask ourselves， okay。![](img/459a65c80f9f13fc0f4dccf9dd01c356_30.png)

Now we want to plot age versus cholesterol。 Well， our age is now our index over here on the left side。 So this is kind of a special feature of pandas data frames。 And then our cholesterol is still just a column。 So if we look at Df group by age do index here are all of our ages。 So this is going to be our new X。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_32.png)

And if we look at DF group by age cholesterol。![](img/459a65c80f9f13fc0f4dccf9dd01c356_34.png)

Dot。Values， and we'll just look at the first 10 of those。![](img/459a65c80f9f13fc0f4dccf9dd01c356_36.png)

Rightright， maybe we can look at the first， you know。10 from the index， as well。Alright。 so let's create a second scatter plot。![](img/459a65c80f9f13fc0f4dccf9dd01c356_38.png)

So we'll say scatter plot number 2。Average。😔。![](img/459a65c80f9f13fc0f4dccf9dd01c356_40.png)

Coholesterol by age。 Alright。So we can take this exact same kind of scatter plot formula。 We'll put it down here。 And now instead of D F， we're going to have Df group by age。 Df group by age， and rather than calling the age column。![](img/459a65c80f9f13fc0f4dccf9dd01c356_42.png)

For this one， we're gonna pass in the index and this DF。![](img/459a65c80f9f13fc0f4dccf9dd01c356_44.png)

Call will stay the same。 So let's plot this and see there you go。 So now we just have a single data point。For each age。 and we get something that actually does look much more like a positive correlation here。So that is scatter plots in a nutshell， A X dot scatter。

 and were we're going to go into more depth with all of this graphing as we go along。 But we're starting with just the question of how do you plot some basic graphs。 So first up。 scatter plot。![](img/459a65c80f9f13fc0f4dccf9dd01c356_46.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_47.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_48.png)

Now， let's talk about a line graph。So what if we wanted to take this same plot here。 But rather than plotting it as a scatter plot， what if we want to connect the dots。 we want to plot a line graph similar to how we did up top with the you know， y equals x squared。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_50.png)

Well， we can just copy this down here。 and rather than A X dot scatter。![](img/459a65c80f9f13fc0f4dccf9dd01c356_52.png)

We've done this before， A X dot plot。![](img/459a65c80f9f13fc0f4dccf9dd01c356_54.png)

And there we go， whether or not it makes sense to represent this data this way。 You know， that's。 that's your judgment call to make， but。To plot a line graph。All you have to do is call AX dot plot。Okay， so let's move on to。 let's do a， let's do a bar graph。 What if you want to plot this as a bar graph， Lots of things look really good as bar graphs。

 It's very easy to tell relationships between different。Different categories in a bar graph。 so this is a very common type of graph， how do we do that in Matplotlib？Once again。 let's go ahead and copy our formula for graphing down here。 So we create our figure。 We create our axes using PL T dot subplots。 And now， rather than A X dot plot。



![](img/459a65c80f9f13fc0f4dccf9dd01c356_56.png)

We just do A X dot bar。 So you can see that we're changing the type of plot here by changing the method that we call on the axes object。 So we have our axes here where we want to plot something。 And then to actually plot something。 we got to call some sort of method on it。And to do a scatter plot， you call dot scatter。To do a line plot， you just call dot plot。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_58.png)

And dot plot is more powerful， by the way， you've got。 you have a lot of different options actually for each one of these methods。 but we're just going through the basic method right now。 And then for a bar graph。 you just do dot bar。 and all the time your first value here is going to be your x。

 and your second value is going to be your y。![](img/459a65c80f9f13fc0f4dccf9dd01c356_60.png)

That is going to change slightly with a horizontal bar graph， which we're going to do next。 So let's do a， let's do a horizontal。![](img/459a65c80f9f13fc0f4dccf9dd01c356_62.png)

Bar graph here， and。So， instead of calling。Bar， now we call bar。![](img/459a65c80f9f13fc0f4dccf9dd01c356_64.png)

H， so we call bar H。 And now so this， this is where it mixes up a little bit。 This first argument that you're going to pass in。 you know， you call it the exact same way here。 But now this first argument that you pass in is technically going to be your Y axis and the second argument that you pass in is going to be your X axis。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_66.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_67.png)

So now you might be thinking， okay， well， hey， how do I， you know。 just how do I see how many methods I can call on this axes object。 So if you go out to a new cell。![](img/459a65c80f9f13fc0f4dccf9dd01c356_69.png)

And I believe we still have this A X object from the previous cell here。 If we do A X， we type dot。 and then we hit tab。 So this will show us all of the different attributes。 all of the different methods that we can call on our axes object。 And you'll see that there are actually they are quite a lot。 So here's bar。 Here's bar H。

 You can see that we've got a box plot there。 You can see that that we've got various things for dealing with labels and zooms。😊，We have error bars here。So you have all kinds of different things and this is， you know。 partially I'm just scrolling through this massive list right here。This is partially what I said whenever I started the video about matpllib can be overwhelming。

 There are so many options because you can you can tweak this graph to look however you want it to look。 So there are a ton of options here。Which is why we are starting kind of nice and simple。And building up complexity as we go。 And there will still be a ton to learn after this video。 So。 you know， it's all about just， how do you want the graph to look。

And how do you get Maplotlib to do that？Let's keep going with simple types of graphs。 This is going to be our last one is a histogram， and for a histogram， you just need one variable。 so you know a histogram buckets， your data into different into different bins and then shows you how many of your rows of data fall into each bin。So in this case， maybe we want to look at。Let's go and copy our。

 our kind of plotting formula down here。Maybe we want to look at our age distribution。 So how many people in our data fall into which age buckets。 So in this case。 we just call Ax dot hist。 So dot hist is the method that we're going to call here for histogram。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_71.png)

And by the way， if we wanted to look at that。![](img/459a65c80f9f13fc0f4dccf9dd01c356_73.png)

Dock string， if we wanted to look at the， the documentation for his。 We just put the question mark after it。 We run that cell。 And then you see， okay。 what do we pass in here。Well we pass in X， X is the only thing that's required。 and all of these other parameters are optional。 They all come with defaults， so。Bins。

Is one of the parameters that we can use。We can plot a histogram， okay。 compute and draw the histogram， etc cetera， et cea。Bs， here's the description for that parameter。 So if you want to do something like plot a histogram and you want a little bit more control。 you know， slap this question mark here， run this cell。

 get the documentation and see what all your options are。And you can set some of these right whenever you first plot your histogram。![](img/459a65c80f9f13fc0f4dccf9dd01c356_75.png)

Alright， so we want to look at our histogram for our age。 So in this case。 we're going to go back to our original data frame that has all of our rows。 that has one row for every person in this data。And let's go ahead and get the values here for the the numpy array。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_77.png)

And here we go。 Here is the histogram of how many people in our dataset fall into each into each age category。 So you can see here that we have， you know， most of the people in the data kind of fall into this cluster right here。 Actually， we've got， you know， we've got two big clusters here。 One of them is from what is this like 53 up to 67 or something like that。

 And then the other the other group here from you know， late 30s up to 50，53， early 50s。 something like that。So that is how you do a histogram。 And with that。 you see we have a number of different chart types here that you can access all just by calling these different methods。 And if you remember。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_79.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_80.png)

Scrolling back up to。![](img/459a65c80f9f13fc0f4dccf9dd01c356_82.png)

These four different subplots that we had， these four different axes。 So if you wanted to do a different type of plot in each one of these， you could。 And， you know， I I。 you know， I could just show you what that looks like right now。 actually， So what if we change。X to the fourth。To a scatter plot。And there we go。 Well， so we have a lot of data points here。 Oh。

 it's because we changed our x and our y。 We changed our x and our y to have。![](img/459a65c80f9f13fc0f4dccf9dd01c356_84.png)

A lot of different points to have 1000 different points down here。 So that's why this graph is now gonna look。![](img/459a65c80f9f13fc0f4dccf9dd01c356_86.png)

Pretty different， which might actually not be super great for these next types of plots。 but let's。 let's try it anyway。 Let's try a bar plot。So this is going to try to do a bar plot with a thousand different bars。 which yeah， it's not not the greatest， but there you go。And so this is how。You would do different types of plots in your different subplots here。

 it's as easy as changing the method you're calling。![](img/459a65c80f9f13fc0f4dccf9dd01c356_88.png)

O。So that wraps it up for these simple graphs here。 We have scatterplot。![](img/459a65c80f9f13fc0f4dccf9dd01c356_90.png)

We have a line graph。 we have a bar graph， horizontal bar graph， and a histogram。 And with those plots， I think you're going to be able to do most of the types of plots that you want to do。 especially when you start kind of mixing and matching these and learning how to use color and all of that。 So let's， let's move on now。

![](img/459a65c80f9f13fc0f4dccf9dd01c356_92.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_93.png)

![](img/459a65c80f9f13fc0f4dccf9dd01c356_94.png)

To the next section。![](img/459a65c80f9f13fc0f4dccf9dd01c356_96.png)
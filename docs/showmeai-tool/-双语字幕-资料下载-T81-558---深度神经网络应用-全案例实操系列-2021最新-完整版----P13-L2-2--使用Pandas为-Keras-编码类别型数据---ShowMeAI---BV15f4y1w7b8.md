# 【双语字幕+资料下载】T81-558 ｜ 深度神经网络应用-全案例实操系列(2021最新·完整版) - P13：L2.2- 使用Pandas为 Keras 编码类别型数据 - ShowMeAI - BV15f4y1w7b8

Hi， this is Jeff Eaton。Welcome to applications of deep neural networks with Washington University。 In this video， we're going to look at how to deal with categorical values。 A categorical value is something that is textual and not numeric。😊。These require special handling to be inputed into a neural network。

There are many classic ways of handling this， such as dummy variables。 however。 we're going to look at a number of different ways to actually encode this type of value for a neural network for the latest on my AI course and projects。 click subscribe and the bell next to it to be notified of every new video categorical and continuous values are two types of data that you'll run into frequently and tabular data sets。

![](img/8a2d61d5d493f9c40cbab3980011f3a5_1.png)

We can really divide the type of data that you will run into。In four categories in all。al nominal ordinal interval and ratio。Character data。 So strings you'll think of as either nominal or ordinal。 Nominal are just pure class values like red， green， blue， orange， indigo。

 like colors or something like that。 Now， color， you might encode that as。As RGB values or something else rather than dummies but。Typically。A nominal value is just something that there's no particular order that you can think of for it。 You should always try to come up with an ordering， if you can。

 And then that makes the nominal value an ordinal。 and ordinals are also textual data in your data sets。 but they can be， they can be ordered。Now you may have occasionally just unbounded text like a note column or a product name。These are neither nominal nor oral， I guess they would be nominal。 but you would have way too many dummy variables。 So there's other ways that we'll see when we get it a natural language processing that you deal with free form text on the numeric data side。

 There's interval and ratio。 These two types really are rarely handled differently。 But interval basically our numeric values that have no defined start， you can think of temperature。 In my example down there， you would never say yesterday was twice as hot as today。 because there's really no， I mean， short of Kelvin。

 there's really no defined start for how low a temperature can go。 Fahrenheit was originally created。 assuming that zero was absolute0 and。That was wrong， but that would have been a。That would have been a good example of making it ratio。 So a ratio is a numeric value that has clearly defined start。

 You could say that one car is going twice as fast as the second because miles per hour。 the speed of a car。 the lowest it can go a 0。 So it has a defined starting point。 I mean。 I guess technically negative 10 could be going backwards，10 miles an hour， but we're not。 we're not considering that for this example。 So let's first look at how do we encode continuous values。

 continuous values。 sometimes you'll want to normalize them。 Now。 why you potentially need to normalize values is consider， you met a friend on campus and they said。 oh， I did， I took this exam yesterday， and I got 60 points。 Well， is that a good score。 is that a bad score。 that's completely unnormalize。 They told you how many points they got。

 how many points are available on the entire exam。 If there's 100。 then a score of 60 points is really not so good。 if there were only 60 points available。On that exam， then that score of 60 is perfect。 Z scores let you do this。 So Z scores normalize a0 z score means that you're exactly at the mean a negative one z score means your one standard deviation below the mean Similarlyly a plus one means your one standard deviation above So this is kind of like expressing something as a percent but it lets you know rather it has the standard deviation baked into it so that that makes it more applicable for normalization Now let's look at how we could normalize something in the miles per gallon database So we're loading the miles per gallon database and we're going to basically take the MPg column and normalize it to a z score So notice the MPg is right these are all negative numbers and you're not seeing very large one this car here is negative one standard。

viation below the average miles per gallon。 This lets you know very quickly which ones are above and below the mean。 Another advantage to doing this is sometimes when we want to redact data so make the data hard so it's secret so that you can't really tell what's going on with the data yet you can still build models on it Z score can be a great way to do this like people's ages if you make that a Z score。

 somebody looking at your data may not guess that that is actually the person's age because they'll see values that look just like that miles per gallon。 whereas if you see values that range between 18 or 21 and 85 you might guess that that is somebody's age and it's useful to redact private information like people's ages and other thing So thats that's another sometimes used for Z scores But what's good about this is if we were to put every one of these columns into Z scores they'd be a lot less readable in a way because you wouldn't see these actual weights and。

Things like that， but you would be able to very quickly spot things that are above are below the mean Also these will tend to cause these values to be fairly evenly distributed about zero。 which in some cases will help neural networks predict power Also you will have all these values in a similar range so the weights of the car could very much overwhelm the cylinders of the car which is a much much lower number so that's some of the advantages of using Z scores for continuous value andcoding Now for categoricals。

 the tried and true one that you're always going to hear about is dummies and if we load the sample data set that we've seen before。 this is the data set that has the job codes areas incomes predicting which of several products the person' is going to buy if we look at this one we can create and we've seen this previously in this course we can basically look at how many areas there are there are four and we can create the dummy。

For you get the AB So for the dummies， what this is doing is this is showing you essentially the lookup table for these。So for the first one area， if it's going to be a。The dummy， the first dummy will be true。 The rest false， Similarlyly， for B， the second and， and so on。 Now。 if we want to actually encode the data using that sort of lookup table， we do this。

 And these are the dummies that were created。 So the first。 the first few rows were probably all value C。 Then we had a value D。 And we can actually see this then by。Running this， all of these first ones where C and similarly。 C is filled in D， C for the area。 And now we have the dummies actually added to it。 Now。

 our ultimate goal is to get this completely numeric。 So we need to drop the area。One from this。 and we do this。And we can see now that area has been removed。 So this is one step closer to to getting this into a form that we can actually present to a neural network。 We still have to do a similar encoding on job。 Now。

 there's other ways to encode for dummy variables。 There's another way to categoricals。 other than dummies。 You can use something called target encoding。 Now。 target encoding is a little more advanced of a technique。 It's commonly used on kggles。 So it's。It's potentially quite powerful， but it's potentially quite dangerous because you can easily。

 easily overfit with this， so be very careful with it。 You should always be using some sort of a holdoutet or a cross validation technique to make sure that you're not getting artificially high accuracy in results because you might be overfit。Let's create a sample data set here real quick。 We look at this data set。 We have a continuous value here， which we actually won't use。 And then two categoricals。

 categoricals 0 and categorical  one。 And then y， which is the target that we're trying to predict。 we could create dummy variables for dog， cat， Wolf and ti。 Now， again， remember， each of these。 each of these has two classes。 So。It would be ti and Wolf for cat 1 and dog and cat for cat 0。 What we're going to do if we run this line here， this is going to group by cat 0。

On y to look at the mean。 So it's going to tell you what the mean value is of the target of y for dog and cat。 So we run that cat is 0。2。 Dog is 0。8。 This is what you like to see when you're evaluating these for target encoding。 Fortunately， these two are differentiated。 This tells you something right there。 The output from this。Cat or dog is very predictive of what the outputs going to be if this was closer to the midpoint between the two targets。

 so the targets are 0 and one， if this was closer to 0。5。Target encoding is probably not going to help you on that particular category。 Similarlyly， dog is 0。8。 So that's， and since the the target itself is one， these should sum to the target。 So essentially what you can think of target encoding doing is very sum。

 We're going to keep cat at cat 0 as a single column。 We're not going to blow it out to two like we would do with dummy variables。And we're going to essentially。Put 0。2 in for all the cats， 0。8 in for all the dogs。And we have now changed that into a number， and that number will help to predict the y out。 Now。

 this is breaking an absolutely cardinal rule of data science。 You are now using the target for。Your prediction for before you're actually training。That is potentially dangerous。 so be very careful with this technique， and I'll show you kind of how we can mitigate that risk a little bit and where this risk comes in is when you have a very small number of one class。 we only have one tiger and the tiger is zero。 So the average on the tiger is going to be zero。

So any place that we replace the tiger with a zero， this one row is going to be absolutely correct。Just based on that one column， so it's going to correlate 100% from Cat one to the target。The riskier this is is when you have low cardinality or low numbers of one particular class。 the way we do that is by keeping count of how many of each of these we do and specifying a weight that says how much in these low cases will we tend towards the average of y overall。

 so we take the overall average of y and we which can be calculated here。 So 0。5 So there's exactly half as many of each。And for cases like the ti。 we would tend very much towards 0。5 rather than 0。 So you've got these two factors as part of this。 you have the average for Wolffer for ti， but then you also have the overall average for why。

 So we calculate a smooth mean so we try to smooth it out and the smoothing factor is passed in here。 You're going to pass in two data frames that you want modified。 The reason I have two data frames is because you're probably going to have a training and also a test set。You may want even more than that。 You can modify the function。

 That's a change that I made from the original function that I copied from Max Halford。 which I've given a link to his original one here I。Fixed a few things and also made that modification。You pass in the name of the categorical variable that you're going to modify what the name of the target is and then the weighting if this weight is zero。

Then it's going to essentially， the risk of overfitting is much higher because it is going more towards what the average for each of those individual categories is。And if D F2， if you don't have a second data frame， just pass in， pass in none for that。

 So when setting the weight， it's important to keep in mind that the stronger the weight value passed in。 the categories with a smaller number of values will tend towards the overall average of y。 which means less chances for overfitting。Weaker weight will have a greater potential to overfit Now。 encoding categorical values as ordinals， this is a very strong technique。

 no real chance of overfitting。 say you had all of these education levels like kindergarten up through postdoctorate。You could create dummy variables for all of these， but you're actually losing some information because these are ordered。 you don't do fifth grade before postdoctorate， so you could assign a number 0 through 20 for each of these and put in that number in place of the dummy variables so instead of having 21 of these you will have just the one value that you put into there。

And then the other thing you may want to do is you may want to change the weighting because say a graduate student。 you might be a graduate student longer than you are， say in sixth grade。 one year versus who knows how many years for the graduate Thank you for watching this video on categorical values。

![](img/8a2d61d5d493f9c40cbab3980011f3a5_3.png)

In the next video， we're going to see how to do other preprocess with pandas such as grouping sorting and shuffling of the dataset set。 This content changes often， so subscribe to the channel to stay up to date on this course and other topics in artificial intelligence。


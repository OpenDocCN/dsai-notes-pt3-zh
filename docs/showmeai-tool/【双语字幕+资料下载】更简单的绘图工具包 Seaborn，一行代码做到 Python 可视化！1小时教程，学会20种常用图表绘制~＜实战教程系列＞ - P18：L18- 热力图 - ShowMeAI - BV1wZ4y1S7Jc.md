# 【双语字幕+资料下载】更简单的绘图工具包 Seaborn，一行代码做到 Python 可视化！1小时教程，学会20种常用图表绘制~＜实战教程系列＞ - P18：L18- 热力图 - ShowMeAI - BV1wZ4y1S7Jc

Alright， so first off， the first matrix plot we're gonna to talk about are heat maps。

 So let's go and do some styling here。 I'm going to say that I want my figure size to be equal to8 and 6 and I am also going to change my grid context here background。

 I'm going change this to paper oops put it in quotes like that。

 And I'm going to use a font scale of 1。4， which also seems to normally work。

 and we'll change that if it doesn't work。 Okay， so to create a heat map with data。

 you are basically going to have have to set up in a matrix format variables。 And with that。

 let's just let me show you exactly what I mean。 So we have our crash。



![](img/23c081e38820296b990078a6472c5936_1.png)

Data frame All right， there it is。 Well what we need to do to create a heat map is we're going to have to have this data that is on our columns go and line up not with indexes like this but with these columns also being used as rows and there's two main ways to do that and I'm going to show you how to do both of them。

 both of the options that are available Allright so let's say crash and this is going to be matrix。

 one way you can do it is to go and get crash data frame and call correlation function on it and basically correlations going to tell you how influential variable is going to be on your results so that is going to create that and I can show you exactly what it looks like so see now you have your columns and your rows all lining up here instead of using those different index。

And this is exactly what is going to be used to create your heat map and you can look at this data right here and you can see。

 for example， that no previous accidents， at least in our data set is heavily correlated with accidents while things like insurance premiums are not okay and you can also see alcohol usage is also heavily correlated with somebody being in an accident okay but the way we're here to talk about heat maps are not looking at just basic numbers so let's create a heat map so I'm going to say heat map and I'm going to be using our crash matrix。

And I'm going to say that I want to add annotations。

 which is going to be the numbers in the center of each part of our heat map。

 and if you've created heat maps inside of mapplotlib you know how much easier this is using Seaborn and there you can see that was how quick that create heat maps inside of mapplotlib is like four or five。

 six lines this is one all and this is a color map which comes from the mapplotlib page that I just showed you previously see this one so you can use any of those different color maps and you can see exactly our heat map lines up and it's basically the same sort of data except it looks much nicer so let's go and I want to show you the other way to go and create the matrix so let's go and I'm just going to leave that be exactly the same you're also going to be able to create a matrix by using what is called a pivot table。



![](img/23c081e38820296b990078a6472c5936_3.png)

![](img/23c081e38820296b990078a6472c5936_4.png)

![](img/23c081e38820296b990078a6472c5936_5.png)

![](img/23c081e38820296b990078a6472c5936_6.png)

![](img/23c081e38820296b990078a6472c5936_7.png)

![](img/23c081e38820296b990078a6472c5936_8.png)

![](img/23c081e38820296b990078a6472c5936_9.png)

![](img/23c081e38820296b990078a6472c5936_10.png)

How don't I just use completely different data， I'm going to go and get some flight data。

 I'm going to call it flights。So SNS。And load。Dataet and the data set we're using this time is built in again it called flights and there you can see and basically what it is is based off of years and months how many people flew on airplanes All right and you can also see there's indexes here and we can't go and create a heat map of this unless we come in and put what is in the columns in the rows and show how they are correlated with each other So we're going to do is we are going to create a pivot table So I'm going to go and call flights dot pivot table and it's just another way to go and get your columns put them in rows and correlate all the data that's what it is so I'm going to say that I want to create a matrix with an index of months and I want my columns to be equal to year and I want the actual values from our data to be passengers You can see exactly where that comes from all three pieces of data will be used。

And if I run that， you can see that we went and have our months on the left side and our years across the top and the number of passengers that flew in those specific years and months is what you see as our actual data All right this is very。

 very useful What I want to do now is go and actually create this heat map I'm going to say heat map use our flights data I'm going to use my color map。

 which is the blues one that I kind of like you can also go and separate your data by putting white lines inside of here。

 I'm going go and show you what it looks like first off though oops， flights。

 this is just going to be S and S we don' need that Alright。

 so you can see there is our new heat map based off of our flight data but you're also going to be able to come in and put lines between the data if that makes it easier to work with and but it doesn't show up unless you come in and also define line width。

And let's try just using one and there you can see how it's all divided up and you can also see that it makes a lot of sense that most of the flights take place in July and August and also over time that more people have been flying since 1949 up to 1960 All right so really cool information and now what I want to do is talk about cluster。



![](img/23c081e38820296b990078a6472c5936_12.png)
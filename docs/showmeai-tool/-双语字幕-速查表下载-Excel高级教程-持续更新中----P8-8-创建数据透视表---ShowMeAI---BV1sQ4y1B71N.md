# 【双语字幕+速查表下载】Excel高级教程（持续更新中） - P8：8）创建数据透视表 - ShowMeAI - BV1sQ4y1B71N

![](img/0f792ae8690d5c7e0534af8ca3c54600_0.png)

In this tutorial， we're going to learn how to use pivot tables in Excel。 And for some reason。

 pivot tables have this reputation as being kind of hard to use。 And at first。

 it probably will seem that way to you。 But after watching this video。

 I hope that you'll see them as being not too complicated to use。 And for this tutorial。

 I've created a spreadsheet that is an inventory of synth pop Cds。

 Let's say that I own a Cd store that sells exclusively the best kind of music ever made。

 which is synth pop。 I don't have a store like that。 Maybe I should。 But I don't。

 But what I've done here is I've created this spreadsheet that lists some of the important information that I want to track for my hypothetical synth pop Cd store。

 I have listed here several bands。 Some of these， no doubt you've heard of like depeche mode or perhaps erasure O M D。

 But there's also some here that are a little bit lesser known。 but I think are really excellent。

 Next， we have albums and these are their most recent album。

From these bands these are albums that I've recently picked up myself and listened to and really enjoy。

 Next we have a column for genre。 It's all really synth pop。

 but for some reason some of these get labeled as rock for example。

 the killers and they do have a mix of rock and synth pop and new wave kind of blended all。

 but anyway， we have the genre listed an item number。

 which is more of an internal number just for my hypothetical store to use we have the price of the CDd and this incidentally is the current actual price of the CDd on Amazon。

 Next we have the quarter。 and so I'm tracking each quarter of the year and tracking how each of these CDds does during that quarter。

 Next I have the number of copies sold for each album in each of these quarters and then I have a formula here to calculate the total number of sales In other words。

 the amount of money brought in and it's a simple formula number of copies sold multiplied by the price。

 so this is a nice useful spreadsheet。me track my small business and what are the big moneymakers for my business。

 The problem is with all of this data， it can be kind of hard for me to drill down and to really see certain information like for example。

 how did I do in the first quarter altogether with all of these Cs and their sales How did my business do in the first quarter Well that's a little bit difficult I would have to maybe copy paste each of these first quarter sales numbers into another spreadsheet or another part of this spreadsheet and then I'd have to do a formula to calculate that number or another example。

 what if I wanted to know specifically how well did the darkwa music that I sold how well did it do or what if I was selling more than just one Cd bype mode What if I was selling two different C or three different Cs by them What if I wanted to calculate the total number of copies sold of depesh mode Cs regardless of what the album is Could I calculate that on my own Yes I could I could create a report basically just by。

Highlighting copy paste， but honestly that could take quite some time to do and it might be likely that I would make a mistake and it's just a lot of work and effort。

 but fortunately， a pivot table can really help me in this situation just to give you a quick definition of a pivot table a pivot table is an Excel tool that allows you to reorganize and summarize certain data in the spreadsheet and specifically in selected columns and rows of data and it not only reorganizes and summarizes that data but it produces a report a report that is going to be helpful to you and one important thing to recognize about pivot tables is that they don't really change any of your data when I create this pivot table in just a minute it's not going to change the data in my spreadsheet this is all going to stay intact。

 Nothing's going be changed at all。 it just helps me to look at this data in a new way so let's get started Now the first thing to consider when you're about to create a pivot table is that it's。

Very important that your data be organized Well， it really does need to be a list。

 you need to have columns with headings or titles， So that's what I have band album genre， etc ce。

 And then a list of items。 And as you can see they can be repeated items that's fine but it needs to be a vertical list。

 Also it's important that you not have any blank rows。 Sometimes for whatever reason。

 people end up with a blank row in their spreadsheet and that's not good if you want to use a pivot table。

 So before you use the pivot table tool， make sure that your data is good that there's no blanks in the data。

 So I'm going to delete that row to get it back into a condition that will work well。

 Also you need to be careful about extra data。 So， for example。

 in this spreadsheet what if I had over to the right side just some notes written here like maybe need to update maybe that's just a note to myself that I need to update these numbers。

Maybe I have down here the word total and then I've put in a formula that adds everything up you don't want to have extra data like that either to the side or underneath your data you need to have a nice data set that doesn't have any extra unnecessary information around it so the next recommendation that I have before you use the pivot table tool you don't have to do this but I highly recommend it and that is you need to format your data as a table So to do that all I have to do is click somewhere inside the data so I'm gonna click here on the word material and then here on the home tab home ribbon in the Sts group I'm gonna click on format as table I can pick any of these styles to format my data as a table I'm going go with this one then it wants me to double check that I'm getting all of the data for the table and it looks pretty good to me but you could change these numbers if you needed to Yes my table has headers that's these column titles across。

The top I'll click OK and look it formatted my data as a table。 I like how that looks。

 So even though you don't have to do this when you're using pivot tables。

 it is a good idea to format your data as a table and the reason why is because that way now that it's a table let's say I add another CD to my inventory let's say brandon flowers the desired effect as I add in this information notice that it's adding it directly to the table。

 it recognizes that it's part of this data set and it formats it along with the rest of the information and not only that but when you use the pivot table。

 the information in the pivot table will be updated when you add additional in this case。

 CDs to the table so let's create a pivot table for this table full of amazing CDs to do this all I have to do is go up to insert and choose pivot table and right away Excel wants me to give it some information about the pivot table。

Notice that the first thing it's asking is if the data is a table or a range or if I would like to use an external data source in this case。

 I want to use a table。 it is a table and it guessed that I wanted to use table3 and that is this table table3 If it guessed wrong you could pick a different one but in this case it worked well it guess the right table Most likely because that's where my mouse was next I'm supposed to choose where I want the pivot table report to be placed somewhere in this existing worksheet If so I'm going have to specify the location For me I almost always choose new worksheet that way it just gives me another sheet and it puts the pivot table there on the sheet it's just cleaner that way so I'm ready to create the pivot table I just click OK and look it created another sheet for me down here and it gives me a little bit of instructions to build a report Choose fields from the pivot table field list and that pivot table field list is over here at the right you can see that a panel opened up on the right and this is the pivot table。

Fields panel or pan。 And what we have here is a list of the column headings or column titles that I had typed in this original spreadsheet。

 So band album genre， etc。 band album genre And then down below I have these four areas filters columns rows and values and what this is for is Excel is basically asking me in this pivot table report that I'm about to make。

 What do I want to be arranged in rows。 What do I want to be arranged in columns And what values do I care about in this report。

 And then finally， what filters， if any， do I want to apply to this report So let's say I want to know which bands were my best sellers in the first quarter of the year。

 Well the column for bands is gonna be important。 So I'm gonna go up here and click on bands and I'll just drag that down。

 and I'm gonna put that in the rows box。 As soon as I did that。 Look what happened。 I got a list。

OfAll of the bands Now， what data do I care about Well I want to know the total money brought in。

 So I click on sales， and I drop it down in the values box down here。

 So now I can see for each band how much money was brought in my hypothetical small business。

 Now maybe I decide no that's a mistake。 I don't necessarily want to know the amount of money。

 I just want to know how many units I sold So copies sold would be the one to drag down there。

 And now that changes my pivot table。 It's showing me different information now。 honestly。

 though I think I would rather see the sales。 So I'm going put that one back。 But remember。

 in my example， I wasn't interested in the total sales I was interested in the total sales for each band in the first quarter。

 So quarter is also important to me。 and I'm going drag quarter this time into the columns box。

 So now I can see each band and each quarter， how much money was brought in for selling their Cds。

 Now， if I had dragged quarter down to。Rs instead of columns。 What would that have looked like。

 I'm going to remove that field so that you can see。 I'll drag it down to rows underneath band。

 And so now the data is still the same。 It's just arranged differently on the screen。

 I have the first band here black audio and it's in a row but I also put quarter in a row。

 So it listed the four quarters that are associated with black audio right underneath black audio And so Excel is really smart about this。

 it figures out that these quarters in the original spreadsheet are obviously referring to quarters for black audio and so it keeps that data together。

 and then covenant the sales quarters for covenant are listed there。 topesh mode。

 the killers on and on。 So I just wanted you to see that that the same data can be illustrated in different ways based on the box that you drag the column name into all right now the last box that we need to think about is filters so I'm going drag quarter down to filters as well now。

As soon as I do that。 look what happened。 The column titled Quater can't be in both of these boxes。

 And so it disappeared out of the columns box， and it moved to the filters box。 Also。

 look what it did to my data。 It's no longer spread out by quarter。 But that's okay。

 I've basically applied a filter here。 here at the top， it says quarter all。

 But if I click on this dropdown arrow。 instead of all， I could try selecting one。

 And now it shows the first quarter sales for each band。

 It looks like the killers was the bests band in first quarter for my hypothetical company。

 their new album， wonderful， wonderful is pretty wonderful。

 I think And you should check it out if you haven't already。 But anyway。

 I hope that you can see how useful this is。 Now， of course。

 these pivot table reports can get pretty complicated。 If I wanted to。

 I could include the album down here in the rows。 I could include the genre in the filters so I can filter out。

 let's say all of the music。cept for synth pop。So that reduced it down dramatically I could put price in the columns if I wanted to。

 and so you can really get some complicated pivot table reports going here in a future tutorial。

 I'll show you another way to create pivot tables and it's kind of a shortcut a lot of people find it to be easier but I do think it's important if you're going to use pivot tables to learn how to do it the right way the old-fashioned way I guess of manually selecting everything that you want and organizing your pivot table report the way you want it to be using this pivot table fields panel so please watch for that future video。



![](img/0f792ae8690d5c7e0534af8ca3c54600_2.png)
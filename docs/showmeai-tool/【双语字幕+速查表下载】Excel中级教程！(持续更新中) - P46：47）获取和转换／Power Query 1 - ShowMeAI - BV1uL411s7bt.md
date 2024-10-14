# 【双语字幕+速查表下载】Excel中级教程！(持续更新中) - P46：47）获取和转换／Power Query 1 - ShowMeAI - BV1uL411s7bt

![](img/acec3a93d9b497450000e00a04171fff_0.png)

This is the beginner's guide to Excel， get and transform。 otherwise known as power query。

 In this video， I'll show you how you can use get and transform to take data that's in a spreadsheet and transform it。

 Clean it。 F it。 Make it better。 and easier for you to use and to read。

 So let's get started learning get and transform。 Take a close look at this worksheet。

 As you can see， it's a list of movies。 and other information about those movies。

 And let's say that I got this spreadsheet from somebody else。

 Maybe someone that wasn't careful about how they formatted the text。

 You can see there's various inconsistencies with using bold or not using bold。

 There's extra spaces that I don't like in my data and different colors and things like that。

 The person that created this must have copy and pasted some of this information from the internet or from emails and things。

 And so it's not standardized。 It's bothering me。 And I would。Like to get and transform this data。

 So step 1 is to simply click inside the data somewhere。

 So I have a range here of several rows and columns。

 I just need to click somewhere inside that range of data。

 and then I can go to the data tab and look in the get and transform group。

 noticeice that there are various sources from which I can get the data。

 I can get it from text from the web from a table or range。 and there's a button here。

 a drop down button that you can click to see even more possible sources for getting data。 So again。

 making sure that I've clicked somewhere in my range。 I'm going to click from table range。

 and Excel has determined where my data is。 Yes， my table has headers。 I click O。

 and notice what it did， It turned my range。 my data into a table。 and it opened this new window。

 This is the power query editor。 And if you're not used to。this window， it can be confusing。

 It looks like Excel just changed dramatically。 And one reason for that is that this window is filling my screen。

 So I'm going to click this button here in the upper right to minimize the power query editor just a bit。

 so that you can see that my original spreadsheet is still there in the background。

 My data is still intact。 The only thing that changed about it is that it was turned into a table and on top of my original sheet。

 I have this power query editor。 I'm going maximize it again。

 I want you to think of this power query editor as being kind of like a sandbox。 that I can play in。

 I can change the data。 I can try some things out， and none of it will affect or ruin my original data in the spreadsheet。

 And then I can choose to add this data to my spreadsheet or not。

 And let's take a close look at this power query editor。

 In addition to being able to see my spreadsheet data here。 on the right side of the screen。

 I have the query settings and included in that。I have a list of applied steps。 It says source。

 In other words， I established a source for my data。

 and that's the range that was turned into a table。

 and it says changed type that probably refers to changing my range into a table as I make additional changes to this data。

 you'll see those changes listed here。 Okay， so let's see how we can improve this data。

 You'll notice that my title column is selected。 I could switch to category or second category or rating whatever I want to do。

 but I'm going start with title and with that selected， I'm going go up here to my tabs。

 noticeice that by default I am on the home tab and there are some options here that I can use to transform this data。

 but there's even more options here on the transform tab by clicking on that。

 I can go to format and click and I would like to change all of the data in my title column to be lowercase。

 So by clicking that button。And switching to lowercase。 Look what happened。

 Every movie title now is in lowercase only。 And that right there is an improvement。

 because look at how it is in the original spreadsheet。 Some titles are in all caps。 Some are not。

 It's just a mess。 And so in this sandbox in the power query editor。

 I'm trying to standardize things and make them look the way they should。

 Now that everything is lowercase。 I can go back to the format button and choose capitalize each word。

 I think that's an improvement。 Next， I'd like to fix all of these extra spaces that you can see in my title column。

 Way too many spaces between gone and with。 there's too many spaces here in front of the word Matilda。

 just lots of problems with spacing to fix that。 I can go again。 to the format button。

 And I'm going to try trimming the excess spaces。 When I click trim。

 you'll notice that extra spaces at the beginning and also at the end of the entries in these cells have。

Been cleaned up。 The extra spaces have been removed。 Now， what about the spaces between words。

 That's a little bit tougher。 And there's probably a better way to do this。

 But I'm going go up here to replace values。 and I'll click and I want to Excel to find examples of three spaces in a row。

 So I just tap spacebar three times。 and I want to replace those three spaces in a row with just one space。

 So I'm clicking here in the second box and tapping spacebar again。 I'm going to click O。 Now。

 watch the data as I click O， You can see that that solved a lot of the problems with spacing。

 I'll try it again。 I'll go up to replace values this time。

 maybe I'll replace two spaces with just one。 click O， again。 that seemed to improve my data。 Now。

 let's look at my rating column。 If I click on the word rating。 It highlights the whole column。

 And I've noticed a couple of problems with this column as well。 Some of these movies are listed as。

And others as R rated。 And P G13， I don't think is correct either。 So we'll use replace values again。

 So value to find R rated。 let's replace that with R。 And I'll do it again。

 replace values value defined P G13， replace with Pg dash 13。 click O。

 and it cleaned up the data for me。 Now， like I said， notice here at the right， my applied steps。

 I have a list of every step I've made。 If I regret any of these。 Let's say I regret fixing R rated。

 I can just click this red X。 Are you sure you want to delete this step。

 It could cause some problems。 Let's try it out。 I click delete it removes that step。

 and it did not cause problems for me。 Now， there are a lot of other ways in which I can transform this data。

 I've shown you mostly this format button and the replace values button。

 and those are some of the most powerful options。 But there's much more。 And if you're interested。

llMake more videos showing you some of the other options。 But for now。

 I want to also show you that instead of simply using these transform buttons that are here。

 sometimes it's a little easier just to right click on a column title and choose options from the dropdown that appears。

 So I'll replace values again and change R rated back to R click。

 let's assume that I'm completely happy with the transformations that I've made of this spreadsheet。

 and I'm ready to apply it to my workbook。 All I have to do is click this home button and then click close and load。

 When I click close and load， it does take a little while sometimes but it creates a new spreadsheet。

 you'll notice that my original is still here sheet1。 Yes， it's a table now。

 but there's also a sheet4 that has all of my cleaned up data。

 and I can browse down to see that all of the data came in。 I can now X out of this panel。

 And if I really do prefer this data。To the original， I， of course。

 could right click on the original and delete that spreadsheet， click， delete。

 and I could even right click and rename sheet 4 to be my new sheet 1。

 And I've just used get and transform， which used to be called power query。

 to clean and transform the messy data into good data that I'm ready to work with。

 There may be small changes that I still need to make。 But the majority of the work has been done。



![](img/acec3a93d9b497450000e00a04171fff_2.png)
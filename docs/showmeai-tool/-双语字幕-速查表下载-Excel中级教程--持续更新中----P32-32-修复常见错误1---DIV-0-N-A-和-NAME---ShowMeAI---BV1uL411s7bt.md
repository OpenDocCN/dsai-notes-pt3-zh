# 【双语字幕+速查表下载】Excel中级教程！(持续更新中) - P32：32）修复常见错误1 - DIV／0、N／A 和 NAME - ShowMeAI - BV1uL411s7bt

![](img/a4c5d4348b8f0db6a99a8f0818bc7cea_0.png)

In this tutorial， we're going to look at how to fix common Excel errors。 And this is the first in a three part series。 In part 1， we're going to look at the div0 error。 The N error and the name error。 And to help with this。 I have a workbook with three unrelated spreadsheets。

 Each one is a good example of one of those errors。 If you would like to follow along with me in the description below this video。 I have a link that you can use to download this workbook。 and it makes it so much easier to follow along。 But let's get started First with the div0 error。

 You can see my spreadsheet here， is tracking my purchase history for some supplies。 And you can see I'm getting a div 0 error a couple of times here in the spreadsheet。 Well。 what this stands for， is dividing by0。 dividing by0， as you probably know， is not possible。 And so because it's impossible when I try to do it。I get this error message in Excel。

 So what's happening here。 Well， I have a formula set up。 You can see it here where what's happening is it's dividing the total cost of a particular item tape in this case。 by the quantity that I purchased， and it gives me the total cost per item。 So this is being divided by this。 Okay， so let's look at the next row。 here I have nothing0。

 basically divided by 0。 Well， that produces an error message because it's not possible to divide 0 by 0。 It's not possible to divide 100 by 0 either。 So that error message is accurate。 It's telling me the truth。 There's an error going on here。 The thing is， it looks so bad。 It looks so ugly in my spreadsheet。 So how could I fix that。

 And you can see there's another example of it down here。 Well。 one way to fix it would be to not divide by 0。 So if I go out and buy a box of markers。 Let's say it's $6。 and I get one。Now that I have something other than0 in this cell。 it updates and there's no error message。 But what if I don't want to buy a box of markers or don't need to。

 Well， let's just zero those out。 and now what I'll do instead is I'll change up my formula。 So I'm going go back up here to cell F2 click on the cell。 and I'm going delete what's there in the formula bar。 I of course could do the same thing here inside the cell。

 but sometimes it's nice to use this formula bar。 It's just a little bit cleaner sometimes So I'll type equals。 and then I'll start out with something called if error。 it's kind of a weird function to use。 but notice what it says returns value if error if expression is an error and the value of the expression itself otherwise。 So this basically helps guard against error and produces something if there is an error。

 Okay so if error left parentheesis。 and now I'll put in the total cost for the tape。So D2。 So I type in D2 divided by E2。 and then I put in a comma。 And then after the comma。 look what it's expecting。 It's expecting the value if error。 So if there is an error in cell F2 based on dividing 60 by 32， If theres an error。

 what do I want it to print on the screen。 Well， I could just put two quotes or a quotation mark。 a space and another quotation mark。 and then close parenthesis。 You really don't need the space in between。 though。 Now I'll just tap enter on the keyboard。 And look， there wasn't an error。 And so it just produced the result of D2 divided by E2。

 And now I'll drag that down all the way down to the bottom and release what changed。 Well。 the div0 errors went away And why because of this new formula。 It's checking for an error。 And if there is an error， I tell it to print nothing in the cell。 And I copied that down using。Autttlefi handle。 So that's true of all of this column。 So that's one way to handle it。

 Another way would be to instead of putting nothing in the cell。 I could put a message to the person who's looking at the spreadsheet。 I could type in something like no purchases。 So that would explain why it's blank。 There have been no purchases。 So I tap enter and notice that it updated the entire column。

 probably because I'm in a table， it did it that way。 So now instead of the ugly error code。 I get this no purchases message。 So that's a little bit about the div0 error in Excel。 Let's move on to another spreadsheet and look at a second error that comes up from time to time。 And this is the N error。 And this comes up most often when you're using V lookup or H lookup or any other function or tool in Excel where it's looking for a specific thing。

 So you can see here I have a movie inventory and I'm using V lookup to tell me the。Of various movies。 so I could click here， type in the Martian tap enter on the keyboard。 and it tells me Pg13。 So that's using Vlookup。 If you haven't already watched my tutorial on Vlookup。 you're missing out， you need to watch that。 But for the purposes of this tutorial。

 Let's just move on and watch what happens when I type the lion king。 I tap enter。 and I get the NA error。 So you can probably figure out the reason why I'm getting N because it's searching the spreadsheet。 it's searching the data that I've provided for the lion King and it's not available。 it's not finding it。 Now watch what happens if I put the lion king into this spreadsheet。

 So the Lion King。 and I'll put in the 2019 version of it。 So I've put that information in。 Now let's go back up and try it again。 the lion king。 I tap enter。 It still doesn't work。 I still get that NA error。Now， if you get an error like that and you're pretty confident that the words that you're looking for are in the range that you're looking in。 That could be for a couple of different reasons。 In this case。

 it could be that I've accidentally put in too many spaces in a cell。 So， for example， here。 the lion king。 noticeice that there's an extra space after the G。 When I search for the lion king without a space， it doesn't work。 If I add a space in here after the G， will it work， will it fix it， Yes， it does。

 But instead of fixing the search term here。 there is a way to actually fix the data。 And it could be that other movie titles also have too many spaces included。 So I want to repair that data to make sure that there are no extra spaces。 to do that。 there may be a better way， but this is how I would do it。

 I would just right click here on column B and choose insert。 So that gives me a new column。 And then here in the column， I'll click on cell B。Tap equals。 and then the word trim left parenthesis。 I'm gonna to trim the title Star Wars。 And then I should put a right parenthesis。 you don't really have to。

 but it's a good idea to get in that habit。 I'll tap enter。 And it seems like nothing changed。 And that's true。 Nothing changed。 But the reason why is because Star Wars didn't have an extra space in it。 But some of these other titles do。 So now that that's done。 I'll use the autofill handle。 click and drag down the page to copy that formula。

 And now I want to replace what's in column A with what's in column B。 but the tricky thing is column B is really made up of just formulas that depend on column A。 So I do have to be a little careful with this。 but I'm just going to call this title as well。 And then I'm going click and drag from title all the way down to the bottom of my data。

 And then I will copy that either by right clicking and choosing copy or control C to copy。 And then I'll click here and。Right click。 but I don't want to just paste。 if I paste。 there will be some errors。 But if I go here to paste values。 What it does is it converts these formulas into actual values In this case， titles of movies。

 So now I don't need this column anymore。 I can right click on B。 chooseose delete。 And that should have cleaned up all of these titles。 it should have trimmed out extra spaces and look， it worked。 So now when I type in the lion king。 it tells me the rating。 Let me show you another example of how you could have the correct data in the sheet。

 but it still gives you the N error。 a few years ago， a movie came out called 42。 So I'll just type in 42。 I don't recall exactly the year it came out。 but I'll put in some data for it。 Okay， so now that that's in if I do a search for 42。 it's gonna work。 it finds it。 It says it's Pg 13。 But from time to time。

 that might not work for you。And if it doesn't， it probably has to do with the number format。 So right now， this number in this cell is considered to be a number， but in some cases。 it might be considered to be a text 42 is actually the title of the movie。 It's not really just a raw number。 So if you're ever doing a V lookup and it gives you an NA error and you're dealing with numbers。

 you might consider making sure that the column or row is formatted correctly。 either as text in this case， or as numbers。 just to make sure that these cells match the format of this cell。 Now， similarly to my purchase history example。 I can fix this。 I can make it so that if I type in a movie that's not in my collection。

 I don't get this ugly error message。 The way that I would fix that is I would click on the cell and change the formula in front of V lookup。 I'm going click in front of the V， I'm just going type if error left print。And then after the Vlookup information， I'll put a comma。 and then in quotes。 I'm just going to put the message that I want to send to the user of this spreadsheet。

 not in inventory。 put in the quote put in the right parenthesis and then I'll tap enter on the keyboard。 Starman is not in inventory。 So now if I type in star Trek。 that's also not in inventory。 but if I type the BfG it is there and has a rating of Pg。 So once again。 this if error function saves the day and makes our spreadsheets look not so ugly when these error messages come up。

 There's one more error message that we're going to tackle in this video。 and that is the name error。 in another video， I show you how to name cells in Excel and I've done that in this spreadsheet。 This is a health tracker for Jason Smith and notice that the cell that has his age in it。 cell B3 has been rename。It's called age。 And I've also renamed B4。 I've called that height。

 So now when I want to calculate the Bmi or body mass index for Jason。 I can just click here type equals。 and then I'll grab his weight So B7 multiplied by 703 divided by。 and I can just type in the word height， and it should grab the data that's in the cell called height in this case B4。 But what if I misspell height。 What if I type in something like that。

 And then I continue on with my formula， which would look something like this。 and then I tap enter on the keyboard。 look， I get a name error。 and what this is trying to tell me is Excel thinks I might have used the wrong name and I did instead of spelling height correctly。 when I was trying to reference the cell called height。

 I spelled it incorrectly And so there is a name problem。 and that's why I get the name error message。 So how do you。Fix that。 you just need to be careful whenever you see that name error。 it usually means that you've typed something incorrectly。 you've misspelled it。

 or maybe there isn't a cell named this exact thing。 So you need to check to make sure that you've used the correct words spelled correctly。 One way to do that with named cells is just go here to the upper left corner， This is the name box。 And if you click this arrow， it gives you a list of all of the names that you've used in this workbook or spreadsheet。

 So you can see height， it's spelled that way。 that's how I need to spell it when I'm typing another example of this error could be when you're trying to do a sum or really any other function。 So let's say I try to type sum and I want to sum this entire column left parenthesis B1 through B59。

 and I tap enter。 and that works fine。 But what if I accidentally leave the M off of sum and I tap enter。 Well， that doesn't make sense。 sum without the M is just not gonna work。And so Excel is telling me there's a naming problem。 you'll have the same problem if you try to do an average。 But instead of typing out average。

 what if you just put A V G。 it's gonna give you a name error。 One more thing to watch for。 when you get that name， error message。 It's possible that the reason why。 is because in your formula you've used quotes。 when you shouldn't use quotes。 or you needed to use quotes。 So for example， in this case， I've added quotes around the word height。

 when I tap enter， I get an error message。 It's a little bit different error message。 but still。 that is something also to watch out for。 So those are three common Excel errors。 div divided by0 N a and name。 in a future video， I'll look at other error messages， including null。 nu， ref and value。 In the meantime， I hope you found this tutorial to be helpful。 If you did。

 please click the like button below。![](img/a4c5d4348b8f0db6a99a8f0818bc7cea_2.png)
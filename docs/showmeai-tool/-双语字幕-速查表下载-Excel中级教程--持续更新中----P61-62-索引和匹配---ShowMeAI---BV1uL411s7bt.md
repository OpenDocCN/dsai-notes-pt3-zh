# 【双语字幕+速查表下载】Excel中级教程！(持续更新中) - P61：62）索引和匹配 - ShowMeAI - BV1uL411s7bt

![](img/639edd188732e38b50bb2a08cd5efa02_0.png)

In this video， I will show you how to use two functions。

 index and match to do powerful lookups in Microsoft Excel。

 And here's the sample spreadsheet we're gonna to use for this video if you want to download it and follow along。

 you can find it in the description below this video。

 And what we have here is a record of sales for a hypothetical media business that sells these things。

 and they've been tracking each month， how much they've sold in each product category。

 So what I'd like to be able to do is go over here on the right next to product category I'd like to be able to type in。

 let's say DVDs and the month of let's say June。 and then be able to see the total sales of DVDs for the month of June。

 So how can we accomplish this。 Well， using index and match is one of the best ways to accomplish that。

 Let's start by trying to understand each of the functions， index and also match。

 So what index is meant to do is to help you pull out information。😊，From a range。 So for example。

 I could use index to search this range and produce the information that's in the second column and the third row。

 for example， So second column third row， it should be 105 and then it would produce that result。

 Let's look at how it works here in cell J 7， I'm going to type equals index and then left parenthesis。

 As usual， Excel gives us some hints and some tips。

 there's a couple of different paths we could take， I'm going to stick with the top example。

 it's looking for an array， which is basically a range So just like in my earlier example。

 I'm going to click and drag to highlight the range of numbers in the spreadsheet next。

 Excel is expecting a comma and then the row number comma column number。

 So I'll put in my comma row number comes first So let's say I do want to produce that 105。

 If you remember my selection started here and。Continued all the way down to here。 So this is row1。

 even though it says two here at the left。 This is2。 and this is3。

 So I'm gonna to type in the number3 to indicate the third row， and then I'll put my comma。

 What column is this。 Well， it's the second column of what I had selected。 So I type 2。

 And then I should put in a right parenthesis in many cases you don't have to put in the right parenthesis。

 and then just tap enter。 noticeice that it produced the correct number 105。 So it worked。

 And that's what index does for us。 It helps us to identify the third row and second column or fifth row and 10th column and then produces the results。

 Whatever numbers we put into here。 that will determine which row and which column it looks at and then produces the number or the data that's in that cell。

 Now， if you're looking at that and saying to yourself， Well， that has limited use。

 You might have a point。 If that's all it did。 I wouldn't be too excited about using index。

 There are many other things you can use it for。But in a minute。

 I'll show you how you compare it with match to do an index and match。

 and that really makes it very useful。 Let's first， though move on to match here in cell J 8。

 I'll type equals， I'll type in match for my function followed by a left parenthesis。

 Next Excel is looking for a lookup value In other words。

 what is Excel gonna look for as a result of this formula。 Well。

 maybe I want it to look for a specific month。 let's say July。 Now。

 because July is a word and not a number。 I should put that in quotation marks if I want it to work。

 So July。 next Excel is expecting a comma and then the lookup array。 So I'll put in the comma。

 What is the lookup array。 Well， what that means is what is the range in Excel that I want Excel to examine and search for this word July in Well。

 the array is here。 I'll click and drag to select each month。

 next Excel is expecting a comma and then。LookWhat it does， It's saying。

 what kind of a match are we looking for， Are we looking for a match that is less than this。

 an exact match or greater than this Now， when it comes to words。

 it's kind of confusing to think about less than greater than but let's go with exact match。

 So I'll just put in a0。 that represents exact match。

 I should put in my right parenthesis and then just tap enter。 and it produces the number 7。 Now。

 why did it produce the number 7 Well， because I was having Excel search this range starting in a2 through a12 looking for the word July。

 if you counted out it's 1，2，3，4，5，6，7。 It's the seventh item in the array or range。 So that worked。

 Let's do a second example。 let's say I'm looking for the word software。

 I could type equals match left parenthesis。 my lookup value is software the lookup array is this information here。

 again。I want an exact match。 So0， and then the right parenthesis tapap enter。

 Let's check it to make sure it was accurate。 We're looking for software。 Soft is 1，2，3，4，5。

 It produced the right number。 Again， if you're thinking to yourself that's nice。

 but this isn't very helpful， but what if instead of typing the word software here。

 What if I tie the match function to something that changes for example， DVDds and June。

 this is an area of the spreadsheet that I expect to change。 I expect to type in different months。

 different categories。 And so if I can tie these match examples to something that changes。

 it becomes a little more powerful。 let's take a look at how to do that。

 So here in my match example number one， I could delete the word July and instead of July I'm just going click in this blank month cell tap enter。

 and it gives me an error it's not applicable。 but what if I now put in the word July tap enter it produces the same result as before。

The number 7。 But the nice thing about this is this is adjustable， so I could put in August。

 and it changes。 I could put in January， and it changes。 same with match example number two。

 Instead of typing the word software in quotation marks。

 Why not simply click here where the product category will be typed。 Tap enter on the keyboard。 Yes。

 I get an error the first time when it's blank。 But now when I type in the word books。

 It produces a result。 and this is an adjustable result。

 I can change it to DVDds and the match updates。 Okay。

 so that makes it a little more useful and exciting。

 these formulas now are tied to something that is a variable， it changes。

 Now we can put both of these functions together。 index and match in one formula to automatically produce the sales of DVDds in the month of January for example。

 So let's do that。 I'll click here and sell J5 type equals index left parenthesis。

 If you remember the point of index。😊，Is to look at an array or a range and then produce results based on the column and row that are specified。

 So it's first looking for an array。 let's give it that same array that we did before。

 Just click and drag to select that range。 Now Excel is expecting a comma and then the row number comma column number。

 So I'll put in my comma。 Now what row number do I put here。 Well。

 I don't know which row number to put。 It's going be a variable。

 it's going to change based on what has been typed into this cell here for month。

 that will determine the row。 and I don't know what's going to be typed in that cell。

 So this is where we use the match function。 This is using one function within a formula that starts with a different function index。

 after match， we put a left parenthesis。 It's looking for a lookup value。

 I don't know what the lookup value is。 It's something that changes。 but it's going to be a month。

 So I'll just click here。 this is where the month will be typed by the end user。

 noticeice when I click there it。Put the word January here。

 It put the cell reference J4 That's perfect。 That's what I wanta Lookup array。

 What range is Excel going to search looking for whatever is typed in this cell。 Well。

 it's this range here。 So I click and drag to select only the months。

 No empty cells above or below just the months I put in my comma what kind of a match is this going to be。

 it's going to be an exact match。 So0。 and then my right parenthesis。

 Now Excel takes me back and reminds me that yes， I've been using match。

 but this is really an index formula。 That's the function that started off this formula。

 And so it's reminding me I need to now go in and put in a comma and then the column number。

 So here's my comma for the column number。 again， I need to match it。

 I don't know exactly what the column number is gonna be。

 but it's going to be based on what's typed here in the product category box that will determine which column I'm interested in left parenthesis Now Excel is looking for a lookup value。

I don't know what that's gonna to be。 It's a variable。 It will change， but it will be located here。

 So I click there。 J3a。 What's the lookup array。 What will be searched in order to find DVDds or books or Cds。

 Well， it's this。 It's this range here。 what kind of a match are we looking for and exact match So I put 0。

 and then write parenthesis。 And then I really should put another write parenthesis to finish off this formula。

 T enter and Excel produces a result for me，288。 Let's check it out。 DVDs in January。

 DVDds in January 288。 Now， we can go in and make changes to these cells。

 Let's say I'm interested in software in the month of October 30 So October 30。

 So this is working flawlessly。 Now this is helpful and kind of fun to use with such a small spreadsheet。

 But imagine instead of just 13 rows and 7 columns。 what if this spreadsheet。

 had so much data that it had 50 columns and。10000 rows or something like that。

 this concept of combining index and match to pull out a specific result out of your spreadsheet that would be even more helpful and useful。

 Now， some of you probably know that you can do similar things with V lookup。

 and if you haven't already， you should definitely watch my video on V lookup。



![](img/639edd188732e38b50bb2a08cd5efa02_2.png)
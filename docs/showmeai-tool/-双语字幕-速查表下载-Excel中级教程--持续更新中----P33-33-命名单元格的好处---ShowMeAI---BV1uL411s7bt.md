# 【双语字幕+速查表下载】Excel中级教程！(持续更新中) - P33：33）命名单元格的好处 - ShowMeAI - BV1uL411s7bt

![](img/9dd1003dd91567638f0fd301bbe58d5e_0.png)

In this tutorial， I'm going to show you some of the benefits that come from naming cells in Excel。 And to show this， I've set up a simple health tracker， or at least the beginnings of one。 Let's say I'm working as a personal trainer and I would like to help Jason Smith here to track his health and his improvement。 So I've got Jason's name here， his age and his height in inches。

 So now all I really need to do is write a formula and put it here in this cell。 and the formula will do most of the work for me， calculating Jason's Bmi or body mass index。 I have here a description of the formula that we need to create in Excel。 And that is Jason's weight multiplied by 703。 at least if you're using inches and pounds。

 And then divide that by Jason's height squared。 And the height again would be an inches。 So that's what we need to recreate in Excel in this particular cell。So let's do it。 Step1 is just to click on the cell。 Tap the equal sign on the keyboard。 Jason's weight for week1 of this tracker is going be right here。 So I just click there。

 multiplied by the asterisk represents multiplied by 703。 and then I'm going divide that by Jason's height。 So that's right here75。 I'll just click there on cell B4。 And then to put in squared。 you need to add this little symbol here。 for me， it's shift 6。 If I hold shift and tap 6。

 it puts that symbol in。 and then you put 2 for squared or 3 for cubed， etc cetera。 Now。 if I tap enter on the keyboard， it returns a number。 Now。 let's put a weight in there to see if it worked。 let's say 265。33。1 Bmi。 So I believe that that's correct。 But watch now what happens when I go to week 2。

 let's say Jason loses a couple of。 and I would like to use the。Auttofill handle here in the lower right corner of the cell to copy this formula that calculated the Bmi。 I'd like to just copy it down here so I don't have to retype it。 so I'll use that autofill handle it copies the formula。 but look it didn't work。

 Now the reason why is because when you use the autofill handle， it tries to in a smart way。 change the numbers in your formula。 So here in cell C7。 notice that the formula is looking to B4 for the height。 but when I dragged it down。 look now it's looking for cell B5。 Well that just gives it this instead of a number and so that's why I get this error message。

 So all of this can be solved and also it'll be easier for me to really understand my formula if I just name certain cells。 So here in B4 I'm going click on 75。 that's Jason's height in inches。 And with that selected if you look here in the upper left corner。There's something called the name box。 And right now it shows B4 as the name of that cell。

 but I can just highlight that， and I can change it to be called height。 Now。 when I was done typing height， I tap enter on the keyboard。 That's very important。 A really common mistake people make when they're trying to do this is they'll type the name and then forget to tap enter。 and they just click away。 and that way， it does not record the name that you want that cell to be called。

 and it can really throw them off later。 another way to do the same thing to name a cell。 instead of going here。 you can click on a cell。 and then go to the formulas tab and there in the defined names group。 you'll find define name。 So I'll click on that。 and it brings up this pop up。 and this accomplishes the same thing as what I did here in the upper left。

 but it does give me some additional options。 Notice that Excel automatically figured out what this represents。 It represents。The age of Jason Smith。 So it put in the word age for me。 Next。 what's the scope that I'm talking about here。 Do I want to create this name for the entire workbook for every spreadsheet that I put in this workbook or do I want to limit it just to the health tracker sheet。 In this case， it doesn't matter either way， I guess I'll leave it as workbook And then underneath that。

 I can type in a comment。 So this is the age of the client。 And then I'll click O。 And now that cell is also named。 So I have height and I have age。 Now to make sure that this worked。 you could go here to the upper left to the name box and click on the arrow that appears there。 When you click， it brings up any named cells that you have。

 You can also just go here again to the formulas tab。 define names group and click name manager and it brings up all of the names that you've established in your workbook or worksheet。 Now， a couple of things to be aware of when you name a cell in Excel。 First of all。 the name cannot begin。With a number or a symbol， it must begin with a letter of the alphabet。

 So watch out for that。 The other thing to avoid is putting a space in the name。 So if I try to edit this name。 So I select age， go to edit。 And if I try to put in age of Jason。 That wouldn't be a good idea anyway， because I want to use this for other people that are training。 But if I click okay， look， it doesn't allow it because I put spaces in the name。

 If you really want to have spaces， just hold shift and tap the minus sign on the keyboard。 and that'll give you an underscore。 but in most cases。 it doesn't really matter that much and you can just type it all as one word。 So I'll click okay to get out of there。 And then the final thing to watch out for is you can't use alphanumeric names。

 for example， B3 or F10。 Why can't you do that， because there already is a cell named F 10 or B3。 And so it's too confusing。 So try to avoid letters and numbers together in your。don't use blank spaces。 and the name must start with a letter。 Okay， I'm gonna close that out。 and let's try the formula again。 But this time， instead of using B4。

 I'm just going to use the name for B4 which is height。 So I'll delete what I already have in this space。 click away and then click back So this cell equals Jason's weight。 which is here multiplied by 703 divided by and then here at this point。 I could click on 75 if I wanted to and it would put in the word height。

 See that I'm going to delete that， though， to show you the other options that we have this time。 instead of clicking on the height cell， I'm just going to type the word height。 Now as I type it notice that my named cell pops up here as an option。 and that's what I want。 So I'll double click on it and then I need to still put that up arrow shift 6。

 and then the number two for squared。 and then I tap return on the keyboard。Now that I've done it this way with a named cell。 watch what happens when I use the autofill handle。 I pull it down and it works。 The reason why it works when you name the cell is because named cells create absolute references。 So when I use the autofill handle and drag it down， it tries to adjust based on the cell。

 And when I simply called this B4， it was changing it to become B5 and then B6 as I dragged down the page。 Well， it can't do that if the cell is named height。 It just always is an absolute reference to this cell and to Jason's height。 So that solved one of the problems that I have in the spreadsheet。

 And I can just click and drag this down all the way down to the bottom。 And now as the weeks go by。 and Jason loses a little bit of weight each week， we can track that and it's automatically done through this formula that references a named cell。 Now， sometimes people named cells simply for their own ease of use。And clarity。 So for example。 if for some reason I wanted to divide Jason's age by his height， I don't know why I would。

 but I could just type in equals， and then I could just type in the number 46 divided by 75 or I could instead of using named cells just click on B3 divided by B4 but because I've named those cells。 all I have to do is type in age divided by height and you can see it suggests height here Also one other thing to be aware of if you tap F3 on the keyboard you get a pop up with a list of all of your named cells and you can just click on the one that you want to use and click OK but either way。

 because of these named cells in my head， I'm thinking in real terms I'm thinking this cell is equal to age divided by height instead of having to think about B3 divided by B4 So many people find that easier to think about and to use in Excel a couple of final things to be aware of when。

Naming cells number one， you can also name ranges。 So for example。 I could click here on a1 and then drag down to the lower right corner of my data which really at this point ends here in C 59。 I'll just release the mouse button and then I can go up here again Forms tab Def Na group and go to define name and I'll just click that and I'll call this health tracker So I am naming everything that's important on this spreadsheet for my health tracker I'm naming it health underscore tracker and then I could put in some comments and then click okay So now that range is also named and I could reference it in a formula if it made sense to do that。

 some health tracker and then enter so I just add it up all that stuff that doesn't make any sense but it is possible to name a range and then the last thing about it that's kind of cool is I can go here。In the upper left corner to the name box， click the arrow and go down to health tracker。

 That highlights everything that's important。 And then let's say I'd like to print this and hand it to Jason as a report。 All I have to do is go to file and then I'll go to print and look what it's trying to print It's trying to print the whole spreadsheet。

 So instead I'm going click here and go down and choose print selection。 because I had named that range。 It just made it much easier to print the exact right selection。 I just click choose health tracker and everything is selected that I want to print and then I go print it。 So I hope you see the benefits of from time to time naming a cell or naming a range。

 Thanks for watching。 I hope you found this tutorial to be helpful。![](img/9dd1003dd91567638f0fd301bbe58d5e_2.png)
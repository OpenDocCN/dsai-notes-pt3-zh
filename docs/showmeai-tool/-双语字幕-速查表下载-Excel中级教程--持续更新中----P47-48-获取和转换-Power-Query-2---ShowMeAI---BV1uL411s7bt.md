# 【双语字幕+速查表下载】Excel中级教程！(持续更新中) - P47：48）获取和转换／Power Query 2 - ShowMeAI - BV1uL411s7bt

![](img/c2aeb140e9824836fd55cd14e85f46f5_0.png)

In this intermediate guide to Excel's get and transform tool。 I'll show you how to get data from the web and transform it in Excel。 You can see here on sheet number 3， I have a couple of website URLs。 And you should have access to the same document that I'm using。

 If you look in the description below the video。 There's a link for it。 And the links take you to these two Wikipedia pages。 And both of these Wikipedia articles have tables in them that I would like to bring in to my Excel workbook to do that。 All I have to do is click on the URL to highlight it and then hold control and tap C to copy the URL。

 and then I'll jump back into Excel， and I'll go to the data tab and I'll look here in the get and transform data group。 and I'll just click from Web。 It opens up this new window and I can simply paste in the URL that I copied from Wikipedia。 I can click O and a window opens up。 This is the navigator。And the navigator will help me to choose what part of that Wikipedia page I would like to get and then transform in my Excel workbook。

 So look at what it gives me。 It says accolades， it says critical response document episodes。 And then it's got a whole bunch of tables below that。 Now， where did it get this information。 Well。 it got it from the URL that I provided。 if I go back to Wikipedia， I can see this better。 if I go down to episodes， for example， there's a list of each season of Marvel's agents of shield。

 the number of episodes when it aired and the viewership。 So let's say that's exactly the data I would like to import。 I just need to take note of the label for that section episodes。 go back into Excel and look for it。 there it is， I can click on it， and if it's perfect the way it looks here。

 I can just click load and it will be added to my workbook。 But I want to make some changes to the data。 So instead of。Clicking load。 I'm going to click transform data。 That takes me to the power query editor window。 and let's take a look at the data。 The data looks pretty good to me。

 but there are some things that are confusing about it。 For example。 this originally aired and then episodes is repeated and seasons repeated。 If I look back at the Wikipedia article。 It becomes more clear。 This originally aired sell is confusing things and is making it so that season gets repeated。

 episode gets repeated。 rank probably gets repeated。 So let's look at how to fix that。 So I don't really need that first row of data。 It's repetitious。 I don't really need this originally aired sell and everything else is really repeated。 So I'm going to click on row 1 at the bottom of the window it lists out everything that's included in row 1。

 and then I'll just go up here on the home tab and I'll just click remove rows。 There's an option to remove top rows， bottom rows or alternate。rows and some other options below。 I'm going go with remove top rows。 Now I need to specify how many rows。 just the one top row。 If I were to put two， it would remove the top two rows。 I'll just click okay。

 rowow number one is now gone。 Now let's remove column 1。 That's also unnecessary data。 So I'll make sure that I've selected column 1 and click remove columns。 And look。 here's another unnecessary column。 Now， this is pretty common。 whenever you're pulling data from the Internet or from other sources that are not natively from Excel。

 It's common to have unnecessary data or repetitious data or other unnecessary artifacts come from that original data into Excel。 And so that's what we're doing here as we're trying to clean it up。 So this is totally unnecessary。 It's just a repetition of column 2。 So again， remove columns。 It's gone。 let's look at the rest of the data。 Everything else looks pretty good。 Now。

 just like I showed in my。Beginner's guide to Excel， get and transform over here on the right。 I have a list of all of the applied steps that I've made as I've tried to clean up this data。 If I regret any of them， I can just click the red X to the left of that step。 and it will undo that step In the previous video I also showed how you can transform data by going to the transform tab and using tools like format to change the format of whatever you have selected in these ways。

 or you can also use replace values to help clean up your data。 Now。 there's one more change I want to make before I add this data to my workbook。 and that is this。 look， the headers don't quite match what I want。 I would like the first row to actually act as the header。 So to do that here on the home tab home ribbon。 I can just go here and click use first row as headers。

 Now， the data looks just how I want it to look。 and I'm ready to add it to my workbook。 The way you do that is。By going to the Home tab and clicking this close and load button Now。 clicking the top part of that button will almost instantly add this data that's from Wikipedia into my workbook。 If I click the bottom part of that button it gives me an option to close and load the data into other places or in other ways for now though I'll just click close and load and the table that was in Wikipedia has been transformed and then loaded into my workbook and it was added as a new sheet sheet 6 I can now right click on that and rename it I could name it something like episodes of agents of Shield Tap enter and this data is ready to be used in Excel。



![](img/c2aeb140e9824836fd55cd14e85f46f5_2.png)
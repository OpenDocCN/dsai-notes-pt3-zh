# 【双语字幕+速查表下载】Excel正确打开方式！提效技巧大合集！(持续更新中) - P44：44）溢出结果和修复SPILL! 错误 - ShowMeAI - BV1Jg411F7cS

![](img/3d53142b9c93da9b51542a11434fa926_0.png)

In this video， I'm going show you some examples of how you can spill the results of a formula in Microsoft Excel and we'll also look at the spill error that you may get sometimes and we'll look at how to fix that。 Now the ability to spill is available in Microsoft 365 versions of Excel and it may be in also some other versions but not all older versions of Excel are going to have this capability So you can see here I have a spreadsheet with a list of bands。

 their albums and some other information about those albums。 Let's say I would like to duplicate the data in column C D and E。 and I want to put that duplicated information over here on the right。 Of course I could highlight it， copy paste etc but take a look at what you can now do in Excel you can simply click on a cell type equals and then either select the range or you could type in the cell references and then tap enter Let's look at both ways So I'll click here on cell C1 and I'll hold。

The click， and I'll drag it over to column E， and I'll pull it down all the way to the bottom of the data。 And now I've released the mouse click。 And now if I go back up to the top。 you can see what the formula says equals C1 through E45 I tap enter on the keyboard and watch what happens with this formula in cell J1。 I was trying to make that cell equal to this entire range C1 through E45。 Well。

 it's not possible to do that in one cell。 and so Excel spilled the results of that formula。 It' spilled it over into column K column L and all the way down to row 45。 So that's what's meant when you hear about spilled results or spilled arrays or spilled ranges。 This is the spilled range down here。 And if I click on any of the data that was spilled below or to the right of the original cell。

 you can see in the formula bar that the formula。It is grayed out。 Why is that， Well。 because there is no formula in this case in cell K6。 there's no formula in K3 or in J5。 The formula that's producing all of these results is found here in cell J1。 And so in J1。 it's not gray out。 you can see the formula in dark black。 Now。

 this is just one example of spilled results in Excel。 fairly recently。 Microsoft Excel added new dynamic array functions。 And in many cases。 those dynamic array functions will produce spilled results。 Watch for future videos that I'll do on the dynamic array functions。 Now， from time to time。

 when you try to spill results， you'll end up getting an error。 So I'm going to hold control in tab Z to undo those changes that I made。 And here in cell J 7。 I'm going type the word test T enter。 Now let me try the same formula again。 So I'll go to J1 equals。This time， instead of just clicking and dragging to get column C D and E。

 I'm going to simply click in cell J1。 And after the equal sign， I'll type in C1 colon E45。 So I've just typed in the cell references rather than clicking and dragging Now I can tap enter on the keyboard and it should work right？

 No， actually it doesn't because when I tap enter Excel tried to spill the results of the formula to the right and also below cell J2。 but it couldn't。 why because I had some data blocking the results。 So generally that's what the spill error is trying to tell you that something is getting in the way of the spilled results to fix this all I have to do is click on test。 tap delete， tap enter and the data is able to spill and it does so immediately。 Now， of course。

 the same thing will happen if I click on results that have already spilled and type something doing that produces the spill error also one other common。Mistake that produces the spill error is sometimes people will go to cell， let's say J4 type equals。

 And instead of putting in the cell references the range name or clicking and dragging to specify what range they want to pull over and spill。 Instead， sometimes people will say I just want all of column C D and E。 by clicking and dragging to select the column headings。 This should produce the entire column all the way down hundreds and hundreds of records down。

 even if they're blank， they should be pulled over here， starting in cell J4。 but watch what happens when I tap enter。 I get the spill error。 Why I don't have anything blocking it。 Well， the reason why I get that error is because Excel is trying to put every single cell in column C D and E from row 1 down thousands and thousands of rows。 It' trying to put all of that into the same space except skipping the first three rows。 Well。

 that's not going to be possible。 There's not enough。🎼Room for that data。 So watch what happens now if I click on the cell and I go to the edge of the cell and click and drag and pull it up。 That should move the formula up。 Now there's room。 And now all of my data fits in the spreadsheet。 And so it was able to spill。 So this is just the beginning of what you can do with spilled results from formulas。

 Watch for my future videos on the dynamic array functions and you'll see even more that can be done with spilled results。 Thanks for watching， I hope you found the tutorial to be helpful。 If you did， please like。 follow and。 And when you do click the bell so you'll be notified when I post another video。 If you'd like to support my channel， you can do that through my Patreon account or by buying channel merch。

 and you'll see links to those opportunities in the description below the video。![](img/3d53142b9c93da9b51542a11434fa926_2.png)

![](img/3d53142b9c93da9b51542a11434fa926_3.png)
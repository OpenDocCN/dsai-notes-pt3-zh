# 【双语字幕+速查表下载】Excel中级教程！(持续更新中) - P55：56）四分位数函数 - ShowMeAI - BV1uL411s7bt

![](img/b14464df2d049c8c13066eebdd554f57_0.png)

In this video， I will show you how to use the quartile function in Excel。

 and the example I want to give is of a class and a list of test scores。

 So let's say I just gave a test to this group of students and you can see I've calculated the top three scores。

 bottom three scores， the high score and the low score。 If you want to learn how I did that。

 you should watch my tutorial on the large and small functions in Excel。 but in this video。

 we're going to focus on how to draw even more information out of the data we have here on their test scores。

 I would like to know what the first quartile of test results is and the second quartile third and fourth。

 And that way I'll know the scores that the students would have to receive in order to be in that fourth quartile or the third quartile etc ce。

 So it would be fairly complicated to do this were it not for the Excel quartile function。

 Let's look at how it works。 And I want to start with the first quartile。

 So I'll just click on cell B 10 and type equal。quartile left parenthesis。

 and you can see what Excel is looking for here。 It wants an array and then a comma and then quart for quartile。

 So by array， it just means a range of cells。 So I'm going click here on G2 and drag down to select all of the test scores。

 That's going to be my array next I'll just type comma。

 and then I just need to decide which quartile am I interested in here。 Well。

 I'm interested in the first quartile。 because that's the information I'm looking for in this particular cell。

 So I'll just type a1 and then the right parenthesis tap enter on the keyboard。

 and it returns the number 71。75。 So knowing that the low score is 58。

 that tells us that in order to be in the first quartile of scores。

 a student would have to score between 58 and 71。75 And what that means is that 25% of the results here fall in between 58 and。

71。5 That's the low quartile， the first quartile。 Okay， what about the second quartile Well。

 I could click on cell B8 type equals type quartile and repeat the same steps basically but it's actually much easier and quicker to simply copy and paste the formula that we already have So I've clicked on B10 I'm going to hold control and tap C to copy that and I'll paste it here for the second quartile while I'm at it might as well past it in for the third quartile Now。

 of course it's just giving me the same results71。75。

 The reason for that is because it still has the number1 in the formula So to fix that all you have to do is click on the cell in this case B8 it highlights the cell and up in the formula bar I can easily change that one to a2 and now it should give me the second quartile when I tap enter and it does 83。

5 Now。Do the same thing for the third quartile。 I'll just click on B6 in this case。

 go up to the formula bar and change the one to a3 tap enter。 And now we have the third quartile。

 Now we already know what the high score is。 The high score listed here is  a00。

 and I figured that out by using a max function and formula。 And so because of that。

 we don't really need the fourth quartile。 the fourth quartile would just give us the same number。

 it would give us the highest score， the highest possible number。

 So even though we don't have to do a fourth quartile， let's do it anyway。 So once again。

 I'll just copy paste that same formula in。 But this time I'll change the one to a four tap enter。

 it gives me the same results。 but now I'm using a different function。

 instead of the max function I'm using the quartile function。 All right， we have all four quartiles。

 And just as a review what this information means is that out of all of the。

Test results data25% of that data falls between 58 and 71。5，25% falls between 71。75 and 83。

525% falls between 83。5 and 94 and 25% falls between 94 and 100 so any student that got a score of 94 through 100 made it into the fourth quartile of scores for the class。

 One last thing you might want to be aware of about the quartile function in Excel is that you can also have it calculate the low score。

 Now I already have the low score calculated。 I used a min function and formula to calculate the smallest number in this range but I could have just used the quartile function so let's switch it to quartile I could type equals quartile left parenthesis select the array or range type comma and then which quartile do I want to put here。

123 or 4。none of the above， I would put zero and then write parenthesis， tap enterter。

 and it returns the lowest number from this list 58。



![](img/b14464df2d049c8c13066eebdd554f57_2.png)
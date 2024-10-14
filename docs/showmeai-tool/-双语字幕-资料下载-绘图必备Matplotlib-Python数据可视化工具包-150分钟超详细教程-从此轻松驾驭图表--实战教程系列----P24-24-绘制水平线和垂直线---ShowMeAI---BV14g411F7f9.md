# 【双语字幕+资料下载】绘图必备Matplotlib，Python数据可视化工具包！150分钟超详细教程，从此轻松驾驭图表！＜实战教程系列＞ - P24：24）绘制水平线和垂直线 - ShowMeAI - BV14g411F7f9

Alright， three more， just three more questions。 This is a， this is a marathon， isn't it， Alright。 so how， how do you draw。Horizontal and vertical lines。 So you might want to draw some reference lines for people to look at for various places in your graph。 So let's。

![](img/7a379eaa3c65d47a09c81a755a8d562e_1.png)

![](img/7a379eaa3c65d47a09c81a755a8d562e_2.png)

![](img/7a379eaa3c65d47a09c81a755a8d562e_3.png)

let's come up here。We'll get our little template。![](img/7a379eaa3c65d47a09c81a755a8d562e_5.png)

We'll do A X dot plot， X and Y。![](img/7a379eaa3c65d47a09c81a755a8d562e_7.png)

Alright， so let's say that we want to draw a horizontal line at 100， a horizontal line at， oh。 let's maybe do 50 and negative 50。And then let's also do a vertical line at negative 4。 So how do we do that？ Well， these nice little A X dot H。Lines function and Ax do v lines function。 So let's look at the documentation for H lines。

![](img/7a379eaa3c65d47a09c81a755a8d562e_9.png)

So you pass in。![](img/7a379eaa3c65d47a09c81a755a8d562e_11.png)

A x dot H line。 So you pass in y， which is a scalar or a sequence of scrs。 This is the y indexes where to plot the lines。 So we're going to say we wanted it at。Negative 50 and 50。 And then you also have to pass in the x min and the x max。 So do you want the。 do you want the line to go from negative 4 to 0， Do you want it to go all the way across the graph？

 And in this case， we want it to go all the way across the graph。 So I'm actually just going to say。 give me the minimum。Of my X data。And give me the maximum of my X data。![](img/7a379eaa3c65d47a09c81a755a8d562e_13.png)

And。There you go。 So we're going from the minimum of our x。Up to the maximum of our x。 And if we wanted this to go， you know， shorter for some reason， well。 we could have it go from 0 to 0 to 5 or whatever。Okay。 and then the same exact thing for A X dot V lines。 So in this case， we just want。

A line at negative 4。 And let's go from the minimum of y to the maximum of y。And there you go。And if you want， you can pass in colors so you can pass in colors equals red。 or you can pass in a list of colors。 So let's say red and blue。And there you go。 So now we're coloring our lines by different。

![](img/7a379eaa3c65d47a09c81a755a8d562e_15.png)
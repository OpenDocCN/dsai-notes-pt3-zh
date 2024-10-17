# P47：L47- The Definite Integral Part I - Approximating Areas with rectangles - ShowMeAI - BV1544y1C7pC

I'm excited because we've been stuck with differentiation for quite a long time in this course。

 but finally， we get to see in this video the second major tool in calculus， which is the integral。

 But what is the integral and why is it helpful and what kind of questions is it going to answer。😊。



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_1.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_2.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_3.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_4.png)

So I want to begin with a very geometric question， we have some curve。

 this is the graph of y equal to x squared。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_6.png)

And I graphed it between zero and one over here and what I'm asking is。

 what is this area under the curve， what is this area over here？😡。



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_8.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_9.png)

It's not a nice triangle， it's not a nice circle， it's not a nice rectangle。

 it's not one of the ones that I have a formula for。

 it's a sort of weird curve top and then all this portion down here so how can we figure out what that area is？



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_11.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_12.png)

Now the integral is going to answer many different questions。

 and this is just one of the sort of foundational ones that we're going to use， in fact。

 to define the notion of the integral。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_14.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_15.png)

What I going to do first to give you a relatively crude approximation。



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_17.png)

I'm going to come here and I'm going to put a bunch of rectangles and my rectangles sort of overlap with my curve。

 you see that what I've done here is I've divided my zero up to one into five different regions， 0。2。

4。6。8 and1 and I've given a rectangle that has a width down here always of that 0。

2 so the width is always going to be the 0。2。😡。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_19.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_20.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_21.png)

But then the height of my rectangle， what I do is I go and I make the right point。

 always line up on the curve。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_23.png)

So this is a bunch of rectangles where their right endpoints are on the curve。

 but they sort of spill out to the left and they've got these even widths of 0。2。



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_25.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_26.png)

So。What if I compute the area of these rectangles， As we can see， it'll be a little bit more。

 it will be an overestimate to the area under the particular curve of x squared。

 but it's not completely terrible。 And indeed， if I wanted to do it numerically， there is rectangle。

 So I should be able to add them up pretty quickly。

 I can figure what the area here is notice that the width is the 0。2， the 0。

2 all the way along but that the height of them changes in this case where I'm using 0。2， it go to 0。

2 squared here is 0。4 and because it's x squared to go to 0。4 squared and so on。

 And then I can add all those up and I get apparently it's 0。44。😡。



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_28.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_29.png)

This doesn't seem terrible by the way， if you imagine the triangle that went from zero to11 that point there。

 that triangle would have area a half and this looks like a little bit less than that triangle so it seems kind of reasonable and then I will again note that what we' have been using is the so-called right endpoints where the heights of my triangles have been specified by the right endpoint of them going up to the level of the function。

Now this is not the only way that I can do this for instance。

 if I have this curve and I want to measure the area under it what if instead of using right endpoints I use some slightly different rectangles in this case the rectangles I'm using the left endpoints so this is the rectangle of height0 the rectangle of height 0。

2 squared of 0。4 squared 0。6 squared and so on so again five different rectangles and this time the area of them is going to be a little bit too small and I again can go and figure out what that computation is it's just the 0。

2 stayed the same but my heights have all changed a little bit and now I've gotten the value of 0。

24 which was a good ways underneath the 0。44 that we saw before。😡。



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_31.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_32.png)

So we have these two different approximations for effectively the same thing。

Now can I do any better than this note that here I used five different rectangles。Well。

 what if instead of five rectangles， I broke it up into 10 different rectangles into that same basic idea？



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_34.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_35.png)

Notice that now I think that the error has gotten in a little bit better that because it's sort of a finer resolution。

 my rectangles have come closer to approximating the value。 indeed。

 if we show what we had before here， this was the case with five。

 and you notice that there's these big gaps， there's a big gap here， here， here。😡。



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_37.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_38.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_39.png)

But when I use 10， yeah， there's gaps， but they've gone definitely a little bit smaller。

So I think the lesson that we can take from this is that when we have a smaller number of rectangles to approximate that we get a bigger error and that when we have a larger number of rectangles。

 we're going to have a smaller error， so here is the fundamental idea if I allow RN to be a shorthand and RN is going to be standing for the area if I approximate it with n different rectangles。

😡。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_41.png)

Well， in this case， we have 10 different rectangles， so I've approximated with R 10。

 then the big idea is this。What if instead of 10 different rectangles。

 I used 50 or 100 or 100 million different rectangles。 All of these are possibilities。

 And in particular， what happens if I let the value of n go to infinity？

 So the big idea here is that the area， the true area。

 the actual value of this is equal to this limit。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_43.png)

As N goes to infinity of the rectangles as the number of them is going to infinity。

 that is we are saying that the rectangle approximation with n intervals as you allow the end to get bigger and bigger and bigger。

 your approximation gets better and better and better。

 these little holes get smaller and smaller and smaller and you approach the area underneath this curve。



![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_45.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_46.png)